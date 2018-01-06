---
title: "Ladění vícevláknových aplikací v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 09/05/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.gputthreads
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- threading [Visual Studio], debugging
- debugging [Visual Studio], high-performance computing
- debugging [Visual Studio], multithreaded
- multithreaded debugging
- high-performance debugging
ms.assetid: 9d175bc2-1d95-4c47-9bc3-9755af968a9c
caps.latest.revision: "25"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8b32134abff19965edac150ac5f69db25640ee08
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/05/2018
---
# <a name="debug-multithreaded-applications-in-visual-studio"></a>Ladění vícevláknových aplikací v sadě Visual Studio
Vlákno je posloupnost pokyny, které operační systém přiděluje času procesoru. Každý proces, který běží v operačním systému se skládá z nejméně jedno vlákno. Procesy, které mají více než jedno vlákno se nazývají s více vlákny.  
  
Počítače s více procesory, procesory nebo Hyper-threadingem procesy můžete současně spustit více vláken. Paralelní zpracování více vláken může výrazně zlepšit výkon programu, ale také může být ladění obtížnější protože zavádí nutné ke sledování více vláken.  
  
Kromě toho multithreading zavádí několik nových typů potenciální chyby. Často například dvě nebo více podprocesů mít přístup k prostředku stejné, ale pouze jedno vlákno můžete bezpečně přístup k prostředku v čase. Určitou formu vzájemné vyloučení je nutné zajistit, že pouze jedno vlákno je přístup k prostředku v čase. Pokud vzájemné vyloučení provádí nesprávně, můžete vytvořit *zablokování* podmínky, které můžete provést žádný přístup z více vláken. Blokování může být obzvláště pevný problém k ladění.

Visual Studio poskytuje různé nástroje pro použití v ladění vícevláknových aplikací.

- Pro vlákna, jsou mezi primární nástroje k ladění vláken **vláken** okno, značek přístup z více vláken ve windows zdroj **paralelní zásobníky** okně **paralelního sledování** okně a **ladění umístění** panelu nástrojů. Další informace o **vláken** okno a **ladění umístění** nástrojů najdete v části [návod: ladění pomocí okna vláken](../debugger/how-to-use-the-threads-window.md). Další informace o použití **paralelní zásobníky** a **paralelního sledování** windows, najdete v části [Začínáme ladění vícevláknové aplikace](../debugger/get-started-debugging-multithreaded-apps.md). Obě témata ukazují, jak používat značky přístup z více vláken.
  
- Pro kód, který používá [Task Parallel Library (TPL)](/dotnet/standard/parallel-programming/task-parallel-library-tpl) nebo [Concurrency Runtime](/cpp/parallel/concrt/concurrency-runtime/), jsou mezi primární nástroje pro ladění **paralelní zásobníky** okno, **Paralelního sledování** okně a **úlohy** okno ( **úlohy** okno také podporuje JavaScript). Abyste mohli začít, najdete v části [návod: ladění paralelní aplikace](../debugger/walkthrough-debugging-a-parallel-application.md) a [návod: ladění aplikace C++ AMP](/cpp/parallel/amp/walkthrough-debugging-a-cpp-amp-application). 

- K ladění vláken v GPU, primárním nástrojem jsou **vláken GPU** okno. V tématu [postupy: použití okna vláken GPU](../debugger/how-to-use-the-gpu-threads-window.md).  

- U procesů, jsou mezi primární nástroje **připojit k procesu** dialogové okno, **procesy** okně a **ladění umístění** panelu nástrojů.  
  
Visual Studio také poskytuje výkonné zarážky a tracepoints, může být velmi užitečná při ladění vícevláknových aplikací. Podmínky zarážek a filtry můžete použít k umístění zarážky na jednotlivých vláken. V tématu [použití zarážek](../debugger/using-breakpoints.md). 
  
Ladění vícevláknové aplikace, která má uživatelské rozhraní může být obzvláště složité. V takovém případě můžete zvážit spouštět aplikace na druhý počítač a pomocí vzdálené ladění. Informace najdete v tématu [vzdálené ladění](../debugger/remote-debugging.md).  
  
## <a name="in-this-section"></a>V tomto oddílu
 [Začínáme ladění vícevláknové aplikace](../debugger/get-started-debugging-multithreaded-apps.md).  
 Průvodce podprocesu ladění funkcí, s důrazem na funkce **paralelní zásobníky** okno a **paralelního sledování** okno.

 [Nástroje pro ladění vláken a procesů](../debugger/debug-threads-and-processes.md)  
 Obsahuje seznam funkcí nástroje pro ladění vláken a procesů.  
  
 [Ladění více procesů](../debugger/debug-multiple-processes.md)  
 Vysvětluje, jak k ladění více procesů.

 [Návod: Ladění pomocí okna vláken](../debugger/how-to-use-the-threads-window.md).  
 Návod, který ukazuje způsob použití **vláken** okno a **ladění umístění** panelu nástrojů. 

 [Návod: Ladění paralelní aplikace](../debugger/walkthrough-debugging-a-parallel-application.md)  
 Návod, který ukazuje způsob použití **paralelní zásobníky** a **úlohy** systému windows.  
  
 [Postupy: přepnutí na jiné vlákno během ladění](../debugger/how-to-switch-to-another-thread-while-debugging.md)  
 Tři způsoby, jak přepnout kontext ladění na jiné vlákno.  
  
 [Postupy: označení a odstranění označení vlákna](../debugger/how-to-flag-and-unflag-threads.md)  
 Označit nebo příznak vláken, které chcete udělit zvláštní pozornost při ladění.    
  
 [Postupy: ladění na clusteru s podporou High-Performance](../debugger/how-to-debug-on-a-high-performance-cluster.md)  
 Techniky pro aplikaci, která běží na clusteru, vysoce výkonné ladění.  

 [Tipy k ladění vláken v nativním kódu](../debugger/tips-for-debugging-threads-in-native-code.md)  
 Jednoduché techniky, které mohou být užitečné k ladění nativního vláken. 

 [Postupy: nastavení názvu vlákna v nativním kódu](../debugger/how-to-set-a-thread-name-in-native-code.md)  
 Poskytnout název, který se zobrazí v vašeho vlákna **vláken** okno.  
  
 [Postupy: nastavení názvu vlákna ve spravovaném kódu](../debugger/how-to-set-a-thread-name-in-managed-code.md)  
 Poskytnout název, který se zobrazí v vašeho vlákna **vláken** okno. 
  
## <a name="related-sections"></a>Související oddíly  
 [Použití zarážek](../debugger/using-breakpoints.md)

 - Podmínky použití zarážek nebo filtry, pokud chcete ladit jednotlivých vlákno.  
  
 - Tracepoints umožňují k trasování provádění vašeho programu bez ukončování řádků. To může být užitečné pro studujete problémy, třeba zablokování.  
  
 [Dělení na vlákna](/dotnet/standard/threading/index)  
 Dělení na vlákna koncepty v [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] programování, včetně ukázkový kód.  
  
 [Více vláken v součásti](http://msdn.microsoft.com/Library/2fc31e68-fb71-4544-b654-0ce720478779)  
 Používání více vláken v [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] součásti.  
  
 [Podpora multithreadingu ve starším kódu (Visual C++)](/cpp/parallel/multithreading/multithreading-support-for-older-code-visual-cpp)  
 Dělení na vlákna koncepty a ukázkový kód pro programátory v jazyce C++ pomocí MFC.  
  
## <a name="see-also"></a>Viz také  
 [Ladění vláken a procesů](../debugger/debug-threads-and-processes.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)