---
title: Ladění vícevláknových aplikací v sadě Visual Studio | Dokumentace Microsoftu
ms.custom: ''
ms.date: 09/05/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.gputthreads
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1d238f1c6be12753fe87cece03139185e1c24ad6
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49854770"
---
# <a name="debug-multithreaded-applications-in-visual-studio"></a>Ladění vícevláknových aplikací v sadě Visual Studio
Vlákno je řada pokynů, pro které operační systém přiděluje čas procesoru. Každý proces, na kterém běží v operačním systému se skládá z alespoň jednoho vlákna. Procesy, které mají více než jedno vlákno, se nazývají s více vlákny.  
  
Počítače s více procesory, vícejádrovými procesory nebo procesy využívající hyperthreading lze spustit více vláken současně. Paralelní zpracování více podprocesů může značně zlepšit výkon aplikace, ale to může také ztížit ladění protože zavádí potřebu sledovat více vláken.  
  
Kromě toho multithreading přináší některé nové typy možných chyb. Často například dvě nebo více vláken mít přístup ke stejnému prostředku, ale pouze jedno vlákno může bezpečně přistupovat k prostředku najednou. Některé forma vzájemného vyloučení je nezbytné, abyste měli jistotu, že pouze jedno vlákno k prostředku najednou. Pokud nesprávně provedeného vzájemného vyloučení můžete vytvořit *zablokování* podmínky, kdy žádné vlákno nelze spustit. Zablokování může být zásadním problémem při ladění.

Visual Studio poskytuje různé nástroje pro použití při ladění aplikace s více vlákny.

- Vlákna, jsou primární nástroje pro ladění vláken **vlákna** okna, značky vlákna ve zdrojových oknech, **paralelní zásobníky** okně **paralelního sledování** okno, a **umístění ladění** nástrojů. Další informace o **vlákna** okno a **umístění ladění** nástrojů, naleznete v tématu [návod: ladění pomocí okna vlákna](../debugger/how-to-use-the-threads-window.md). Další informace o použití **paralelní zásobníky** a **paralelní sledování** naleznete zde [Začínáme s laděním vícevláknových aplikacích](../debugger/get-started-debugging-multithreaded-apps.md). Obě témata ukazují, jak používat značky vlákna.
  
- Pro kód, který se používá [Task Parallel Library (TPL)](/dotnet/standard/parallel-programming/task-parallel-library-tpl) nebo [Concurrency Runtime](/cpp/parallel/concrt/concurrency-runtime/), jsou základními nástroji pro ladění **paralelní zásobníky** okno, **Paralelní sledování** okně a **úlohy** okno ( **úlohy** okna také podporuje JavaScript). Abyste mohli začít, najdete v článku [návod: ladění paralelní aplikace](../debugger/walkthrough-debugging-a-parallel-application.md) a [návod: ladění aplikace C++ AMP](/cpp/parallel/amp/walkthrough-debugging-a-cpp-amp-application). 

- Pro ladění vláken v GPU je primárním nástrojem **vlákna GPU** okna. Zobrazit [postupy: použití okna vláken GPU](../debugger/how-to-use-the-gpu-threads-window.md).  

- Pro procesy, jsou primární nástroje **připojit k procesu** dialogovém okně **procesy** okně a **umístění ladění** nástrojů.  
  
Visual Studio také poskytuje výkonné zarážky a trasování, což může být velmi užitečné při ladění aplikací s více vlákny. Podmínky zarážky a filtry můžete použít k umístění zarážek na jednotlivá vlákna. Zobrazit [pomocí zarážek](../debugger/using-breakpoints.md). 
  
Ladění aplikace s více vlákny s uživatelským rozhraním může být zvláště obtížné. V takovém případě zvažte spuštění aplikace na druhém počítači a použití vzdáleného ladění. Informace najdete v tématu [vzdálené ladění](../debugger/remote-debugging.md).  
  
## <a name="in-this-section"></a>V tomto oddílu
 [Začínáme s laděním vícevláknových aplikacích](../debugger/get-started-debugging-multithreaded-apps.md).  
 Seznámení s funkcemi, s důrazem na funkce v ladění vlákna **paralelní zásobníky** okno a **paralelní sledování** okna.

 [Nástroje pro ladění vláken a procesů](../debugger/debug-threads-and-processes.md)  
 Obsahuje seznam funkcí nástroje pro ladění vláken a procesů.  
  
 [Ladění více procesů](../debugger/debug-multiple-processes.md)  
 Vysvětluje, jak ladění více procesů.

 [Návod: Ladění pomocí okna vlákna](../debugger/how-to-use-the-threads-window.md).  
 Návod, který ukazuje způsob použití **vlákna** okno a **umístění ladění** nástrojů. 

 [Návod: Ladění paralelní aplikace](../debugger/walkthrough-debugging-a-parallel-application.md)  
 Návod, který ukazuje způsob použití **paralelní zásobníky** a **úlohy** systému windows.  
  
 [Postupy: Přepnutí na jiné vlákno během ladění](../debugger/how-to-switch-to-another-thread-while-debugging.md)  
 Tři způsoby, jak přepnout kontext ladění na jiný podproces.  
  
 [Postupy: Označení a odstranění označení vlákna](../debugger/how-to-flag-and-unflag-threads.md)  
 Opatřete značkou nebo příznakem vlákna, které chcete věnovat zvláštní pozornost při ladění.    
  
 [Postupy: Ladění na klastru s vysokým výkonem](../debugger/how-to-debug-on-a-high-performance-cluster.md)  
 Techniky ladění aplikace, která běží na vysoký výkon clusteru.  

 [Tipy k ladění vláken v nativním kódu](../debugger/tips-for-debugging-threads-in-native-code.md)  
 Jednoduché techniky, které mohou být užitečné při ladění nativních vláken. 

 [Postupy: Nastavení názvu vlákna v nativním kódu](../debugger/how-to-set-a-thread-name-in-native-code.md)  
 Pojmenujte vašeho vlákna, která se zobrazí v **vlákna** okna.  
  
 [Postupy: Nastavení názvu vlákna ve spravovaném kódu](../debugger/how-to-set-a-thread-name-in-managed-code.md)  
 Pojmenujte vašeho vlákna, která se zobrazí v **vlákna** okna. 
  
## <a name="related-sections"></a>Související oddíly  
 [Použití zarážek](../debugger/using-breakpoints.md)

- Použijte podmínky zarážky nebo filtry, pokud chcete ladit jednotlivá vlákna.  
  
- Zarážky s trasováním umožňuje trasování spuštění programu bez přerušení. To může být užitečné pro studium problémů například zablokování.  
  
  [Dělení na vlákna](/dotnet/standard/threading/index)  
  Práce s vlákny koncepty v [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] programování, včetně příkladu kódu.  
  
  [Multithreading u komponent](https://msdn.microsoft.com/Library/2fc31e68-fb71-4544-b654-0ce720478779)  
  Jak používat multithreading u [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] komponenty.  
  
  [Podpora multithreadingu ve starším kódu (Visual C++)](/cpp/parallel/multithreading-support-for-older-code-visual-cpp)  
  Práce s vlákny koncepty a příklady kódu pro programátory C++ používající knihovnu MFC.  
  
## <a name="see-also"></a>Viz také  
 [Ladění vláken a procesů](../debugger/debug-threads-and-processes.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)