---
title: "Zobrazit použití okna paralelní zásobníky vlákna | Microsoft Docs"
ms.custom: 
ms.date: 04/25/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 72c7c38dece8924f48298c0b7b661f564f9b1afc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="view-threads-and-tasks-using-the-parallel-stacks-window"></a>Zobrazení vláken a úloh pomocí okna paralelní zásobníky
**Paralelní zásobníky** je užitečná při ladění vícevláknové aplikace. Jeho **zobrazení vláken** zobrazí informace v zásobníku volání pro všechna vlákna ve vaší aplikaci. Umožňuje vám přecházet mezi vláken a rámce zásobníku na těchto vláken. Ve spravovaném kódu **zobrazení úlohy** ukáže zásobníky z volání <xref:System.Threading.Tasks.Task?displayProperty=fullName> objekty. V nativním kódu **zobrazení úlohy** ukáže zásobníky z volání [úkolů skupiny](/cpp/parallel/concrt/task-parallelism-concurrency-runtime), [paralelní algoritmy](/cpp/parallel/concrt/parallel-algorithms), [asynchronních agentů](/cpp/parallel/concrt/asynchronous-agents)a [prosté úlohy](/cpp/parallel/concrt/task-scheduler-concurrency-runtime).  
  
## <a name="threads-view"></a>Zobrazení vláken  
 Následující obrázek znázorňuje jedno vlákno, které se z hlavní do A, b a pak na externí kód. Dva jiná vlákna spuštěné z některého externího kódu a pak se do A, ale jeden z vláken dál b a pak na některé externí kódu a další vlákno dál c a pak na některé AnonymousMethod.  
  
 ![Zobrazení v okně paralelní zásobníky vláken](../debugger/media/parallel_stacksthread.png "Parallel_StacksThread")  
  
 Na obrázku modře zvýrazněný volání cesta aktuální vlákno a aktuální umístění (aktivní zásobníku) vlákno jsou označeny žlutou šipku. Můžete změnit tak, že vyberete jinou metodu v aktuální rámec zásobníku **paralelní zásobníky** okno. To může dojít také přepínání aktuální vlákno, v závislosti na tom, jestli metodu, kterou jste vybrali je součástí aktuální vlákno již nebo jiné vlákno. Následující tabulka popisuje hlavní funkce **paralelní zásobníky** okno, jak je znázorněno na obrázku.  
  
|Písmeno popisku|Název elementu|Popis|  
|--------------------|------------------|-----------------|  
|OBJEKT|Uzel nebo Segment zásobník volání|Obsahuje řadu metody pro jeden nebo více vláken. Pokud uzel nemá žádné řádky šipku připojeny, pak představuje cestu celý volání pro podprocesy.|  
|B|Modré zvýraznění|Určuje cestu volání aktuálního vlákna.|  
|C|Šipka řádky|Připojte uzly a společně tvoří celá volání cestu pro podprocesy.|  
|D|Popis tlačítka na záhlaví uzlu|Zobrazí ID a uživatelské jméno každé vlákno, jehož cesta volání sdílí tento uzel.|  
|E|Metoda|Reprezentuje jeden nebo více rámce zásobníku v stejnou metodu.|  
|F|Popis tlačítka na – metoda|V zobrazení vláken zobrazuje všechna vlákna v tabulce podobně jako **vláken** okno. V zobrazení úlohy zobrazuje všechny úlohy v tabulce podobně jako **úlohy** okno.|  
  
 Kromě toho okna paralelní zásobníky ukazuje **pohled z ptačí perspektivy** ikonu v hlavním podokně, když je moc velká a nevejde se do okna grafu. Kliknutím na ikonu zobrazíte celý grafu v okně.  
  
## <a name="stack-frame-icons"></a>Ikony rámce zásobníku  
 Následující tabulka popisuje ikony, které obsahují informace o rámce zásobníku aktivní a aktuální:  
  
|||  
|-|-|  
|Ikona|Popis|  
|![Paralelní zásobníky – žlutá šipka](../debugger/media/icon_parallelyellowarrow.gif "Icon_ParallelYellowArrow")|Určuje, že metoda obsahuje aktuální umístění aktuální vlákno (aktivní zásobníku).|  
|![Paralelní zásobníky – ikona vláken](../debugger/media/icon_parallelthreads.gif "Icon_ParallelThreads")|Určuje, že metoda obsahuje aktuální umístění (aktivní zásobníku) bez aktuální vlákno.|  
|![Paralelní zásobníky – zelenou šipku](../debugger/media/icon_parallelgreenarrow.gif "Icon_ParallelGreenArrow")|Určuje, že metoda obsahuje aktuální rámec zásobníku (aktuální kontextu ladicího programu). Tento název metody je ve všech uzlech, ve kterých se zobrazí tučně.|  
  
## <a name="toolbar-controls"></a>Ovládací prvky panelu nástrojů  
 Následující obrázek a tabulka popisují ovládacích prvků, které jsou k dispozici na panelu nástrojů paralelní zásobníky.  
  
 ![Nástrojů okna paralelní zásobníky](../debugger/media/parallel_stackstoolbar.png "Parallel_StacksToolbar")  
  
|Písmeno popisku|Ovládací prvek|Popis|  
|--------------------|-------------|-----------------|  
|OBJEKT|Pole se seznamem vláken nebo úlohy|Přepínače zobrazení mezi zásobníky vlákna volání a zásobníky úloh volání. Další informace najdete v zobrazení úloh a zobrazení vláken.|  
|B|Zobrazit pouze příznakem|Zásobníky volání zobrazuje pouze pro vláken, která jsou označena v jiných ladění windows, jako **vláken GPU** okno a **paralelního sledování** okno.|  
|C|Přepnout zobrazení – metoda|Přepíná mezi zásobníku a zobrazení metody. Další informace najdete v tématu zobrazení metody.|  
|D|Posuňte se automaticky aktuální rámec zásobníku|Autoscrolls diagramu tak, aby rámce zásobníku aktuální je v zobrazení. Tato funkce je užitečná, pokud měníte aktuální rámec zásobníku z jiných windows, nebo když jste nedosáhli nové zarážka v velkých diagramů.|  
|E|Ovládací prvek přepínač přiblížení|Zobrazí nebo skryje ovládacího prvku přiblížení. Můžete také zvětšit stisknutím kláves CTRL a zapnutí kolečka myši, bez ohledu na to, viditelnost ovládacího prvku přiblížení, nebo pomocí kombinace kláves CTRL + SHIFT + '+' přiblížení a CTRL + SHIFT +'-' zvětšit. Stisknutím kombinace kláves CTRL + F8 změní měřítko na celou obrazovku.|  
  
### <a name="context-menu-items"></a>Položek kontextové nabídky  
 Následující obrázek a tabulka popisují položky místní nabídky, které jsou k dispozici, když kliknete pravým tlačítkem na metodu v zobrazení vláken nebo v zobrazení úloh. Posledních šest položky jsou vždy pouze vypůjčí přímo z okna zásobník volání a způsobit žádné nové chování.  
  
 ![Místní nabídky v okně paralelní zásobníky](../debugger/media/parallel_contmenu.png "Parallel_ContMenu")  
  
|Položka nabídky|Popis|  
|---------------|-----------------|  
|Příznak|Označí vybrané položky.|  
|Odstranění označení|Unflags vybranou položku.|  
|Zablokování|Zablokuje vybranou položku.|  
|Odblokování|Thaws vybranou položku.|  
|Přejděte k úloze (přístup z více vláken)|Provede stejnou funkci jako pole se seznamem na panelu nástrojů, ale zachová stejné rámce zásobníku zvýrazněná.|  
|Přejít do zdrojového kódu|Umožňuje přejít do umístění ve zdrojovém kódu, která odpovídá rámce zásobníku, který uživatel klepli pravým tlačítkem myši.|  
|Přepnout na rámec|Stejné jako odpovídající příkaz nabídky v okně zásobník volání. S paralelní zásobníky, však může více snímků odpovídají jednu metodu. Položky nabídky proto musí dílčích, z nichž každý představuje konkrétní zásobníku. Pokud jeden z rámce zásobníku na aktuální vlákno, je vybrán v nabídce, která odpovídá této rámce zásobníku.|  
|Přejděte na zpětný překlad|Umožňuje přejít do umístění v okně zpětný překlad, která odpovídá rámce zásobníku, který uživatel klepli pravým tlačítkem myši.|  
|Zobrazit externí kódu|Zobrazí nebo skryje externí kódu.|  
|Hexadecimální zobrazení|Přepne mezi decimal, šestnáctkové hodnoty zobrazení.|  
|Informace o načítání symbolů|Zobrazí dialogové okno odpovídající.|  
|Nastavení – symbol|Zobrazí dialogové okno odpovídající.|  
  
## <a name="tasks-view"></a>Zobrazení úloh  
 Pokud vaše aplikace používá <xref:System.Threading.Tasks.Task?displayProperty=fullName> objekty (spravovaný kód) nebo `task_handle` objekty (nativní kód) express paralelismus, můžete použít pole se seznamem na panelu nástrojů okna paralelní zásobníky přepnout do *zobrazení úlohy*. Úlohy zobrazení se zobrazují zásobníky volání úloh místo vláken. Zobrazení úloh se liší od zobrazení vláken následujícím způsobem:  
  
-   Zásobníky volání vláken, které nejsou spuštěné úlohy nejsou zobrazeny.  
  
-   Zásobníky volání vláken, které jsou spuštěné úkoly jsou vizuálně oříznut v horní a dolní zobrazíte nejdůležitější rámců, které se týkají úlohy.  
  
-   Po několika úloh na jedno vlákno se zásobníky volání těchto úloh se rozdělí se do samostatné uzly.  
  
 Následující obrázek znázorňuje paralelní zásobníky – zobrazení úloh na pravé straně a odpovídající zobrazení vláken na levé straně.  
  
 ![Úlohy zobrazení v okně paralelní zásobníky](../debugger/media/parallel_tasksview.png "Parallel_TasksView")  
  
 Pokud chcete zobrazit celý zásobník volání, právě přepněte zpět na zobrazení vláken pravým tlačítkem myši na rámec zásobníku a potom kliknutím na **přejít na vlákno**.  
  
 Jak je popsáno v předchozí tabulce, ukázáním myší metodu, můžete zobrazit další informace. Následující obrázek ukazuje informace v popisu tlačítka pro zobrazení vláken a zobrazení úloh.  
  
 ![Popisy tlačítek v okně paralelní zásobníky](../debugger/media/parallel_stack_tooltips.png "Parallel_Stack_Tooltips")  
  
## <a name="method-view"></a>Zobrazení metody  
 Zobrazení vláken nebo zobrazení úloh můžete vytvořit kontingenční graf na aktuální metoda kliknutím na zobrazení metody ikonu na panelu nástrojů. Zobrazení metody zobrazuje rychlý přehled všech metod v všechna vlákna, které volají nebo jsou volány aktuální metoda. Následující obrázek znázorňuje zobrazení vláken a také vzhled stejné informace. v zobrazení metodu.  
  
 ![Zobrazení metody v okně paralelní zásobníky](../debugger/media/parallel_methodview.png "Parallel_MethodView")  
  
 Přepnutím na nové rámce zásobníku, ujistěte se, že metoda aktuální metoda a způsobit okno a zobrazit všechny volající a volané nové metody. To může způsobit některé vláken zobrazují nebo zmizí ze zobrazení, v závislosti na tom, jestli dané metody se zobrazí na jejich zásobníky volání. Pokud chcete vrátit do zásobníku zobrazení, klikněte na tlačítko panelu nástrojů zobrazení metody znovu.  
  
## <a name="see-also"></a>Viz také  
 [Začínáme ladění vícevláknové aplikace](../debugger/get-started-debugging-multithreaded-apps.md)   
 [Návod: Ladění paralelní aplikace](../debugger/walkthrough-debugging-a-parallel-application.md)   
 [Základy ladicího programu](../debugger/debugger-basics.md)   
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)   
 [Paralelní programování](/dotnet/standard/parallel-programming/index)   
 [Používání okna úloh](../debugger/using-the-tasks-window.md)   
 [Task – třída](../extensibility/debugger/task-class-internal-members.md)
