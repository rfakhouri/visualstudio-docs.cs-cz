---
title: Používání okna úloh | Microsoft Docs
ms.custom: ''
ms.date: 03/18/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d840f6c12de20fb613ee27d59395afeb15a5c34b
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2018
ms.locfileid: "37059332"
---
# <a name="using-the-tasks-window"></a>Používání okna úloh

**Úlohy** okno vypadá takto: **vláken** okno, s výjimkou toho, které se zobrazují informace o <xref:System.Threading.Tasks.Task?displayProperty=fullName>, [task_handle](/cpp/parallel/concrt/reference/task-group-class), nebo [WinJS.Promise ](http://msdn.microsoft.com/library/windows/apps/br211867.aspx) objekty místo každé vlákno. Jako vláken úlohy představují asynchronních operací, které můžou běžet souběžně; Při spuštění ve stejném vlákně, ale může několika úloh.

Ve spravovaném kódu, můžete použít **úlohy** okno při práci s <xref:System.Threading.Tasks.Task?displayProperty=fullName> objekty nebo pomocí **await** a **asynchronní** klíčová slova (**Await** a **asynchronní** v VisualBasic). Další informace o úlohách ve spravovaném kódu najdete v tématu [paralelní programování](/dotnet/standard/parallel-programming/index).

V nativním kódu, můžete použít **úlohy** okno při práci s [úkolů skupiny](/cpp/parallel/concrt/task-parallelism-concurrency-runtime), [paralelní algoritmy](/cpp/parallel/concrt/parallel-algorithms), [asynchronních agentů](/cpp/parallel/concrt/asynchronous-agents), a [prosté úlohy](/cpp/parallel/concrt/task-scheduler-concurrency-runtime). Další informace o úlohách v nativním kódu najdete v tématu [Concurrency Runtime](/cpp/parallel/concrt/concurrency-runtime).

V jazyce JavaScript, můžete použít okno úlohy při práci s promise `.then` kódu. V tématu [asynchronní programování v jazyce JavaScript (aplikace pro UPW)](http://msdn.microsoft.com/library/windows/apps/hh700330.aspx) Další informace.

Můžete použít **úlohy** okně vždy, když rozdělit ladicího programu. Je k dispozici na **ladění** nabídky kliknutím **Windows** a pak levým na **úlohy**. Následující obrázek ukazuje **úlohy** okno v jeho výchozí režim.

![Okno úlohy při](../debugger/media/parallel_tasks_window.png "Parallel_Tasks_Window")

> [!NOTE]
> Ve spravovaném kódu <xref:System.Threading.Tasks.Task> , je ve stavu [TaskStatus.Created](<xref:System.Threading.Tasks.TaskStatus.Created>), [TaskStatus.WaitingForActivation](<xref:System.Threading.Tasks.TaskStatus.WaitingForActivation>), nebo [TaskStatus.WaitingToRun](<xref:System.Threading.Tasks.TaskStatus.WaitingToRun>) nemusí být zobrazí v **úlohy** okno při spravovaných vláknech jsou v režimu spánku nebo připojení stavu.

## <a name="tasks-column-information"></a>Informace o sloupci úlohy

Sloupce v **úlohy** v okně zobrazí následující informace.

|Název sloupce|Popis|
|-----------------|-----------------|
|**příznaky**|Zobrazuje úkoly, které jsou označeny a umožňuje příznak nebo odstranění označení úlohu.|
|**Ikony**|Žlutá šipka označuje aktuální úlohy. Aktuální úloha je na nejvyšší úrovni na aktuální vlákno.<br /><br /> Bílé šipka označuje ukončování úlohy, který je ten, který byl aktuální v době byla vyvolána ladicího programu.<br /><br /> Ikona pozastavení označuje úlohu, která má byly pozastaveny uživatelem. Můžete ukotvení a uvolnění úlohy kliknutím pravým tlačítkem myši v seznamu.|
|**ID**|Poskytované systémem číslo pro úlohu. V nativním kódu jde o adresu úlohy.|
|**Status**|Aktuální stav (naplánované, aktivní, blokované, zablokovaných, čeká se na nebo dokončené) úlohy. Naplánované úlohy je ten, který dosud nebyla spuštěna a proto ještě nemá zásobníku volání, přiřazené vlákno nebo související informace.<br /><br /> Aktivní úkol je ten, který byl před porušením v ladicím programu provádění kódu.<br /><br /> Čeká se na nebo blokované úkol je ten, který je zablokovaný, protože se čeká na signál události, zámek k uvolnění nebo na dokončení jiné úlohy.<br /><br /> Zablokovaných úloha je čekání úlohy, jejichž vlákno je zablokována s jiné vlákno.<br /><br /> Najeďte myší **stav** buňky pro úlohu zablokovaných nebo čeká se na další informace o bloku. **Upozornění:** **úlohy** okno sestavy zablokování pouze pro blokované úlohu, která používá primitivní synchronizace, která je podporována počkejte Traversal řetězu (WCT). Například pro zablokovaných <xref:System.Threading.Tasks.Task> objekt, který používá WCT, sestavy ladicího programu **zablokována čeká na**. Pro zablokovaných úkol, který je spravován nástrojem Concurrency Runtime, který nepoužívá WCT, ladicího programu sestavy **čekání**. Další informace o WCT najdete v tématu [počkejte Traversal řetězu](http://msdn.microsoft.com/library/ms681622\(VS.85\).aspx).|
|**Čas spuštění**|Čas, kdy jsou aktivní úlohy.|
|**Doba trvání**|Počet sekund, po které byl aktivní úlohy.|
|**Čas dokončení**|Čas, kdy je úloha dokončena.|
|**Poloha**|Aktuální umístění v zásobníku volání úlohy. Podržte ukazatel nad tuto buňku, chcete-li zobrazit celý zásobník volání pro úlohu. Naplánované úlohy nemají hodnotu v tomto sloupci.|
|**Úloha**|Počáteční metoda a všechny argumenty, které byly předány úlohy při vytváření.|
|**AsyncState**|Pro spravovaný kód, stav úlohy. Ve výchozím nastavení je tento sloupec skrytá. Chcete-li zobrazit tento sloupec, otevřete v místní nabídce pro jednu ze záhlaví sloupců. Zvolte **sloupce**, **AsyncState**.|
|**Nadřazené**|ID úkolu, který vytvořil tento úkol. Pokud je toto pole prázdné, úloha nemá žádný nadřazený. Tento krok platí jenom pro spravované programy.|
|**Přiřazení přístup z více vláken**|ID a název vláken, na kterém je spuštěn úkol.|
|**AppDomain**|Pro spravovaný kód domény aplikace, ve kterém je prováděna úloha.|
|**task_group**|Pro nativní kód, adresa [task_group](/cpp/parallel/concrt/reference/task-group-class) objekt, který naplánované úlohy. Asynchronní agenti a prosté úlohy v tomto sloupci nastavena na hodnotu 0.|
|**Proces**|ID procesu, který úloha spuštěná.|

 Pravým tlačítkem myši na záhlaví sloupce a potom výběrem sloupce, které chcete, můžete přidat sloupce do zobrazení. (Odebrání sloupce tím, že zrušíte výběr.) Můžete také změnit pořadí sloupců tak, že je přetáhnete doleva nebo doprava. Místní nabídky sloupec je vidět na následujícím obrázku.

 ![Místní nabídky zobrazení v okně úlohy](../debugger/media/parallel_tasks_contextmenu.png "Parallel_Tasks_ContextMenu")

## <a name="sorting-tasks"></a>Řazení úkolů
 Úlohy seřadit podle sloupce kritéria, klikněte na záhlaví sloupce. Například kliknutím **ID** záhlaví sloupce lze seřadit úlohy s ID úlohy: 1,2,3,4,5 a tak dále. Chcete-li pořadí řazení, klikněte na záhlaví sloupce znovu. Aktuální sloupce a řazení řazení je indikován šipka na sloupec.

## <a name="grouping-tasks"></a>Seskupení úkolů
 Můžete seskupit podle libovolného sloupce v zobrazení seznamu úloh. Například, že kliknete pravým tlačítkem **stav** záhlaví sloupce a potom kliknutím na **Seskupit podle** > **[*stav*]**, můžete všechny úlohy, které mají stejný stav skupiny. Například by mohli rychle zobrazit, čeká na úlohy tak, aby může zaměřit na Proč jsou zablokované. Můžete také sbalit skupinu, která není týkající se během ladicí relace. Stejným způsobem můžete seskupit podle jiných sloupců. Skupinu lze (bez znaménka) příznakem jednoduše kliknutím na tlačítko vedle záhlaví skupiny. Následující obrázek ukazuje **úlohy** okno v režimu seskupené.

 ![Seskupené režim v okně úlohy](../debugger/media/parallel_tasks_groupedmode.png "Parallel_Tasks_GroupedMode")

## <a name="parent-child-view"></a>Nadřazeného a podřízeného prvku
 (Toto zobrazení je k dispozici pro spravovaný kód pouze.) Kliknutím pravým tlačítkem myši **stav** záhlaví sloupce a potom kliknutím na **Seskupit podle** > **nadřazené**, seznam úloh, můžete změnit na hierarchické zobrazení, ve kterém všechny podřízené úlohy je dílčí uzel, který můžete zobrazení nebo skrytí pod jeho nadřazeným prvkem.

## <a name="flagging-tasks"></a>Označování úlohy
 Můžete označit příznakem vlákno seznamu úkolů, na kterém je spuštěna úloha výběrem úlohy položky a pak vyberete **příznak přiřazené vlákno** z kontextové nabídky, nebo klikněte na ikonu vlajky prvního sloupce. Pokud je příznak několik úloh, můžete pak seřadit podle sloupce Příznak přenést všechny úkoly s příznakem dopředu tak, aby se můžete soustředit na ně. Můžete také **paralelní zásobníky** okno zobrazení jenom příznakem úlohy. To vám umožňuje odfiltrovat úlohy, které vás zajímají není pro ladění. Příznaky nejsou mezi ladění relacemi trvalé.

## <a name="freezing-and-thawing-tasks"></a>Zmrazení a uvolnění úlohy
 Lze ukotvit vláken, na kterém je spuštěn úkol pravým tlačítkem myši na položce v seznamu úloh a poté klikněte na **Freeze – přiřazené vlákno**. (Pokud již úloha nereaguje, příkaz je **odblokování přiřazené vláken**.) Po ukotvení vlákno daném vláknu nebude spustit, když krok prostřednictvím kódu po aktuální zarážce. **Freeze všechny vláken, ale tento jeden** příkaz se zablokuje všechna vlákna kromě toho, který provádí položce v seznamu úkolů.

 Následující obrázek znázorňuje další položky nabídky pro každou úlohu.

 ![Místní nabídky přístup z více vláken v okně úlohy](../debugger/media/parallel_tasks_contextmenu2.png "Parallel_Tasks_ContextMenu2")

## <a name="switching-the-active-task-or-frame"></a>Přepnutí na aktivní úkol nebo rámec

**Přepnout úloh** příkaz aktivní úkol díky aktuální úlohy. **Přepnout na rámce** příkaz díky vybrané zásobníku rámce zásobníku aktivní. Aktuální úloha nebo rámec zásobníku vybrané přepínačů kontextu ladicího programu.

## <a name="see-also"></a>Viz také:

- [Základy ladicího programu](../debugger/debugger-basics.md)
- [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)
- [Paralelní programování](/dotnet/standard/parallel-programming/index)
- [Concurrency Runtime](/cpp/parallel/concrt/concurrency-runtime)
- [Použití okna paralelní zásobníky](../debugger/using-the-parallel-stacks-window.md)
- [Návod: Ladění paralelní aplikace](../debugger/walkthrough-debugging-a-parallel-application.md)