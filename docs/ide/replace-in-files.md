---
title: Visual Studio najít a nahradit v souborech
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.findreplace.replaceinfiles
- vs.replaceinfiles
helpviewer_keywords:
- text searches, replacing text
- find and replace
- replace in files
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b6d1a59e3e07120e01fa7757b53b71833a7bc09c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="replace-in-files"></a>Nahradit v souborech

**Nahradit v souborech** umožňuje hledat kód zadanou sadu souborů pro řetězec nebo výraz a změnit některé nebo všechny nalezených shod. Nebyla nalezena shoda a akcí provedených jsou uvedeny v **Najít výsledky** vybrán v okně **způsobit možnosti**.

> [!NOTE]
> Dialogová okna a příkazy nabídky se zobrazí se mohou lišit od těch popsaných v **pomoci** v závislosti na aktivním nastavení nebo edici. Chcete-li změnit nastavení, například k **Obecné** nebo **Visual C++** nastavení, vyberte **nástroje** > **nastavení importu a exportu**a potom zvolte **obnovit nastavení**.

K zobrazení můžete použít některou z následujících metod **nahradit v souborech** v **najít a nahradit** okno.

## <a name="to-display-replace-in-files"></a>Chcete-li zobrazit nahradit v souborech

1. Na **upravit** nabídky, rozbalte položku **najít a nahradit**.

1. Zvolte **nahradit v souborech**.

   – nebo –

  Pokud **najít a nahradit** , je již otevřeno, na panelu nástrojů vyberte **nahradit v souborech**.

## <a name="find-what"></a>Najít

Vyhledat nový textový řetězec nebo výraz, zadejte do pole. Chcete-li vyhledávat libovolné 20 řetězce, které jste hledali naposledy, otevřete rozevírací seznam a zvolte řetězec. Zvolte sousedním **Tvůrce** tlačítko, pokud chcete použít jeden nebo více regulární výrazy v hledanému řetězci. Další informace najdete v tématu [použití regulárních výrazů v sadě Visual Studio](../ide/using-regular-expressions-in-visual-studio.md).

> [!NOTE]
> **Tvůrce** tlačítko bude povoleno pouze pokud jste vybrali **pomocí regulárních výrazů** pod **najít možnosti**.

## <a name="replace-with"></a>Nahraďte

Nahradit instance řetězce do **najít** pole s jiným řetězcem, zadejte náhradní řetězec v **nahradit za** pole. Odstranění instance řetězce do **najít** pole, to pole ponechat prázdné. Otevřete seznamu zobrazíte 20 řetězců, pro které jste naposledy vyhledávat. Zvolte sousedním **Tvůrce** tlačítko, pokud chcete použít jeden nebo více regulární výrazy v náhradní řetězec. Další informace najdete v tématu [použití regulárních výrazů v sadě Visual Studio](../ide/using-regular-expressions-in-visual-studio.md).

## <a name="look-in"></a>Oblast hledání

Možnost výběru z **naleznete v** rozevíracího seznamu určuje, zda **nahradit v souborech** vyhledá pouze v aktuálně aktivních soubory nebo vyhledá všechny soubory uložené v rámci určitých složek. Vyberte ze seznamu obor vyhledávání, zadejte cestu ke složce nebo klikněte na **Procházet (...)**  tlačítko pro zobrazení **zvolte složky výsledků hledání** dialogové okno pole a zvolte skupinu složek, které chcete vyhledat. Můžete také zadat cestu přímo do **Hledat v** pole.

> [!NOTE]
> Pokud **Hledat v** možnost způsobí, že jste k vyhledání souboru, který máte rezervován od správy zdrojového kódu, prohledají se jenom verze tohoto souboru, který byl stažen do místního počítače.

## <a name="find-options"></a>Možnosti hledání

Můžete rozbalit nebo sbalit **najít možnosti** části. Následující možnosti může být vybrána nebo vymazána:

**Malá a velká písmena**

Při výběru, **výsledky hledání** windows zobrazí pouze instance **najít** řetězec, který se splní podle obsahu a podle případu. Například vyhledejte "MyObject" s **malá a velká písmena** vybrané bude vracet "MyObject", ale ne "myobject" nebo "MYOBJECT."

**Celá slova**

Při výběru, **Najít výsledky** windows zobrazí pouze instance **najít** řetězec, který se splní v celá slova. Například vyhledejte "MyObject" vrátí "MyObject", ale ne "CMyObject" nebo "MyObjectC."

**Používání regulárních výrazů**

Když toto políčko zaškrtnuto, můžete použít speciální zápisy definovat strukturu textu v **najít** nebo **nahraďte** textových polí. Seznam těchto zápisy, naleznete v části [použití regulárních výrazů v sadě Visual Studio](../ide/using-regular-expressions-in-visual-studio.md).

**Podívejte se na tyto typy souborů**

Tento seznam uvádí typy souborů, pokud chcete hledat v **Hledat v** adresáře. Pokud toto pole ponecháte prázdné, všechny soubory v **Hledat v** prohledávaných adresářů. Vyberte libovolnou položku v seznamu a zadejte předkonfigurované vyhledávací řetězec, který zjistí tyto konkrétní typy souborů.

## <a name="result-options"></a>Možnosti výsledku

Můžete rozbalit nebo sbalit **způsobit možnosti** části. Následující možnosti může být vybrána nebo vymazána:

**Najít výsledky 1** okna

Pokud vybraná, výsledky hledání aktuální nahradí obsah **najít 1 výsledky** okno. Toto okno se automaticky otevře a zobrazí výsledky hledání. Otevřete toto okno ručně, vyberte **ostatní okna** z **zobrazení** nabídky a zvolte **najít 1 výsledky**.

**Najít výsledky 2** okna

Pokud vybraná, výsledky hledání aktuální nahradí obsah **najít 2 výsledky** okno. Toto okno se automaticky otevře a zobrazí výsledky hledání. Otevřete toto okno ručně, vyberte **ostatní okna** z **zobrazení** nabídky a zvolte **najít 2 výsledky**.

**Zobrazit pouze názvy souborů**

Když toto políčko zaškrtnuto, **Najít výsledky** windows seznamu úplné názvů a cest pro všechny soubory, které obsahují řetězec pro hledání. Ale výsledky neobsahují řádek kódu, kde se zobrazí řetězec. Toto zaškrtávací políčko je dostupné pro **hledání v souborech** pouze.

**Nechte změněné soubory otevřené po Replace všechny**

Při výběru, otevřete všechny soubory zůstanou ve kterých náhrady byly provedeny, abyste mohli vrátit zpět nebo uložte změny. Omezení paměti může být omezen počet souborů, které může zůstat otevřené po operaci nahrazení.

> [!CAUTION]
> Můžete použít **vrátit zpět** pouze u souborů, které zůstávají otevřený pro úpravy. Pokud tuto možnost nevyberete, soubory, které už nebyly otevřete pro úpravy zůstanou uzavřené a ne **vrátit zpět** možnost nebude k dispozici v těchto souborů.

## <a name="see-also"></a>Viz také

- [Najít a nahradit text](../ide/finding-and-replacing-text.md)
- [Hledání v souborech](../ide/find-in-files.md)
- [Příkazy sady Visual Studio](../ide/reference/visual-studio-commands.md)
