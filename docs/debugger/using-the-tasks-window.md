---
title: "Používání okna úloh | Microsoft Docs"
ms.custom: 
ms.date: 04/21/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.paralleltasks
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, parallel tasks window
ms.assetid: bd5e0612-a0dc-41cf-a7af-1e87d0d5c35f
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c4ec0178a4767e7e0c5c726816dcd7088e14f17b
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/05/2018
---
# <a name="using-the-tasks-window"></a>Používání okna úloh
**Úlohy** okno vypadá takto: **vláken** okno, s výjimkou toho, které se zobrazují informace o <xref:System.Threading.Tasks.Task?displayProperty=fullName>, [task_handle](/cpp/parallel/concrt/reference/task-group-class), nebo [WinJS.Promise ](http://msdn.microsoft.com/library/windows/apps/br211867.aspx) objekty místo každé vlákno. Jako vláken úlohy představují asynchronních operací, které můžou běžet souběžně; Při spuštění ve stejném vlákně, ale může několika úloh. 
  
 Ve spravovaném kódu, můžete použít **úlohy** okno při práci s <xref:System.Threading.Tasks.Task?displayProperty=fullName> objekty nebo pomocí **await** a **asynchronní** klíčová slova (**Await** a **asynchronní** v VisualBasic). Další informace o úlohách ve spravovaném kódu najdete v tématu [paralelní programování](/dotnet/standard/parallel-programming/index).  
  
 V nativním kódu, můžete použít **úlohy** okno při práci s [úkolů skupiny](/cpp/parallel/concrt/task-parallelism-concurrency-runtime), [paralelní algoritmy](/cpp/parallel/concrt/parallel-algorithms), [asynchronních agentů](/cpp/parallel/concrt/asynchronous-agents), a [prosté úlohy](/cpp/parallel/concrt/task-scheduler-concurrency-runtime). Další informace o úlohách v nativním kódu najdete v tématu [Concurrency Runtime](/cpp/parallel/concrt/concurrency-runtime).  
  
 V jazyce JavaScript, můžete použít okno úlohy při práci s promise `.then` kódu. V tématu [asynchronní programování v jazyce JavaScript (aplikace pro UPW)](http://msdn.microsoft.com/library/windows/apps/hh700330.aspx) Další informace.   
  
 Můžete použít **úlohy** okně vždy, když rozdělit ladicího programu. Je k dispozici na **ladění** nabídky kliknutím **Windows** a pak levým na **úlohy**. Následující obrázek ukazuje **úlohy** okno v jeho výchozí režim.  
  
 ![Okno úlohy při](../debugger/media/parallel_tasks_window.png "Parallel_Tasks_Window")  
  
> [!NOTE]
>  Ve spravovaném kódu <xref:System.Threading.Tasks.Task> , je ve stavu <xref:System.Threading.Tasks.TaskStatus>, <xref:System.Threading.Tasks.TaskStatus>, nebo <xref:System.Threading.Tasks.TaskStatus> nemusí být zobrazeny v okně úlohy po spravovaných vláknech v režimu spánku nebo připojení stavu.  
  
## <a name="tasks-column-information"></a>Informace o sloupci úlohy  
 Sloupce v **úlohy** v okně zobrazí následující informace.  
  
|Název sloupce|Popis|  
|-----------------|-----------------|  
|**Příznaky**|Zobrazuje úkoly, které jsou označeny a umožňuje příznak nebo odstranění označení úlohu.|  
|**Ikony**|Žlutá šipka označuje aktuální úlohy. Aktuální úloha je na nejvyšší úrovni na aktuální vlákno.<br /><br /> Bílé šipka označuje ukončování úlohy, který je ten, který byl aktuální v době byla vyvolána ladicího programu.<br /><br /> Ikona pozastavení označuje úlohu, která má byly pozastaveny uživatelem. Můžete ukotvení a uvolnění úlohy kliknutím pravým tlačítkem myši v seznamu.|  
|**ID**|Poskytované systémem číslo pro úlohu. V nativním kódu jde o adresu úlohy.|  
|**Status**|Aktuální stav (naplánované, aktivní, zablokovaných, čekání nebo dokončené) úlohy. Naplánované úlohy je ten, který dosud nebyla spuštěna a proto ještě nemá zásobníku volání, přiřazené vlákno nebo související informace.<br /><br /> Aktivní úkol je ten, který byl před porušením v ladicím programu provádění kódu.<br /><br /> Úloha čekání je ten, který je zablokovaný, protože se čeká na signál události, zámek k uvolnění nebo na dokončení jiné úlohy.<br /><br /> Zablokovaných úloha je čekání úlohy, jejichž vlákno je zablokována s jiné vlákno.<br /><br /> Najeďte myší **stav** buňky zablokovaných nebo čekání úlohy zobrazíte další informace o bloku. **Upozornění:** **úlohy** okno sestavy zablokování pouze pro blokované úlohu, která používá primitivní synchronizace, která je podporována počkejte Traversal řetězu (WCT). Například pro zablokovaných <xref:System.Threading.Tasks.Task> objekt, který používá WCT, sestavy ladicího programu **zablokována čekání**. Pro zablokovaných úkol, který je spravován nástrojem Concurrency Runtime, který nepoužívá WCT, ladicího programu sestavy **čekání**. Další informace o WCT najdete v tématu [počkejte Traversal řetězu](http://msdn.microsoft.com/library/ms681622\(VS.85\).aspx).|  
|**Čas spuštění**|Čas, kdy jsou aktivní úlohy.|  
|**Doba trvání**|Počet sekund, po které byl aktivní úlohy.|  
|**Čas dokončení**|Čas, kdy je úloha dokončena.|  
|**Umístění**|Aktuální umístění v zásobníku volání úlohy. Podržte ukazatel nad tuto buňku, chcete-li zobrazit celý zásobník volání pro úlohu. Naplánované úlohy nemají hodnotu v tomto sloupci.|  
|**Úloha**|Počáteční metoda a všechny argumenty, které byly předány úlohy při vytváření.|  
|**Nadřazené**|ID úkolu, který vytvořil tento úkol. Pokud je toto pole prázdné, úloha nemá žádný nadřazený. Tento krok platí jenom pro spravované programy.|  
|**Přiřazení přístup z více vláken**|ID a název vláken, na kterém je spuštěn úkol.|  
|**Návratový stav**|Stav úlohy po jeho dokončení. Návratový stav hodnoty jsou **úspěch**, **zrušeno**, a **chyba**.|  
|**Domény aplikace**|Pro spravovaný kód domény aplikace, ve kterém je prováděna úloha.|  
|**task_group**|Pro nativní kód, adresa [task_group](/cpp/parallel/concrt/reference/task-group-class.mdd) objekt, který naplánované úlohy. Asynchronní agenti a prosté úlohy v tomto sloupci nastavena na hodnotu 0.|  
|Proces|ID procesu, který úloha spuštěná.|  
|Asynchronní stavu|Pro spravovaný kód, stav úlohy. Ve výchozím nastavení je tento sloupec skrytá. Chcete-li zobrazit tento sloupec, otevřete v místní nabídce pro jednu ze záhlaví sloupců. Zvolte **sloupce**, **AsyncState**.|  
  
 Pravým tlačítkem myši na záhlaví sloupce a potom výběrem sloupce, které chcete, můžete přidat sloupce do zobrazení. (Odebrání sloupce tím, že zrušíte výběr.) Můžete také změnit pořadí sloupců tak, že je přetáhnete doleva nebo doprava. Místní nabídky sloupec je vidět na následujícím obrázku.  
  
 ![Místní nabídky zobrazení v okně úlohy](../debugger/media/parallel_tasks_contextmenu.png "Parallel_Tasks_ContextMenu")  
  
## <a name="sorting-tasks"></a>Řazení úkolů  
 Úlohy seřadit podle sloupce kritéria, klikněte na záhlaví sloupce. Například kliknutím **ID** záhlaví sloupce lze seřadit úlohy s ID úlohy: 1,2,3,4,5 a tak dále. Chcete-li pořadí řazení, klikněte na záhlaví sloupce znovu. Aktuální sloupce a řazení řazení je indikován šipka na sloupec.  
  
## <a name="grouping-tasks"></a>Seskupení úkolů  
 Můžete seskupit podle libovolného sloupce v zobrazení seznamu úloh. Například, že kliknete pravým tlačítkem **stav** záhlaví sloupce a potom kliknutím na **seskupení podle stavu**, můžete seskupit všechny úlohy, které mají stejný stav. Například může rychle zobrazí čekání úlohy tak, aby může zaměřit na Proč jsou zablokované. Můžete také sbalit skupinu, která není týkající se během ladicí relace. Stejným způsobem můžete seskupit podle jiných sloupců. Skupinu lze (bez znaménka) příznakem jednoduše kliknutím na tlačítko vedle záhlaví skupiny. Následující obrázek ukazuje **úlohy** okno v režimu seskupené.  
  
 ![Seskupené režim v okně úlohy](../debugger/media/parallel_tasks_groupedmode.png "Parallel_Tasks_GroupedMode")  
  
## <a name="parent-child-view"></a>Nadřazeného a podřízeného prvku  
 (Toto zobrazení je k dispozici pro spravovaný kód pouze.) Pravým tlačítkem myši na záhlaví sloupce a kliknutím na **nadřazeného a podřízeného prvku**, seznam úloh, můžete změnit na hierarchické zobrazení, ve které všechny podřízené úloha je dílčí uzel, který můžete zobrazení nebo skrytí pod jeho nadřazeným prvkem. Následující obrázek znázorňuje úlohy v zobrazení nadřazený podřízený.  
  
 ![Nadřazené & č. 45; podřízené zobrazení v okně úlohy](../debugger/media/parallel_tasks_parentchildview.png "Parallel_Tasks_ParentChildView")  
  
## <a name="flagging-tasks"></a>Označování úlohy  
 Můžete označit příznakem vlákno seznamu úkolů, na kterém je spuštěna úloha výběrem úlohy položky a pak vyberete **příznak** z kontextové nabídky, nebo klikněte na ikonu vlajky prvního sloupce. Pokud je příznak několik úloh, můžete pak seřadit podle sloupce Příznak přenést všechny úkoly s příznakem dopředu tak, aby se můžete soustředit na ně. Můžete také **paralelní zásobníky** okno zobrazení jenom příznakem úlohy. To vám umožňuje odfiltrovat úlohy, které vás zajímají není pro ladění. Příznaky nejsou mezi ladění relacemi trvalé.  
  
## <a name="freezing-and-thawing-tasks"></a>Zmrazení a uvolnění úlohy  
 Lze ukotvit vláken, na kterém je spuštěn úkol pravým tlačítkem myši na položce v seznamu úloh a poté klikněte na **Freeze – přiřazené vlákno**. (Pokud již úloha nereaguje, příkaz je **odblokování přiřazené vláken**.) Po ukotvení vlákno daném vláknu nebude spustit, když krok prostřednictvím kódu po aktuální zarážce. **Freeze všechny vláken, ale tento** příkaz se zablokuje všechna vlákna kromě toho, který provádí položce v seznamu úkolů.  
  
 Následující obrázek znázorňuje další položky nabídky pro každou úlohu.  
  
 ![Místní nabídky přístup z více vláken v okně úlohy](../debugger/media/parallel_tasks_contextmenu2.png "Parallel_Tasks_ContextMenu2")  
  
## <a name="see-also"></a>Viz také  
 [Základy ladicího programu](../debugger/debugger-basics.md)   
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)   
 [Paralelní programování](/dotnet/standard/parallel-programming/index)   
 [Concurrency Runtime](/cpp/parallel/concrt/concurrency-runtime)   
 [Použití okna paralelní zásobníky](../debugger/using-the-parallel-stacks-window.md)   
 [Návod: Ladění paralelní aplikace](../debugger/walkthrough-debugging-a-parallel-application.md)