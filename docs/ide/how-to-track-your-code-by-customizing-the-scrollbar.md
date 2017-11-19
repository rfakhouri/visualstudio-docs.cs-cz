---
title: "Postupy: přizpůsobení posuvník sledují kódu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a9ebe7ec-4b6f-4ba2-a79e-80fab3db485b
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e6dd6eab2d607d059967e89030ae92d34b407ff1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-track-your-code-by-customizing-the-scrollbar"></a>Postupy: přizpůsobení posuvník sledují kódu
Při práci se soubory dlouho kódu, může být obtížné všechno mějte na paměti. Můžete přizpůsobit posuvníku okna kód tak, abyste získali pohled z ptačí perspektivy co se děje ve vašem kódu.  
  
### <a name="to-show-annotations-on-the-scroll-bar"></a>Chcete-li zobrazit poznámky na posuvníku  
  
1.  Posuvník můžete nastavit pro zobrazení změn kódu, zarážky, chyb a záložky.  
  
     Otevřete **posuvníku** stránka Možnosti (**nástroje, Možnosti textového editoru. Všechny jazyky** nebo na konkrétní jazyk, nebo typ **posuvníku** v okně Snadné spuštění).  
  
2.  Vyberte **zobrazit poznámky přes svislý posuvník**, pak vybrat poznámky, které chcete zobrazit. ( **Značky** zahrnuje možnost zarážky a záložky.)  
  
3.  Nyní vyzkoušejte ji. Otevřete soubor velké kód a nahraďte něco, co dojde na několika místech v souboru. Posuvník ukazuje účinku nahrazení, tak můžete zálohovat na změny, pokud je něco, co by nemělo být nahrazen.  
  
     Zde je, jak vypadá posuvníku po hledání řetězce. Všimněte si, že se zobrazují všechny instance řetězce.  
  
     ![Posuvník po hledání řetězce. ] (../ide/media/enhancedscrollbarsearch.png "EnhancedScrollbarSearch")  
  
     Zde je posuvníku po nahrazení všechny instance řetězce. Můžete zobrazit okamžitě, že operace nezdařila z důvodu některé problémy.  
  
     ![Scrollbar po nahrazení řetězec s chybami](../ide/media/enhancedscrollbarreplace.png "EnhancedScrollbarReplace")  
  
### <a name="to-set-the-display-mode-for-the-scroll-bar"></a>Chcete-li nastavit režim zobrazení pro posuvník  
  
1.  Posuvník má dva režimy, režimu panelu (výchozí) a režim mapy. Panelu režimu jenom zobrazí indikátory poznámky na posuvníku. V režimu mapy řádky kódu uváděny na posuvníku. Můžete zvolit jsou jak široké a zda jejich kódu zobrazit při přesunutí ukazatele myši na ně. Když kliknete na panelu přejděte do umístění, kurzor se přesune do tohoto umístění v kódu. Sbalené oblasti jsou zobrazena šedě jinak; stavu rozbalení poklepáním na nich.  
  
     Na **posuvníku** možnosti vyberte buď **použití panelu režim pro svislý posuvník** nebo **Map použití režimu pro svislý posuvník**. Můžete zvolit šířka v **zdroj přehled** rozevíracího seznamu.  
  
     Zde je, jak vypadá v příkladu vyhledávání když je režim mapy na a šířka je nastavena na hodnotu Střední:  
  
     ![Posuvník v režimu mapy](../ide/media/enhancedscrollbar.png "EnhancedScrollbar")  
  
2.  V režimu mapy, chcete-li verze Preview kódu při přesunutí ukazatele nahoru a dolů posuvníku, vyberte **zobrazit náhled popisek** možnost. Zde je, jak vypadá:  
  
     ![Posuvník s popisek](../ide/media/enhancedscrollbarsearchtooltip.png "EnhancedScrollbarSearchTooltip")  
  
     Pokud chcete zachovat režimu mapy posouvání chování a popisek preview, ale nechcete, aby zobrazíte Přehled zdrojového kódu, můžete nastavit **zdroj přehled** k **vypnout**.