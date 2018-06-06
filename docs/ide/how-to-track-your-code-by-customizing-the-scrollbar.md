---
title: 'Postupy: přizpůsobení posuvník sledují kódu'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bc18b436a7f25baad9870e36c3224f23de920241
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34745734"
---
# <a name="how-to-track-your-code-by-customizing-the-scrollbar"></a>Postupy: přizpůsobení posuvník sledují kódu

Při práci se soubory dlouho kódu, může být obtížné všechno mějte na paměti. Můžete přizpůsobit posuvníku okna kód tak, abyste získali pohled z ptačí perspektivy co se děje ve vašem kódu.

## <a name="to-show-annotations-on-the-scroll-bar"></a>Chcete-li zobrazit poznámky na posuvníku

1. Posuvník můžete nastavit pro zobrazení změn kódu, zarážky, chyb a záložky.

    Otevřete **posuvníku** stránka Možnosti výběrem **nástroje** > **možnosti** > **textového editoru**  >  **Všechny jazyky** nebo konkrétní jazyk, nebo zadáním **posuvníku** v **Snadné spuštění** okno.

2. Vyberte **zobrazit poznámky přes svislý posuvník**, pak vybrat poznámky, které chcete zobrazit.

    **Značky** zahrnuje možnost zarážky a záložky.

3. Nyní vyzkoušejte ji. Otevřete soubor velké kód a nahraďte něco, co dojde na několika místech v souboru. Posuvník ukazuje účinku nahrazení, tak můžete zálohovat na změny, pokud je něco, co by nemělo být nahrazen.

    Zde je, jak vypadá posuvníku po hledání řetězce. Všimněte si, že se zobrazují všechny instance řetězce.

    ![Posuvník po hledání řetězce.](../ide/media/enhancedscrollbarsearch.png)

    Zde je posuvníku po nahrazení všechny instance řetězce. Můžete zobrazit okamžitě, že operace nezdařila z důvodu některé problémy.

    ![Scrollbar po nahrazení řetězec s chybami](../ide/media/enhancedscrollbarreplace.png)

## <a name="to-set-the-display-mode-for-the-scroll-bar"></a>Chcete-li nastavit režim zobrazení pro posuvník

1. Posuvník obsahuje dva režimy: panel režim (výchozí) a režim mapy. Panelu režimu jenom zobrazí indikátory poznámky na posuvníku. V režimu mapy řádky kódu uváděny na posuvníku. Můžete zvolit jsou jak široké a zda jejich kódu zobrazit při přesunutí ukazatele myši na ně. Když kliknete na panelu přejděte do umístění, kurzor se přesune do tohoto umístění v kódu. Sbalené oblasti jsou zobrazena šedě jinak; stavu rozbalení poklepáním na nich.

    Na **posuvníku** možnosti vyberte buď **použití panelu režim pro svislý posuvník** nebo **Map použití režimu pro svislý posuvník**. Šířka v můžete **zdroj přehled** rozevíracího seznamu.

    Zde je, jak vypadá v příkladu vyhledávání map režim je na a šířka je nastavena na **střední**:

    ![Posuvník v režimu mapy](../ide/media/enhancedscrollbar.png)

2. V režimu mapy, chcete-li verze Preview kódu při přesunutí ukazatele nahoru a dolů posuvníku, vyberte **zobrazit náhled popisek** možnost. Zde je, jak vypadá:

    ![Posuvník s popisek](../ide/media/enhancedscrollbarsearchtooltip.png)

    Pokud chcete zachovat režimu mapy posouvání chování a popisek preview, ale nechcete, aby zobrazíte Přehled zdrojového kódu, můžete nastavit **zdroj přehled** k **vypnout**.

## <a name="see-also"></a>Viz také:

- [Funkce editoru kódu](../ide/writing-code-in-the-code-and-text-editor.md)