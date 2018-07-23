---
title: Zobrazit vlákna použití okna paralelní zásobníky | Dokumentace Microsoftu
ms.custom: ''
ms.date: 04/25/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.parallelstacks
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, parallel tasks window
ms.assetid: f50efb78-5206-4803-bb42-426ef8133f2f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cd35f8545c1c768b07ff45ff8a6cdf84d24f3c58
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/20/2018
ms.locfileid: "39176964"
---
# <a name="view-threads-and-tasks-using-the-parallel-stacks-window"></a>Zobrazit vláknech a úkolech použití okna paralelní zásobníky
**Paralelní zásobníky** okna je užitečné při ladění aplikací s více vlákny. Jeho **zobrazení vláken** ukazuje informace v zásobníku volání pro všechna vlákna ve vaší aplikaci. Umožňuje procházet mezi vlákny a rámce zásobníku na tato vlákna. Ve spravovaném kódu **zobrazení úkolů** ukazuje volání zásobníků s <xref:System.Threading.Tasks.Task?displayProperty=fullName> objekty. V nativním kódu **zobrazení úkolů** ukazuje volání zásobníků s [skupiny úloh](/cpp/parallel/concrt/task-parallelism-concurrency-runtime), [paralelní algoritmy](/cpp/parallel/concrt/parallel-algorithms), [asynchronních agentů](/cpp/parallel/concrt/asynchronous-agents)a [prostých úloh](/cpp/parallel/concrt/task-scheduler-concurrency-runtime).  
  
## <a name="threads-view"></a>Zobrazení vláken  
 Následující obrázek znázorňuje jedno vlákno, které se nezdařilo z hlavní a b a pak na některé externí kód. Dvě ostatní vlákna spustit z externího kódu a pak se nepovedlo A, ale jedno z vláken pokračování b a pak na některé externí kód a další vlákno pokračuje na C a potom na některé AnonymousMethod.  
  
 ![Zobrazení okna paralelní zásobníky vlákna](../debugger/media/parallel_stacksthread.png "Parallel_StacksThread")  
  
 Na obrázku je modře zvýrazněna volání Cesta aktuálního vlákna a aktuální umístění vlákna (aktivní blok zásobníku) jsou označeny žlutou šipkou. Aktuální rámec zásobníku můžete změnit tak, že vyberete jinou metodu v **paralelní zásobníky** okna. To může způsobit také přepínání aktuálního vlákna, v závislosti na tom, zda je součást již aktuální vlákno nebo jiné vlákno metodu, kterou jste vybrali. Následující tabulka popisuje hlavní funkce **paralelní zásobníky** okna, jak je znázorněno na obrázku.  
  
|Popisek písmeno|Název elementu|Popis|  
|-|-|-|  
|OBJEKT|Segment zásobník volání nebo uzlu|Obsahuje řadu metod pro jedno nebo více vláken. Pokud uzel nemá žádné řádky šipky k ní připojená, to představuje cestu celý volání pro podprocesy.|  
|B|Modré zvýraznění|Označuje volání cestu aktuální vlákno.|  
|C|Šipka řádky|Připojte uzly k vytvoření volání celou cestu pro podprocesy.|  
|D|Popisek tlačítka na záhlaví uzlu|Zobrazí ID a uživatelem definovaný název každé vlákno, jehož cesta volání sdílí tento uzel.|  
|E|Metoda|Představuje jeden nebo více rámců zásobníku v stejným způsobem.|  
|F|Popisek tlačítka na – metoda|V zobrazení vláken, zobrazuje všechna vlákna v tabulce podobně jako **vlákna** okna. V zobrazení úlohy zobrazuje všechny úkoly v tabulce podobně jako **úlohy** okna.|  
  
 Kromě toho ukazuje okna paralelní zásobníky **pohled z ptačí perspektivy** ikonu v hlavním podokně při graf je příliš velký a nevejde se do okna. Můžete kliknout na ikonu zobrazíte celý graf v okně.  
  
## <a name="stack-frame-icons"></a>Ikony rámce zásobníku  
 Následující tabulka popisuje ikony, které obsahují informace o aktivní a aktuální rámců:  
  
|Ikona|Popis|  
|-|-|  
|![Paralelních zásobníků žlutá šipka](../debugger/media/icon_parallelyellowarrow.gif "Icon_ParallelYellowArrow")|Označuje, že metoda obsahuje aktuální umístění aktuální vlákno (aktivní blok zásobníku).|  
|![Paralelních zásobníků ikony vlákna](../debugger/media/icon_parallelthreads.gif "Icon_ParallelThreads")|Označuje, že metoda obsahuje aktuální umístění (aktivní blok zásobníku) mimo aktuální vlákno.|  
|![Paralelních zásobníků zelenou šipku](../debugger/media/icon_parallelgreenarrow.gif "Icon_ParallelGreenArrow")|Označuje, že metoda obsahuje aktuální blok zásobníku (aktuální kontext ladicího programu). Tento název metody je ve všech uzlech, ve které se zobrazí tučně.|  
  
## <a name="toolbar-controls"></a>Ovládací prvky panelu nástrojů  
 Následující obrázek a tabulka popisovat kontrolní mechanismy, které jsou k dispozici v panelu nástrojů paralelních zásobníků.  
  
 ![Panel nástrojů v okna paralelní zásobníky](../debugger/media/parallel_stackstoolbar.png "Parallel_StacksToolbar")  
  
|Popisek písmeno|Ovládací prvek|Popis|  
|-|-|-|  
|OBJEKT|Pole se seznamem vláken nebo úloh|Přepíná zobrazení mezi zásobníky vlákna volání a volání zásobníků s úkoly. Další informace najdete v zobrazení úloh a zobrazení vláken.|  
|B|Zobrazit pouze označená příznakem|Zásobníky volání zobrazí pouze pro vlákna, která jsou označena jako v jiných oknech ladění **vlákna GPU** okno a **paralelní sledování** okna.|  
|C|Přepnout zobrazení metody|Přepne mezi zobrazením zásobníku a metody. Další informace najdete v tématu zobrazení metody.|  
|D|Automaticky přejít na aktuální rámec zásobníku|Autoscrolls diagramu tak, aby zásobníku aktuálního rámce se v zobrazení. Tato funkce je užitečná, pokud změníte aktuální rámec zásobníku mezi jinými nebo pokud dosahujete Nová zarážka ve velkých diagramů.|  
|E|Přepnout ovládání lupy|Zobrazí nebo skryje ovládací prvek lupy. Můžete také přiblížit pomocí klávesy CTRL a kolečka myši, bez ohledu na to, zda se ovládací prvek lupy zapíná nebo pomocí kombinace kláves CTRL + SHIFT + '+' přiblížit a CTRL + SHIFT +'-' zmenšíte. Stisknutím kombinace kláves CTRL + F8 změní měřítko na celou obrazovku.|  
  
### <a name="context-menu-items"></a>Položek kontextové nabídky  
 Následující obrázek a tabulka popisují položky místní nabídky, které jsou k dispozici, když kliknete pravým tlačítkem myši na metodu v zobrazení vláken nebo úloh zobrazení. Posledních šest položek jsou si přímo z okna zásobník volání a zavést žádné nové chování.  
  
 ![Místní nabídky okna paralelní zásobníky](../debugger/media/parallel_contmenu.png "Parallel_ContMenu")  
  
|Položka nabídky|Popis|  
|-|-|  
|Příznak|Označí vybrané položky.|  
|Odznačit|Unflags vybranou položku.|  
|zablokování|Zablokuje vybranou položku.|  
|Uvolnit|Thaws vybranou položku.|  
|Přejít k úloze (vlákno)|Provádí stejnou funkci jako pole se seznamem na panelu nástrojů, ale udržuje stejné zvýrazněnou rámce zásobníku.|  
|Přejít ke zdrojovému kódu|Přejde do umístění ve zdrojovém kódu, který odpovídá rámce zásobníku, který klikli pravým tlačítkem myši uživatele.|  
|Přepnout na rámec|Stejné jako odpovídající příkaz nabídky v okně zásobník volání. Pomocí paralelní zásobníky, však může více snímků odpovídají jedné metody. Proto má položka nabídky podnabídky, z nichž každý představuje konkrétního zásobníku. Pokud jeden z rámce zásobníku v aktuálním vlákně, je vybraná nabídka, která odpovídá tohoto rámce zásobníku.|  
|Přejít na zpětný překlad|Přejde do umístění v okně zpětný překlad, která odpovídá rámce zásobníku, který klikli pravým tlačítkem myši uživatele.|  
|Zobrazit externí kód|Zobrazí nebo skryje externí kód.|  
|Hexadecimální zobrazení|Přepíná mezi desetinných míst a hexadecimální zobrazení.|  
|Informace o načítání symbolů|Zobrazí dialogové okno odpovídající.|  
|Nastavení symbolů|Zobrazí dialogové okno odpovídající.|  
  
## <a name="tasks-view"></a>Zobrazení úloh  
 Pokud vaše aplikace používá <xref:System.Threading.Tasks.Task?displayProperty=fullName> objekty (spravovaný kód) nebo `task_handle` objekty (nativní kód) vyjádřete paralelismus, můžete použít pole se seznamem na panelu nástrojů okna paralelní zásobníky přepnout na *zobrazení úkolů*. Úlohy zobrazení uvádí zásobníky volání úkolů místo vlákna. Zobrazení úloh se liší od zobrazení vláken následujícím způsobem:  
  
-   Zásobníky volání vláken, které nejsou spuštěné úkoly se nezobrazují.  
  
-   Zásobníky volání vláken, na kterých běží úlohy jsou vizuálně oříznut v horní a dolní části můžete zobrazit nejrelevantnější bloky, které se vztahují na úlohy.  
  
-   Po několika úloh v jednom vlákně se oddělit zásobníky volání těchto úkolů do samostatné uzly.  
  
 Následující obrázek znázorňuje paralelní zásobníky – zobrazení úloh na pravé straně a odpovídající zobrazení vláken na levé straně.  
  
 ![Úlohy zobrazení okna paralelní zásobníky](../debugger/media/parallel_tasksview.png "Parallel_TasksView")  
  
 Pokud chcete zobrazit celý zásobník volání, stačí přepnout zpět na zobrazení vláken pravým tlačítkem myši na rámec zásobníku a poté klepnutím na **přejít k vláknu**.  
  
 Jak je popsáno v předchozí tabulce, podržením ukazatele nad metodu, zobrazí se další informace. Následující obrázek ukazuje informace v popisu pro zobrazení vláken a zobrazení úloh.  
  
 ![Popisy tlačítek v okna paralelní zásobníky](../debugger/media/parallel_stack_tooltips.png "Parallel_Stack_Tooltips")  
  
## <a name="method-view"></a>Zobrazení metody  
 Ze zobrazení zobrazení vláken nebo úloh můžete vytvořit kontingenční graf v aktuální metodě kliknutím na ikonu zobrazení metody na panelu nástrojů. Metoda zobrazení ukazuje na první pohled všechny metody v všechna vlákna, které volají nebo jsou volány aktuální metoda. Následující obrázek znázorňuje zobrazení vláken a také jak vypadá stejné informace v zobrazení metody.  
  
 ![Zobrazení metody v okna paralelní zásobníky](../debugger/media/parallel_methodview.png "Parallel_MethodView")  
  
 Přepnutím na nový rámec zásobníku, proveďte tuto metodu aktuální metoda a způsobit, že v okně zobrazíte všechny volající a volané pro nové metody. To může způsobit, že některá vlákna se zobrazí nebo zmizí ze zobrazení, v závislosti na tom, zda se zobrazí na svých zásobníků volání metody. Pokud chcete vrátit do zobrazení za sebou, klikněte na tlačítko panelu nástrojů zobrazení metody znovu.  
  
## <a name="see-also"></a>Viz také  
 [Začínáme s laděním vícevláknových aplikace](../debugger/get-started-debugging-multithreaded-apps.md)   
 [Návod: Ladění paralelní aplikace](../debugger/walkthrough-debugging-a-parallel-application.md)   
 [Základy ladicího programu](../debugger/getting-started-with-the-debugger.md)   
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)   
 [Paralelní programování](/dotnet/standard/parallel-programming/index)   
 [Používání okna úloh](../debugger/using-the-tasks-window.md)   
 [Třída úlohy](../extensibility/debugger/task-class-internal-members.md)
