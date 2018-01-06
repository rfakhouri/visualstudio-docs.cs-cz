---
title: "Postupy: Export Texture, který obsahuje Mipmaps | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d1ad14b-44fb-4cf0-a995-5e2f60026524
caps.latest.revision: "7"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ef8f94ae451902c8f7b5e5d2b5f3156d01107589
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-export-a-texture-that-contains-mipmaps"></a>Postupy: Export textury obsahující mipmapy
Kanál obsahu bitové kopie můžete vygenerovat mipmaps zdrojové bitové kopie v rámci fáze sestavení vašeho projektu. Pokud není potřeba ručně zadejte obsahu bitové kopie každé úrovně MIP – jako mohou k dosažení určité účinky – generování mipmaps v čase vytvoření buildu zajišťuje, že obsah mipmap nikdy stát se na synchronizaci a eliminuje náklady výkonu generování mipmaps v době běhu.  
  
 Tento dokument ukazuje tyto aktivity:  
  
-   Konfigurace zdrojové bitové kopie na zpracování kanálu obsahu bitové kopie.  
  
-   Konfigurace obsahu kanálu bitové kopie, který se má generovat mipmaps.  
  
## <a name="exporting-mipmaps"></a>Export Mipmaps  
 Mipmapping poskytuje automatické místo na obrazovce úroveň--detailů pro texturou ploch v 3D hry nebo aplikace. Zvyšuje tak výkon vykreslování hry nebo aplikace pomocí předem computing vzorkovat nižší verze texturou tak, aby celý texture nemá na nižší odběr pokaždé, když je vzorků.  
  
#### <a name="to-export-a-texture-that-has-mipmaps"></a>Chcete-li exportovat texture, který má mipmaps  
  
1.  Začněte základní texturou. Nahrajte existující soubor bitové kopie, nebo ji vytvořte jak je popsáno v [postupy: vytvoření základní Texture](../designers/how-to-create-a-basic-texture.md). Pro podporu mipmaps, zadejte texture, který má šířka a výška, které jsou stejné power dva velikosti, například 64 x 64, 256 x 256 nebo 512 x 512.  
  
2.  Nakonfigurujte texture soubor, který jste právě vytvořili, aby se zpracování obsahu kanálu bitové kopie. V **Průzkumníku řešení**, otevřete místní nabídku pro soubor textury, kterou jste právě vytvořili a potom zvolte **vlastnosti**. Na **vlastnosti konfigurace**, **Obecné** nastavte **typ položky** vlastnost **bitové kopie obsahu kanálu**. Ujistěte se, že **obsahu** je nastavena na **Ano** a **vyloučit ze sestavení** je nastaven na **ne**a potom vyberte  **Použít** tlačítko. **Bitové kopie obsahu kanálu** zobrazí se stránka vlastností konfigurace.  
  
3.  Konfiguraci kanálu bitové kopie obsahu k vygenerování mipmaps. Na **vlastnosti konfigurace**, **bitové kopie obsahu kanálu**, **Obecné** nastavte **generovat Mips** vlastnost **Ano (nebo generatemips)**.  
  
4.  Vyberte **OK** tlačítko.  
  
 Při sestavování projektu bitové kopie obsahu kanálu převede zdrojové bitové kopie z formátu pracovní výstupní formát, který jste zadali, včetně úrovní MIP a výsledek je zkopírován do výstupního adresáře projektu.