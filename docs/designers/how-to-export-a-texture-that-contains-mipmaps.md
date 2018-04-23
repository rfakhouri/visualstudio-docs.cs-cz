---
title: 'Postupy: Export textury obsahující mipmapy'
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 3d1ad14b-44fb-4cf0-a995-5e2f60026524
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0ff27404a37eb641deb8409e6e529bf052264591
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-export-a-texture-that-contains-mipmaps"></a>Postupy: Export textury obsahující mipmapy

Kanál obsahu bitové kopie můžete vygenerovat mipmaps zdrojové bitové kopie v rámci fáze sestavení vašeho projektu. K dosažení určité účinky, někdy je nutné k určení bitové kopie obsahu jednotlivých úrovní MIP ručně. Pokud nepotřebujete k určení bitové kopie obsahu jednotlivých úrovní MIP ručně, generování mipmaps v čase vytvoření buildu zajišťuje mipmap obsah nikdy stát se na synchronizaci. Také eliminuje náklady výkonu generování mipmaps za běhu.

Tento článek se zabývá:

- Konfigurace zdrojové bitové kopie na zpracování kanálu obsahu bitové kopie.

- Konfigurace obsahu kanálu bitové kopie, který se má generovat mipmaps.

## <a name="export-mipmaps"></a>Export Mipmaps

Mipmapping poskytuje automatické místo na obrazovce úroveň--detailů pro texturou ploch v 3D hry nebo aplikace. Zvyšuje tak výkon vykreslování hry nebo aplikace pomocí předem computing vzorkovat nižší verze texturou. Předem computing vzorkovat nižší verze, znamená to, že celá texture nemusí být nižší vzorkovat pokaždé, když ho je vzorků.

### <a name="to-export-a-texture-that-has-mipmaps"></a>Chcete-li exportovat texture, který má mipmaps

1.  Začněte základní texturou. Nahrajte existující soubor bitové kopie, nebo ji vytvořte jak je popsáno v [postupy: vytvoření základní Texture](../designers/how-to-create-a-basic-texture.md). Pro podporu mipmaps, zadejte texture, který má šířka a výška, které jsou stejné power dva velikosti, například 64 x 64, 256 x 256 nebo 512 x 512.

2.  Nakonfigurujte texture soubor, který jste právě vytvořili, aby se zpracování obsahu kanálu bitové kopie. V **Průzkumníku řešení**, otevřete místní nabídku pro soubor textury jste vytvořili a potom zvolte **vlastnosti**. Na **vlastnosti konfigurace** > **Obecné** nastavte **typ položky** vlastnost **bitové kopie obsahu kanálu**. Ujistěte se, že **obsahu** je nastavena na **Ano** a **vyloučit ze sestavení** je nastaven na **ne**. Vyberte **použít**.

   **Bitové kopie obsahu kanálu** zobrazí se stránka vlastností konfigurace.

3.  Konfiguraci kanálu bitové kopie obsahu k vygenerování mipmaps. Na **vlastnosti konfigurace** > **bitové kopie obsahu kanálu** > **Obecné** nastavte **generovat Mips** vlastnost **Ano (nebo generatemips)**.

4.  Vyberte **OK**.

Při sestavování projektu bitové kopie obsahu kanálu převede zdrojové bitové kopie z formátu pracovní výstupní formát, který jste zadali, MIP úrovní. Výsledek zkopírován do výstupního adresáře projektu.