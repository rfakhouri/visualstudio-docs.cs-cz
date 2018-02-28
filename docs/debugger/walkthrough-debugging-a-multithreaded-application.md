---
title: "Zobrazení vláken v ladicím programu | Microsoft Docs"
ms.custom: 
ms.date: 04/25/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.threads
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- threading [Visual Studio], debugging
- Thread.Name property
- debugger, Threads window
- SetThreadName function
- Threads window
- '@TIB'
- debugging [Visual Studio], threads
ms.assetid: 590ffd57-0556-43d8-8962-ee27e5b2b7d7
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: bde9f1c8aa09f8e5961bd228a5f1947c2fc30f82
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="view-threads-in-the-debugger-in-visual-studio-using-the-threads-window"></a>Zobrazení vláken v ladicím programu v sadě Visual Studio pomocí okna vláken
V **vláken** okně můžete prozkoumat a práce s vlákny v aplikaci, kterou ladíte. Podrobné pokyny k použití **vláken** okně najdete v části [návod: ladění pomocí okna vláken](../debugger/how-to-use-the-threads-window.md).
  
 **Vláken** okno obsahuje tabulku, kde každý řádek představuje vlákno v aplikaci. Ve výchozím nastavení v tabulce jsou uvedeny všechny vláken ve vaší aplikaci, ale můžete filtrovat na seznamu a zobrazit pouze vláken, které vás zajímají. Každý sloupec obsahuje jiný typ informací. Můžete také skrýt některé sloupce. Pokud chcete zobrazovat všechny sloupce, tyto informace se zobrazí, zprava doleva:  
  
-   Příznak sloupec, kde můžete označit vlákno, do kterého chcete věnujte zvláštní pozornost. Informace o tom, jak příznak vlákno najdete v tématu [postup: Příznak a odstranění označení vlákna](../debugger/how-to-flag-and-unflag-threads.md).  
  
-   Aktuální vlákno sloupec, ve kterém žlutá šipka označuje aktuální vlákno (Přehled šipku indikuje aktuální kontextu ladicího programu pro jiný aktuální vlákno).
  
-   **ID** sloupec, který obsahuje identifikační číslo pro každé vlákno.  
  
-   **Spravované ID** sloupec, který obsahuje spravované identifikační čísla pro spravovaných vláknech.  
  
-   **Kategorie** sloupec, který rozděluje vláken jako vlákna uživatelského rozhraní, obslužné rutiny volání vzdálených procedur nebo pracovních vláken. Speciální kategorie identifikuje hlavního vlákna aplikace.  
  
-   **Název** sloupce, které identifikují každé vlákno podle názvu, pokud má jedna nebo jako \<ne Name >.  
  
-   **Umístění** sloupce, které ukazuje, kde vlákno je spuštěno. Můžete rozbalit tohoto umístění zobrazíte zásobníku volání úplné pro vlákno.  
  
-   **s prioritou** sloupec, který obsahuje priority nebo přednost, které systém přiřadil každé vlákno.  
  
-   **Maska spřažení** sloupců, což je sloupec pokročilé (obvykle skryté). Tento sloupec zobrazuje masky spřažení procesoru pro každé vlákno. V víceprocesorový systém Určuje Maska spřažení procesorů, které ve kterých lze spustit vlákno.  
  
-   **Pozastaveno počet** sloupec (obvykle skryté), který obsahuje počet pozastavený a je obvykle skrytá. Tento počet Určuje, jestli se může spustit vlákno. Vysvětlení počtu pozastavený najdete v části "Zmrazení a uvolnění vlákna" dál v tomto tématu.  
  
-   **Název procesu** sloupec (obvykle skryté), který obsahuje procesu, ke kterému patří každé vlákno. Tento sloupec může být užitečné při ladění více procesů.  
  
### <a name="to-display-the-threads-window-in-break-mode-or-run-mode"></a>Pro zobrazení okna vláken v režimu pozastavení nebo spuštění  
  
-   Při ladění, vyberte **ladění** nabídky, přejděte na příkaz **Windows**a potom klikněte na **vláken**.  
  
### <a name="to-display-or-hide-a-column"></a>Chcete-li zobrazit nebo skrýt sloupce  
  
-   Na panelu nástrojů v horní části **vláken** okně klikněte na tlačítko **sloupce**, zaškrtněte nebo zrušte název sloupce, který chcete zobrazit nebo skrýt.    

## <a name="display-flagged-threads"></a>Zobrazit označení vlákna  
 Můžete označit příznakem vlákno, které chcete udělit zvláštní pozornost označením ikonou v **vláken** okno. Další informace najdete v tématu [postup: Příznak a odstranění označení vlákna](../debugger/how-to-flag-and-unflag-threads.md). V **vláken** okno můžete zobrazit všechna vlákna nebo pouze označení vlákna.  
  
#### <a name="to-display-only-flagged-threads"></a>Chcete-li zobrazit pouze označení vlákna  
  
-   Vyberte **zobrazit příznakem vláken pouze** tlačítka v horní části **vláken** okno. (Pokud je zobrazeno šedě, budete muset příznak některé vláken nejprve.) 

## <a name="freeze-and-thaw-threads"></a>Ukotvení a odblokování vláken  
 Po ukotvení vlákno se systém nespustí provádění vlákna, i když jsou k dispozici prostředky.  
  
 V nativním kódu, pozastavit nebo obnovit vláken voláním funkce Windows `SuspendThread` a `ResumeThread` nebo funkce MFC [CWinThread::SuspendThread](/cpp/mfc/reference/CWinThread-class.md#cwinthread__suspendthread) a [CWinThread::ResumeThread](/cpp/mfc/reference/CWinThread-class.md#cwinthread__resumethread). Při volání `SuspendThread` nebo `ResumeThread`, můžete změnit *pozastaveno počet*, který se objevuje v **vláken** okno. Ale pokud zablokování nebo odblokování nativní vlákno, nezměníte pozastavenou count. V nativním kódu vlákna nelze provést, pokud je roztát a má pozastavenou nulový počet.  
  
 Ve spravovaném kódu změňte pozastavenou počet zmrazení nebo uvolnění vlákna. Ukotvené vlákna ve spravovaném kódu má pozastavenou počet 1. Ukotvené vlákna v nativním kódu má pozastavenou počet 0, pokud pozastavily vlákno `SuspendThread` volání.  
  
> [!NOTE]
>  Při ladění volání z nativní kód do spravovaného kódu, spravovaný kód běží ve stejné fyzické vlákna v nativním kódu, která je volána. Pozastavení nebo zmrazení nativní vlákno se taky zablokuje spravovaného kódu.  
  
#### <a name="to-freeze-or-thaw-execution-of-a-thread"></a>Zablokování nebo odblokování provádění vlákna  
  
-   Na panelu nástrojů v horní části **vláken** okně klikněte na tlačítko **Freeze vláken** nebo **odblokování vláken**.  
  
     Tato akce ovlivní pouze vláken, které jsou vybrány v **vláken** okno. 

### <a name="switch-to-another-thread"></a>Přepnutí na jiné vlákno 

Žlutá šipka označuje aktuální vlákno (a umístění ukazatele spuštění). Zelenou šipku s složené tail označuje, že není aktuální vlákno má aktuálního kontextu ladicího programu.

#### <a name="to-switch-to-another-thread"></a>Chcete-li přepnout na jiné vlákno  
  
-   Proveďte některý z následujících kroků:  
  
    -   Dvakrát klikněte na libovolného vlákna.  
  
    -   Klikněte pravým tlačítkem na vlákno a klikněte na tlačítko **přepnout na vlákno**.

## <a name="group-and-sort-threads"></a>Skupiny a řazení vláken  
 Při seskupení vláken, zobrazí se v tabulce pro každou skupinu nadpisu. Záhlaví obsahuje popis skupiny, jako je například "Pracovní vlákna" nebo "Bez příznaku vláken" a ovládacím prvkem strom. Vlákna člena každé skupiny se zobrazí v části skupiny. Pokud chcete skrýt člen vláken pro skupiny, můžete v ovládacím prvku stromu sbalit skupiny.  
  
 Seskupení má přednost před řazení, můžete seskupit podle kategorií, například vláken a seřadit je podle ID v rámci každé kategorie.  
  
#### <a name="to-sort-threads"></a>Chcete-li seřadit vláken  
  
1.  Na panelu nástrojů v horní části **vláken** okně klikněte na tlačítko v horní části žádný sloupec.  
  
     Vláken jsou nyní seřazené podle hodnoty v tomto sloupci.  
  
2.  Pokud chcete pořadí řazení, klikněte znovu na tlačítko stejné.  
  
     Vláken, která zobrazovaly v horní části seznamu, se teď zobrazí v dolní části.  
  
#### <a name="to-group-threads"></a>Do skupiny vláken  
  
-   V **vláken** nástrojů v okně klikněte **Seskupit podle** seznamu a pak klikněte na kritéria, která chcete skupině vláken ve.  
  
#### <a name="to-sort-threads-within-groups"></a>Chcete-li seřadit vláken v rámci skupin  
  
1.  Na panelu nástrojů v horní části **vláken** okně klikněte **Seskupit podle** seznamu a pak klikněte na kritéria, která chcete skupině vláken ve.  
  
2.  V **vláken** okně klikněte na tlačítko v horní části žádný sloupec.  
  
     Vláken jsou nyní seřazené podle hodnoty v tomto sloupci.  
  
#### <a name="to-expand-or-collapse-all-groups"></a>Chcete-li rozbalit nebo sbalit všechny skupiny  
  
-   Na panelu nástrojů v horní části **vláken** okně klikněte na tlačítko **skupiny rozbalte** nebo **sbalit skupiny**.  
  
## <a name="search-for-specific-threads"></a>Vyhledejte konkrétní vláken  
 V [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], můžete vyhledat vláken, které odpovídají určeného řetězce. Při vyhledávání vláken v **vláken** okno, v okně se zobrazí všechna vlákna, které odpovídají řetězec pro hledání v žádný sloupec. Zahrnuje informace o umístění přístup z více vláken, který se zobrazí v horní části zásobníku volání v **umístění** sloupce. Ve výchozím nastavení ale zásobník úplné volání není vyhledávat.  
  
#### <a name="to-search-for-specific-threads"></a>K vyhledání konkrétní vláken  
  
-   Na panelu nástrojů v horní části **vláken** okno, přejděte na **vyhledávání** pole a buď:  
  
    -   Zadejte hledaný řetězec a stiskněte klávesu ENTER.  
  
         \-nebo –  
  
    -   Klikněte na rozevírací seznam vedle **vyhledávání** pole a vyberte z předchozí hledání hledaný řetězec.  
  
-   (Volitelné) Chcete-li zahrnout zásobníku úplné volání hledání, vyberte **zásobníkem volání hledání**.   
  
## <a name="display-thread-call-stacks-and-switching-between-frames"></a>Zásobníky volání vlákna zobrazení a přepínání mezi rámce  
Každé vlákno v vícevláknové program, má vlastní zásobníku volání. **Vláken** okno nabízí pohodlný způsob, jak zobrazit tyto balíčky.

> [!TIP]
> Vizuální znázornění zásobníku volání pro každé vlákno, použijte [paralelní zásobníky](../debugger/get-started-debugging-multithreaded-apps.md) okno.
  
#### <a name="to-view-the-call-stack-of-a-thread"></a>Chcete-li zobrazit zásobníku volání vlákna  
  
-   V **umístění** sloupce, klikněte na tlačítko obrácený trojúhelník vedle umístění přístup z více vláken.  
  
     Umístění se rozbalí a zobrazí zásobníku volání pro vlákno.  
  
#### <a name="to-view-or-collapse-the-call-stacks-of-all-threads"></a>K zobrazení nebo sbalit všechny podprocesy zásobníky volání  
  
-   Na panelu nástrojů v horní části **vláken** okně klikněte na tlačítko **rozbalte zásobníky volání** nebo **zásobníky volání sbalit**.  
  
## <a name="see-also"></a>Viz také  
 [Ladění vícevláknových aplikací](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Začínáme ladění vícevláknové aplikace](../debugger/get-started-debugging-multithreaded-apps.md)