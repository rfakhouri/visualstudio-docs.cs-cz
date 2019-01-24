---
title: 'Postupy: Sledování kódu přizpůsobením posuvníku | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: a9ebe7ec-4b6f-4ba2-a79e-80fab3db485b
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 11df0e3ca4e8b9c814bf91735d48bb091c711068
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54788203"
---
# <a name="how-to-track-your-code-by-customizing-the-scrollbar"></a>Postupy: Sledování kódu přizpůsobením posuvníku
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Při práci se soubory kódu dlouho, může být obtížné všechno, co brát v úvahu. Můžete upravit posuvník rohu okna kódu vám pohled z ptačí perspektivy co se děje ve vašem kódu.  
  
### <a name="to-show-annotations-on-the-scroll-bar"></a>Chcete-li zobrazit poznámky na posuvníku  
  
1.  Můžete nastavit posuvník pro zobrazení změn kódu, zarážky, chyby a záložky.  
  
     Otevřít **posuvník** stránka možností (**nástroje, Možnosti textového editoru. Všechny jazyky** nebo konkrétní jazyk, nebo typ **posuvník** v okně Snadné spuštění).  
  
2.  Vyberte **zobrazit poznámky přes svislý posuvník**, pak vybrat poznámky, které chcete zobrazit. ( **Značky** možnost obsahuje zarážky a záložky.)  
  
3.  Nyní vyzkoušejte. Otevřete soubor kódu a nahraďte něco, ke které dochází na několika místech v souboru. Posuvník demonstruje účinek nahrazení, tak si změny můžete zálohovat, pokud něco, co by nemělo být nahrazen.  
  
     Tady je vzhled posuvníku po hledání řetězce. Všimněte si, že se zobrazují všechny instance řetězce.  
  
     ![Posuvník po vyhledání řetězce. ](../ide/media/enhancedscrollbarsearch.png "EnhancedScrollbarSearch")  
  
     Tady je posuvník po nahrazení všechny instance řetězce. Můžete zobrazit okamžitě, že operace způsobila některé problémy.  
  
     ![Posuvník po nahrazení řetězce s chybami](../ide/media/enhancedscrollbarreplace.png "EnhancedScrollbarReplace")  
  
### <a name="to-set-the-display-mode-for-the-scroll-bar"></a>Chcete-li nastavit režim zobrazení pro posuvník  
  
1.  Posuvník má dva režimy, režimu panelu (výchozí) a režim mapování. Panel režimu pouze zobrazuje indikátory poznámky na posuvníku. V režimu mapování jsou reprezentovány řádky kódu na posuvníku. Můžete zvolit jsou jak široké a určuje, zda se zobrazí základního kódu při přesunutí ukazatele myši na ně. Po kliknutí na umístění na posuvníku, kurzor se přesune do tohoto umístění v kódu. Sbalených oblasti jsou jinak; označeno šedou barvou jsou rozbaleny při dvojitém kliknutí na ně.  
  
     Na **posuvník** možnosti stránky, vyberte buď možnost **režim panel použijte pro svislý posuvník** nebo **režim použít mapování pro svislý posuvník**. Můžete zvolit požadovanou šířku v **hled zdrojů** rozevíracího seznamu.  
  
     Zde je, jak vypadá příklad prohledávání je zapnut režim mapování a je nastavena šířku střední:  
  
     ![Posuvník v režimu mapy](../ide/media/enhancedscrollbar.png "EnhancedScrollbar")  
  
2.  V režimu Mapa k povolení verze Preview kódu při přesunutí kurzoru nahoru a dolů posuvníku, vyberte **zobrazení popisu tlačítka ve verzi Preview** možnost. Zde je, jak bude vypadat:  
  
     ![Posuvník s popisem](../ide/media/enhancedscrollbarsearchtooltip.png "EnhancedScrollbarSearchTooltip")  
  
     Pokud chcete zachovat mapy režim posouvání chování a popisu tlačítka ve verzi preview, ale nechcete zobrazit přehled zdrojového kódu, můžete nastavit **hled zdrojů** k **vypnout**.
