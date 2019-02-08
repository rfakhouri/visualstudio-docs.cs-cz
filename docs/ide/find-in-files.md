---
title: Najít v souborech
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.findreplace.findinfiles
- vs.findinfiles
helpviewer_keywords:
- objects [Visual Studio], finding
- text searches, replacing text
- objects [Visual Studio], searching for
- Find and Replace window, Find in Files tab
- text searches, Find and Replace window
- documents, searching
- files, searching
- Find in Files tab, Find and Replace window
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1247bae6193294667953376f7e86c42cf5b8f8a8
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55952954"
---
# <a name="find-in-files"></a>Najít v souborech

**Najít v souborech** umožňuje vyhledávat zadané sady souborů. Nalezených shod a akcí provedených jsou uvedeny v **výsledky hledání** vybraný v interval **způsobit možnosti**.

Můžete použít některý z následujících metod k zobrazení **najít v souborech** v **najít a nahradit** okna.

## <a name="to-display-find-in-files"></a>Chcete-li zobrazit najít v souborech

1. V panelu nabídky zvolte **upravit** > **najít a nahradit**.

1. Zvolte **najít v souborech**.

Chcete-li zrušit operaci hledání, stiskněte **Ctrl** + **přerušit**.

> [!NOTE]
> Nástroj Najít a nahradit neprohledává adresáře s `Hidden` nebo `System` atribut.

## <a name="find-what"></a>Najít

K vyhledání nový textový řetězec nebo výraz, zadejte do pole. Chcete-li vyhledávat libovolné 20 řetězců, které jste hledali naposledy, otevřete rozevírací seznam a zvolte řetězec. Zvolte sousedních **Tvůrce výrazů** tlačítko, pokud chcete použít jeden nebo více regulární výrazy ve vyhledávaném řetězci. Další informace najdete v tématu [pomocí regulárních výrazů v sadě Visual Studio](../ide/using-regular-expressions-in-visual-studio.md).

> [!NOTE]
> **Tvůrce výrazů** tlačítko bude povoleno pouze pokud jste vybrali **pomocí regulárních výrazů** pod **možnosti hledání**.

## <a name="look-in"></a>Oblast hledání

Možnost výběru z **Hledat v** rozevíracího seznamu určuje, zda **najít v souborech** prohledávání pouze v aktuálně aktivních souborů nebo ve všech souborech se ukládají v určitých složkách. Obor vyhledávání vyberte ze seznamu nebo klikněte na tlačítko **Procházet (...)**  tlačítka pro zobrazení **zvolit složky pro hledání** dialogové okno a zadat vlastní sadu adresáře. Můžete také zadat přímo do cesty **Hledat v** pole.

> [!WARNING]
> S **celé řešení** nebo **aktuální projekt** možnosti, projektu a řešení soubory nebudou vyhledány. Pokud chcete vyhledat v souborech projektu, zvolte složku výsledků hledání.

> [!NOTE]
> Pokud **Hledat v** zaškrtnutou možnost způsobí, že vám umožní vyhledávat soubor, který jste rezervovali ve správě zdrojového kódu, je prohledána pouze verze tohoto souboru, který byl stažen do místního počítače.

## <a name="include-subfolders"></a>Zahrnout podsložky

Určuje této podsložky **Hledat v** prohledá složku.

## <a name="find-options"></a>Možnosti hledání

Můžete rozbalit nebo sbalit **možnosti hledání** oddílu. Následující možnosti můžete vybrané nebo zrušeno:

**Rozlišovat velikost písmen**

Pokud je vybráno, **výsledky hledání** hledání bude malá a velká písmena

**Pouze celá slova**

Pokud je vybráno, **výsledky hledání** windows vrátí pouze celá slova shody.

**Používání regulárních výrazů**

Pokud je toto políčko zaškrtnuto, můžete použít speciální zápisy k definování vzorků text tak, aby odpovídaly v **najít** nebo **nahraďte** textová pole. Seznam těchto zápisy najdete v tématu [pomocí regulárních výrazů v sadě Visual Studio](../ide/using-regular-expressions-in-visual-studio.md).

**Podívejte se na tyto typy souborů**

Tento seznam uvádí typy souborů pro hledání prostřednictvím v **Hledat v** adresáře. Pokud je toto pole prázdné, všechny soubory v **Hledat v** budou prohledány adresáře.

Vyberte libovolnou položku v seznamu a zadejte předkonfigurované vyhledávací řetězec, který najdete tyto konkrétní typy souborů.

## <a name="result-options"></a>Možnosti výsledků

Můžete rozbalit nebo sbalit **způsobit možnosti** oddílu. Následující možnosti můžete vybrané nebo zrušeno:

**Najít výsledky 1 okno**

Pokud je vybráno, výsledky aktuální hledání nahradí obsah **Najít výsledky 1** okna. Toto okno se automaticky otevře a zobrazí výsledky hledání. Ručně otevřete toto okno, vyberte **ostatní Windows** z **zobrazení** nabídku a zvolte **Najít výsledky 1**.

**Najít výsledky 2 okno**

Pokud je vybráno, výsledky aktuální hledání nahradí obsah **Najít výsledky 2** okna. Toto okno se automaticky otevře a zobrazí výsledky hledání. Ručně otevřete toto okno, vyberte **ostatní Windows** z **zobrazení** nabídku a zvolte **Najít výsledky 2**.

**Zobrazit pouze názvy souborů**

Zobrazí seznam souborů obsahující vyhledávání odpovídá místo zobrazení hledání odpovídá sami.

**Připojit výsledky**

Připojí výsledky hledání na předchozí výsledky hledání.

## <a name="see-also"></a>Viz také:

- [Hledání a nahrazení textu](../ide/finding-and-replacing-text.md)
- [Nahradit v souborech](../ide/replace-in-files.md)
- [Příkazy sady Visual Studio](../ide/reference/visual-studio-commands.md)