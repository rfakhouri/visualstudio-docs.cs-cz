---
title: 'Postupy: Export textury obsahující mipmapy'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 3d1ad14b-44fb-4cf0-a995-5e2f60026524
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f5226903112d06d5efa362c61db938124eed8e68
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62897315"
---
# <a name="how-to-export-a-texture-that-contains-mipmaps"></a>Postupy: Export textury obsahující mipmapy

Kanál s obsahem obrazu může generovat mipmapy ze zdrojového obrazu jako část fáze se sestavením projektu. K dosažení určitých efektů, někdy je nutné ručně zadat obsah bitové kopie každé úrovně MIP. Když není nutné ručně zadat obsah bitové kopie každé úrovně MIP, generování mipmaps v okamžiku sestavení zajistí, že obsah mipmap nikdy stát mimo synchronizace. Také eliminuje náklady na generování Mipmap v době běhu.

Tento článek se týká:

- Konfigurace zdrojového obrazu pro zpracování obsahu kanálu obrázku.

- Konfigurace obsahu kanálu obrázku ke generování Mipmap.

## <a name="export-mipmaps"></a>Export mipmapy

Mipmapping zajišťuje úroveň of-Detail automatické místo na obrazovce pro texturované povrchy u 3D her nebo aplikací. To zvyšuje rychlost vykreslování hry nebo aplikace předvýpočtem zredukovaných verzí textur výpočtem předem. Předem computingu předvýpočtem zredukovaných verzí, znamená, že celá textura nemusela být zredukována pokaždé, když se odebírá.

### <a name="to-export-a-texture-that-has-mipmaps"></a>Pro export textury obsahující mipmapy

1. Začněte základní texturou. Načtěte stávající obrazový soubor nebo jej vytvořte podle pokynů v [jak: Vytvoření základní textury](../designers/how-to-create-a-basic-texture.md). Na podporu Mipmap určete texturu, která má šířku a výšku, které mají stejný výkon rozměry, například 64 x 64, 256 x 256 nebo 512 x 512.

2. Nakonfigurujte soubor textury, které jste právě vytvořili, aby byl zpracován kanálem obsahu obrázku. V **Průzkumníka řešení**, otevřete místní nabídku pro soubor textury, který jste vytvořili a klikněte na tlačítko **vlastnosti**. Na **vlastnosti konfigurace** > **Obecné** nastavte **typ položky** vlastnost **kanál obsahu obrazu**. Ujistěte se, že **obsahu** je nastavena na **Ano** a **vyloučit ze sestavení** je nastavena na **ne**. Vyberte **Použít**.

   **Kanál obsahu obrazu** se zobrazí stránka pro konfiguraci vlastností.

3. Nakonfigurujte kanál obsahu obrázku ke generování Mipmap. Na **vlastnosti konfigurace** > **kanál obsahu obrazu** > **Obecné** nastavte **generovat Mips** vlastnost **Ano (/ generatemips)**.

4. Vyberte **OK**.

Při vytváření projektu kanál obsahu obrázku tak převede zdrojový obraz z pracovního formátu na výstupní formát, který jste zadali, včetně úrovní MIP. Výsledek je zkopírován do výstupního adresáře projektu.