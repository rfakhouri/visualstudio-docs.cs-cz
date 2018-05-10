---
title: Ladění - vizualizaci dat
description: Ladění je běžné a potřeby součástí programování. Visual Studio pro Mac obsahuje celou sadu funkcí, které usnadňují easy ladění. Tento článek vypadá na různých datových vizualizacemi, které lze zobrazit při kontrole objekty v ladicím programu.
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.technology: vs-ide-debug
ms.assetid: 527E6BEC-EF15-4002-ACB5-62AE1C16F6B7
ms.openlocfilehash: 5ee16324a312eca79de2f3b356a5f3be941f5e7b
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
---
# <a name="data-visualizations"></a>Vizualizaci dat

Visual Studio pro Mac zahrnuje podporu uživatelského rozhraní pro ladicí program, což vizualizace hodnoty proměnné, pole nebo vlastnost při ladění. Tato data vizualizérech zobrazit rozšířenou verzi dat a umožňují vývojářům zkontrolovat známé struktury, například zobrazující barva struktury barev.

Vizualizérech v ladění **místní** pad lze zobrazit kliknutím na ikonu preview, který se zobrazí vpravo hodnoty, když nastavení ukazatele myši na řádek:

 ![Místní odsazení](media/data-visualizations-image9.png)

Níže uvedeného seznamu vypadá na řadu nové vizualizace, které jsou k dispozici při ladění v sadě Visual Studio for Mac.

## <a name="point"></a>bod
Bod/PointF nebo CGPoint v iOS a Mac se vykreslí jako řazené kolekce členů zobrazující hodnoty X a Y v panelu pro ladění:

 ![Vizualizace bodu](media/data-visualizations-image10.png)

## <a name="size"></a>Velikost
Velikost/SizeF nebo CGSize v iOS a Mac, se vykreslují jako obdélník. Kreslení škálování, dokud dimenzi zvětšování po 250, od této chvíle se bude škálovat rámeček s největší dimenzí jako 250:

![Velikost vizualizace](media/data-visualizations-image11.png)


## <a name="rectangle"></a>rámeček
Rámeček nebo RectangleF nebo CGRect v iOS a Mac, se zobrazí, dimenzí a původu. Podobně jako velikost, kreslení škálování, dokud dimenzi zvětšování po 250:

 ![Vizualizace obdélníku](media/data-visualizations-image12.png)

## <a name="coordinate"></a>Souřadnice
Souřadnice jsou zobrazeny na mapě, s připnutou k centru umístění:

![Koordinaci vizualizace](media/data-visualizations-image13.png)

## <a name="color"></a>Barva
Bude se zobrazovat vlastnosti UIColor, CGColor a barvu znázorňující preview barvu, RGBA komponent, hodnoty Hue-sytost světlosti a šestnáctkové hodnoty barvu:

![Vizualizace barev](media/data-visualizations-image14.png)


## <a name="images"></a>Obrázky

Média bude vykreslen škálování, až do maximální dimenze 250 a bude možné rozšířit, aby vyhovoval když bitovou kopii překračuje 250:

 ![Vizualizace bitové kopie](media/data-visualizations-image15.png)


## <a name="bezier-curves"></a>Bézierovy křivky

Se zobrazí vizualizér `NSBezierPath`:

![Vizualizace Bézierovu křivku](media/data-visualizations-image16.png)


## <a name="string"></a>String

Řetězec méně než 100 znaků, se zobrazí v plné výši bez náhled. Zobrazí se delší řetězce v úplné ve verzi preview. Řetězce se upravovat, a vizualizér obsahuje tlačítko pro úpravy, povolení řetězcovou hodnotu k provádění úprav, buď ve verzi preview, nebo v řetězec hodnotu editoru vidíte níže:

![Vizualizace řetězec](media/data-visualizations-image17.png)

### <a name="small-strings"></a>Malé řetězců:
![Vizualizace malé řetězec](media/data-visualizations-image18.png)]

### <a name="medium-length-strings"></a>Střední délky řetězce:
![Vizualizace střední řetězec](media/data-visualizations-image19.png)

### <a name="editor"></a>Editor:

 ![Vizualizace editoru](media/data-visualizations-image21.png)

## <a name="ienumerable"></a>Rozhraní IEnumerable

Rozhraní IEnumerable zobrazí všechny hodnoty; hodnoty jednotlivých lze zobrazit kliknutím **zobrazit** tlačítko hodnoty. Možnost IEnumerable nezobrazí hodnoty pro objekty, jako `Array`, `ArrayList`, `List<>`, `Dictionary<,>` jako mají své vlastní vizualizérech ladicí program.

![Rozhraní IEnumerable vizualizace](media/data-visualizations-image22.png)

## <a name="other-visualizers"></a>Další Vizualizérech

Některé typy, které mají své vlastní vložené vizualizérech taky jsou uvedeny níže:

 ![Jiné vizualizace](media/data-visualizations-image23.png)

*   **Primitiva**
    *   Tato rutina ukáže, Nezpracovaná hodnota primitivního typu.
*   **výčet**
    *   Tato akce zobrazí hodnota pole bez kvalifikátor typu výčtu.
*   **řazené kolekce členů**
    *   Zobrazí ve formátu ()
*   **Hodnotu Null**
    *   Zobrazí hodnotu "null".
*   **ADRESA URL**
    *   Tato akce zobrazí prokliknutelný hypertextový odkaz.
*   **IntPtr**
    *   Tato akce zobrazí hexadecimální reprezentace IntPtr.
