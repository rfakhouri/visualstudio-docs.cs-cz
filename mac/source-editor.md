---
title: Editor zdrojového kódu
description: Pomocí editoru zdroje v sadě Visual Studio pro Mac
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.assetid: A018A314-C1C4-4F36-BCB6-2D434208FCFE
ms.openlocfilehash: 8660ee0de90813e95a221c3b4ea3a50528b4307a
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2018
---
# <a name="source-editor"></a>Editor zdrojového kódu

Editor spolehlivý zdroj je nezbytné pro psaní kódu stručně a efektivně. Visual Studio pro Mac poskytuje sofistikované zdroj editor, který je v centru vaši interakci s rozhraní IDE. Editor zdroj poskytuje funkce, které můžete očekávat a potřebují k práci s snadné: Z základy takové zvýraznění syntaxe, fragmenty kódu a kódu skládání, výhod integrace kompilátoru jeho Roslyn, jako je plně funkční IntelliSense kódu dokončení.

Editor zdrojového kódu v sadě Visual Studio pro Mac umožňuje jednotné prostředí s všechny ostatní funkce v prostředí IDE, jako je například ladění, refaktoring a integraci správy verzí.

Tento článek představuje některé klíčové funkce editoru zdroje a popisuje, jak Visual Studio pro Mac můžete být stejně produktivní nejblíže.

## <a name="the-source-editor-experience"></a>Editor zdrojové prostředí

Zobrazení a efektivně přesunutí v rámci kódu je nedílnou součástí pracovní postup vývoje. Jakým způsobem se rozhodnete zobrazit a spravovat, že kód je osobní rozhodnutí, které se liší mezi vývojáři - a často mezi projekty.

Visual Studio pro Mac nabízí mnoho výkonné funkce, aby vývoj pro různé platformy jako přístupné a co nejužitečnější. Následující části popisují některé z světla.

## <a name="code-folding"></a>Skládání kódu

Skládání kód usnadňuje vývojářům můžete zobrazit nebo skrýt dokončení části kódu, například pomocí direktivy, často používaný kód a komentářů a příkazy #region spravovat soubory velké zdrojového kódu. Skládání kód je ve výchozím nastavení vypnuté v sadě Visual Studio pro Mac

Chcete-li zapnout skládání kód, přejděte na **Visual Studio > Předvolby... > textový Editor > Obecné > skládání kód**:

![Kód skládání možnosti](media/source-editor-image1.png)

Tato nabídka také zahrnuje možnost fold #regions a komentáře ve výchozím zobrazení s názvem pomocného parametru, místo kódu.

Pokud chcete zobrazit nebo skrýt oddíly, použijte widget zpřístupnění vedle číslo řádku:

 ![Zobrazit nebo skrýt oddíly v kódu](media/source-editor-image2.png)

Můžete také přepínat mezi zobrazení a skrytí složení pomocí **zobrazení > skládání > Fold – přepínač / přepněte všechny složení** položky nabídky:

 ![Skládání položky nabídky](media/source-editor-image19.png)

Tuto položku nabídky lze také chcete povolit nebo zakázat skládání kódu.

## <a name="white-space"></a>Prázdné znaky

Může být nutné pro vás k zobrazení neviditelná znaků ve zdrojovém kódu. Je viditelná způsob, jak se ujistěte, že jste dodržujte kódování standardů a plýtvání není zbytečnému místa. Je také užitečné při zápisu F #, což závisí na přesněji odsazené řádky pro vyhodnocení kódu.

Nastavení možností zobrazíte prázdné přechodem na **Visual Studio > Předvolby > textový Editor > značek a pravítek**. Výběrem této možnosti povolíte nastavení _při_ neviditelná znaků se zobrazí: Nikdy, na výběr, nebo vždy:

 ![Zobrazit možnosti neviditelná znaků](media/source-editor-image3.png)

K dispozici je také možnost Zobrazit karty, mezery a konce řádků:

 ![Zobrazit karty a prostory](media/source-editor-image4.png)

 Neviditelná znaky jsou zobrazeny jako šedé tečky, jak je znázorněno na následujícím obrázku:

 ![zobrazí prázdné znaky](media/source-editor-image22.png)

## <a name="ruler"></a>Pravítko

Sloupec pravítka jsou užitečné pro určení řádku délky, zejména při práci na tým, který obsahuje pokynů délka řádku. Sloupec pravítka může být zapnout nebo vypnout tak, že přejdete do **Visual Studio > Předvolby... > textový Editor > značek a pravítek** a vyberete (nebo zrušením výběru) **pravítka zobrazit sloupec**, jak je popsáno v na následujícím obrázku:

 ![Dialogové okno Předvolby s "Zobrazit sloupce pravítka" zvýrazněná](media/source-editor-image5.png)

 Zobrazí se jako světla šedé svislice v editoru zdroje.

## <a name="highlight-identifier-references"></a>Zvýrazněte identifikátor odkazy

"Zvýraznění identifikátor odkazy" je povolena možnost můžete vybrat libovolný symbol ve zdrojovém kódu a zdroj editor bude na poskytovat visual průvodce všechny odkazy v tomto souboru. Chcete-li tuto možnost zapnout, přejděte na **Visual Studio > Předvolby... > textový Editor > značek a pravítek** a vyberte _zvýrazněte identifikátor odkazy_, jak je znázorněno na následujícím obrázku:

![Dialogové okno Předvolby s "Zvýraznění identifikátor odkazy" zvýrazněná](media/source-editor-image6.png)

Barva zvýraznění je také užitečné, pro které označuje, že něco je probíhá přiřazené nebo je odkazované. Pokud je přiřazen něco, ho se zobrazí červeně; Pokud se odkazuje, je modře zvýrazněný:

![Příklad zobrazuje barva higlight](media/source-editor-image7.png)