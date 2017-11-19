---
title: "Postupy: Export texturou pro použití s aplikací Javascipt nebo Direct2D | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 241c25fe-764e-4e1b-ad32-b1377dcbb605
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ad01fe04374ee9ae8c1514f8194a91c2247a5311
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-export-a-texture-for-use-with-direct2d-or-javascipt-apps"></a>Postupy: Export textury pro použití s rozhraním Direct2D nebo aplikacemi JavaScript
Kanál obsahu bitové kopie můžete vygenerovat textury, které jsou kompatibilní s Direct2D na interní vykreslování konvence. Textury tohoto druhu, jsou vhodné pro použití v aplikacích, které používají Direct2D a v aplikacích pro UPW vytvořit pomocí jazyka JavaScript.  
  
 Tento dokument ukazuje tyto aktivity:  
  
-   Konfigurace zdrojové bitové kopie na zpracování kanálu obsahu bitové kopie.  
  
-   Konfigurace obsahu kanálu bitové kopie, který se má generovat texture, který můžete použít v aplikaci Direct2D nebo JavaScript.  
  
    -   Vygenerujte soubor .dds-komprimovaného bloku.  
  
    -   Generovat předem vynásobí alfa.  
  
    -   Zakažte generování mipmap.  
  
## <a name="rendering-conventions-in-direct2d"></a>Vykreslování názvů v Direct2D  
 Textury, které se používají v rámci Direct2D musí splňovat tyto Direct2D interní vykreslování konvence:  
  
-   Direct2D implementuje průhlednost a průsvitnosti pomocí předem vynásobí alfa. Textury použít s Direct2D musí obsahovat předem vynásobí alpha Přestože textury nepoužívá průhlednost nebo průsvitnosti. Další informace o předem vynásobí alpha najdete v tématu [postupy: Export Texture, který má předem vynásobený Alpha](../designers/how-to-export-a-texture-that-has-premultiplied-alpha.md).  
  
-   Textury je potřeba zadat ve formátu .dds pomocí jedné z těchto formátů bloku komprese:  
  
    -   Komprese BC1_UNORM  
  
    -   Komprese BC2_UNORM  
  
    -   Komprese BC3_UNORM  
  
-   Mipmaps nejsou podporovány.  
  
#### <a name="to-create-a-texture-thats-compatible-with-direct2d-rendering-conventions"></a>Chcete-li vytvořit texture, který je kompatibilní s Direct2D vykreslování konvence  
  
1.  Začněte základní texturou. Načíst stávající image, nebo vytvořte novou, jak je popsáno v [postupy: vytvoření základní Texture](../designers/how-to-create-a-basic-texture.md). Pro podporu komprese bloku ve formátu .dds, zadejte texture, který má šířka a výška, které jsou čtyři velikosti, například 100 x 100, velikosti 128 × 128 nebo 256 x 192 násobky. Protože mipmapping není podporována, textury nemá čtvercový a nemá být násobek dvou velikost.  
  
2.  Soubor textury nakonfigurujte, aby se zpracování obsahu kanálu bitové kopie. V **Průzkumníku řešení**, otevřete místní nabídku pro soubor textury, kterou jste právě vytvořili a potom zvolte **vlastnosti**. Na **vlastnosti konfigurace**, **Obecné** nastavte **typ položky** vlastnost **bitové kopie obsahu kanálu**. Ujistěte se, že **obsahu** je nastavena na **Ano** a **vyloučit ze sestavení** je nastaven na **ne**a potom vyberte  **Použít** tlačítko. **Bitové kopie obsahu kanálu** zobrazí se stránka vlastností konfigurace.  
  
3.  Nastavte výstupní formát na jednom z formátů kompresí bloku. Na **vlastnosti konfigurace**, **bitové kopie obsahu kanálu**, **Obecné** nastavte **komprimovat** vlastnost  **Komprese BC3_UNORM (nebo compress: BC3_UNORM)**. Vybrat kteroukoli z jiné BC1, BC2 nebo BC3 formáty, může v závislosti na vaše požadavky. Direct2D aktuálně nepodporuje BC4 BC5, BC6 nebo BC7 textury. Další informace o různých formátech BC najdete v tématu [bloku komprese (Direct3D – 10)](http://msdn.microsoft.com/library/windows/desktop/bb694531.aspx).  
  
    > [!NOTE]
    >  Komprese formátu, který je zadán Určuje formát souboru, který je produkovaný kanálu obsahu bitové kopie. Liší se od **formátu** vlastnost zdrojové bitové kopie v editoru obrázků, který určuje formát zdrojový soubor bitové kopie, protože uložená na disku – to znamená, *pracovní formátu*. Obvykle nechcete, aby pracovní formátu, který se komprimují.  
  
4.  Konfiguraci kanálu obsahu bitové kopie k vytvoření výstupu, který používá předem vynásobí alfa. Na **vlastnosti konfigurace**, **bitové kopie obsahu kanálu**, **Obecné** nastavte **převést na formát předem vynásobená alfa** Vlastnost **Ano (nebo generatepremultipliedalpha)**.  
  
5.  Konfiguraci kanálu obsahu bitové kopie, tak, aby to není generovat mipmaps. Na **vlastnosti konfigurace**, **bitové kopie obsahu kanálu**, **Obecné** nastavte **generovat Mips** vlastnost **Ne**.  
  
6.  Vyberte **OK** tlačítko.  
  
 Při sestavování projektu bitové kopie obsahu kanálu převede zdrojové bitové kopie z formátu práci na výstupní formát, který jste zadali – převod zahrnuje generování předem vynásobí alpha – a výsledek bude zkopírován do výstupního adresáře projektu.