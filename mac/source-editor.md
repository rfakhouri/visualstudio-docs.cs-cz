---
title: Editor zdroje | Microsoft Docs
description: "Pomocí editoru zdroje v sadě Visual Studio pro Mac"
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: A018A314-C1C4-4F36-BCB6-2D434208FCFE
ms.openlocfilehash: f52e60c0ade8cebc78b3408b4ef81ef85fcd767b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="source-editor"></a>Editor zdrojového kódu

Editor spolehlivý zdroj je nezbytné pro psaní kódu stručně a efektivně. Visual Studio pro Mac poskytuje sofistikované zdroj editor, který je v centru vaši interakci s rozhraní IDE. Editor zdroj poskytuje funkce, které můžete očekávat a potřebují k práci s snadné: Z základy takové zvýraznění syntaxe, fragmenty kódu a kódu skládání, výhod integrace kompilátoru jeho Roslyn, jako je plně funkční IntelliSense kódu dokončení.

Editor zdrojového kódu v sadě Visual Studio pro Mac umožňuje jednotné prostředí s všechny další funkce poskytované službou IDE, jako je například ladění, refaktoring a integraci správy verzí.

Toto téma uvádí některé klíčové funkce editoru zdroje a popisuje, jak Visual Studio pro Mac můžete být stejně produktivní, jako je to možné.

## <a name="the-source-editor-experience"></a>Editor zdrojové prostředí

Zobrazení a efektivně přesunutí v rámci kódu je nedílnou součástí pracovní postup vývoje. Jakým způsobem se rozhodnete zobrazit a spravovat, že kód je osobní rozhodnutí, které se liší mezi vývojáři - a často mezi projekty.

Visual Studio pro Mac nabízí mnoho výkonné funkce, aby vývoj pro různé platformy jako přístupné a co nejužitečnější. Následující oddíly popisují některé z světla.


### <a name="code-folding"></a>Skládání kódu

Skládání kód usnadňuje vývojářům můžete zobrazit nebo skrýt dokončení části kódu, například pomocí direktivy, často používaný kód a komentářů a příkazy #region spravovat soubory velké zdrojového kódu. To je ve výchozím nastavení v sadě Visual Studio vypnuté pro Mac

Chcete-li zapnout skládání kód, přejděte na **Visual Studio > Předvolby... > textový Editor > Obecné > skládání kód**:

![Kód skládání možnosti](media/source-editor-image1.png)

Kromě poskytuje možnost Povolit kód skládání, tato nabídka také zahrnuje možnost fold #regions a komentáře ve výchozím zobrazení s názvem pomocného parametru, místo kódu.

Pokud chcete zobrazit nebo skrýt oddíly, použijte widget zpřístupnění vedle číslo řádku:

 ![Zobrazit nebo skrýt oddíly v kódu](media/source-editor-image2.png)

Můžete také přepínat mezi zobrazení a skrytí složení pomocí **zobrazení > skládání > Fold – přepínač / přepněte všechny složení** položky nabídky:

 ![Skládání položky nabídky](media/source-editor-image19.png)

Tuto položku nabídky lze také chcete povolit nebo zakázat skládání kódu.

### <a name="white-space"></a>Prázdné znaky

Může být nutné, abyste mohli zobrazit neviditelná znaků ve zdrojovém kódu. Je viditelná způsob, jak zajistit, že jsou splněny kódování standardů a plýtvání není zbytečnému místa. Je také velmi užitečné při zápisu F #, což závisí na přesněji odsazené řádky pro vyhodnocení kódu.

Nastavení možností zobrazíte prázdné přechodem na **Visual Studio > Předvolby > textový Editor > značek a pravítek**, jak je uvedeno dále. Výběrem této možnosti povolíte nastavení _při_ neviditelná znaků se zobrazí: Nikdy, na výběr, nebo vždy:

 ![Zobrazit možnosti neviditelná znaků](media/source-editor-image3.png)

K dispozici je také možnost Zobrazit karty, mezery a konce řádků:

 ![Zobrazit karty a prostory](media/source-editor-image4.png)

 Neviditelná znaky jsou zobrazeny jako šedé tečky, jak je uvedeno dále:

 ![zobrazí prázdné znaky](media/source-editor-image22.png)


### <a name="ruler"></a>Pravítko

Zobrazuje sloupec pravítka jsou užitečné pro určení řádku délky, zejména při práci na tým, který obsahuje pokynů délka řádku. Sloupec pravítka může být zapnout nebo vypnout tak, že přejdete do **Visual Studio > Předvolby... > textový Editor > značek a pravítek** a vyberete (nebo zrušením výběru) **pravítka zobrazit sloupec**, jak je popsáno níže:

 ![](media/source-editor-image5.png)

 Zobrazí se jako světla šedé svislice v editoru zdroje.


### <a name="highlight-identifier-references"></a>Zvýrazněte identifikátor odkazy

Pokud je tato možnost zapnutá, vývojáři mohou nastavovat myší na všechny symbol ve zdrojovém kódu a zdroj editor bude na poskytovat visual průvodce všechny odkazy v tomto souboru. To je zapnutá přechodem na **Visual Studio > Předvolby... > textový Editor > značek a pravítek** a výběrem _zvýrazněte identifikátor odkazy_, jak je uvedeno dále:

![](media/source-editor-image6.png)

Barva zvýraznění je také užitečné, pro které označuje, že něco je probíhá přiřazené nebo je odkazované. Pokud je přiřazen něco, ho se zobrazí červeně; Pokud se odkazuje, je modře zvýrazněný:

![](media/source-editor-image7.png)



