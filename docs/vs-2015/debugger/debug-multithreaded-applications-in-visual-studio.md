---
title: Ladění vícevláknových aplikací v sadě Visual Studio | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.gputthreads
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- threading [Visual Studio], debugging
- debugging [Visual Studio], high-performance computing
- debugging [Visual Studio], multithreaded
- multithreaded debugging
- high-performance debugging
ms.assetid: 9d175bc2-1d95-4c47-9bc3-9755af968a9c
caps.latest.revision: 28
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4d841456ab95d06a7b586f7a8566f8530acbb021
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49897495"
---
# <a name="debug-multithreaded-applications-in-visual-studio"></a>Ladění vícevláknových aplikací v sadě Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vlákno je řada pokynů, pro které operační systém přiděluje čas procesoru. Každý proces, na kterém běží v operačním systému se skládá z alespoň jednoho vlákna. Procesy, které mají více než jedno vlákno, se nazývají s více vlákny.  
  
 Počítače s více procesory, vícejádrovými procesory nebo procesy využívající hyperthreading lze spustit více vláken současně. Paralelní zpracování více podprocesů může značně zlepšit výkon aplikace, ale to může také ztížit ladění protože zavádí potřebu sledovat více vláken.  
  
 Kromě toho multithreading přináší některé nové typy možných chyb. Často například dvě nebo více vláken mít přístup ke stejnému prostředku, ale pouze jedno vlákno může bezpečně přistupovat k prostředku najednou. Některé forma vzájemného vyloučení je nezbytné, abyste měli jistotu, že pouze jedno vlákno k prostředku najednou. Pokud nesprávně provedeného vzájemného vyloučení můžete vytvořit *zablokování* podmínky, kdy žádné vlákno nelze spustit. Zablokování může být zásadním problémem při ladění.  
  
 Visual Studio poskytuje **vlákna** oken, okno vlákna GPU, okno paralelního sledování a další funkce, které bylo vícevláknové ladění snazší. Tyto postupy je nejlepší způsob, jak Další informace o funkcích vláken. Zobrazit [návod: ladění vícevláknové aplikace](../debugger/walkthrough-debugging-a-multithreaded-application.md) a [návod: ladění aplikace C++ AMP](http://msdn.microsoft.com/library/40e92ecc-f6ba-411c-960c-b3047b854fb5).  
  
 Visual Studio také poskytuje výkonné zarážky a trasování, což může být velmi užitečné při ladění aplikací s více vlákny. Filtry zarážky slouží k umístění zarážek na jednotlivá vlákna. Zobrazit [použití zarážek](../debugger/using-breakpoints.md)  
  
 Ladění aplikace s více vlákny s uživatelským rozhraním může být zvláště obtížné. V takovém případě zvažte spuštění aplikace na druhém počítači a použití vzdáleného ladění. Informace najdete v tématu [vzdálené ladění](../debugger/remote-debugging.md).  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Ladění vláken a procesů](../debugger/debug-threads-and-processes.md)  
 Popisuje základní informace o ladění vláken a procesů.  
  
 [Ladění více procesů](../debugger/debug-multiple-processes.md)  
 Vysvětluje, jak ladění více procesů.  
  
 [Postupy: Použití okna vláken](../debugger/how-to-use-the-threads-window.md)  
 Vhodné procedury pro ladění vláken s **vlákna** okna.  
  
 [Postupy: Přepnutí na jiné vlákno během ladění](../debugger/how-to-switch-to-another-thread-while-debugging.md)  
 Tři způsoby, jak přepnout kontext ladění na jiný podproces.  
  
 [Postupy: Označení a odstranění označení vlákna](../debugger/how-to-flag-and-unflag-threads.md)  
 Opatřete značkou nebo příznakem vlákna, které chcete věnovat zvláštní pozornost při ladění.  
  
 [Postupy: Nastavení názvu vlákna v nativním kódu](../debugger/how-to-set-a-thread-name-in-native-code.md)  
 Pojmenujte vašeho vlákna, která se zobrazí v **vlákna** okna.  
  
 [Postupy: Nastavení názvu vlákna ve spravovaném kódu](../debugger/how-to-set-a-thread-name-in-managed-code.md)  
 Pojmenujte vašeho vlákna, která se zobrazí v **vlákna** okna.  
  
 [Návod: Ladění vícevláknové aplikace](../debugger/walkthrough-debugging-a-multithreaded-application.md).  
 Seznámení s funkcemi, s důrazem na funkce jak ladění vlákna do [!INCLUDE[vs_orcas_long](../includes/vs-orcas-long-md.md)].  
  
 [Postupy: Ladění na klastru s vysokým výkonem](../debugger/how-to-debug-on-a-high-performance-cluster.md)  
 Techniky ladění aplikace, která běží na vysoký výkon clusteru.  
  
 [Tipy k ladění vláken v nativním kódu](../debugger/tips-for-debugging-threads-in-native-code.md)  
 Jednoduché techniky, které mohou být užitečné při ladění nativních vláken.  
  
 [Použití okna úloh](../debugger/using-the-tasks-window.md)  
 Zobrazuje seznam všech objektů spravované nebo nativní úloh, včetně jejich stavu a dalších užitečných informací.  
  
 [Použití okna Paralelní zásobníky](../debugger/using-the-parallel-stacks-window.md)  
 Ukazuje volání zásobníků s více vlákny (nebo úlohami) v jednom zobrazení a také coalesces zásobníku segmentů, které jsou společné mezi vlákny (nebo úlohami).  
  
 [Návod: Ladění paralelní aplikace](../debugger/walkthrough-debugging-a-parallel-application.md)  
 Návod, který ukazuje, jak použít paralelní úkoly a Paralelní zásobníky systému windows.  
  
 [Postupy: Použití okna paralelního sledování](../debugger/how-to-use-the-parallel-watch-window.md)  
 Zkontrolujte hodnoty a výrazy napříč více vlákny.  
  
 [Postupy: Použití okna vláken GPU](../debugger/how-to-use-the-gpu-threads-window.md)  
 Prozkoumejte a pracujte s vlákny, která běží na GPU během ladění.  
  
## <a name="related-sections"></a>Související oddíly  
 [Použití zarážek](../debugger/using-breakpoints.md)  
 -   Použijte filtry zarážek, když chcete umístit zarážky na jednotlivá vlákna.  
  
- Zarážky s trasováním umožňuje trasování spuštění programu bez přerušení. To může být užitečné pro studium problémů například zablokování.  
  
  [Dělení na vlákna](http://msdn.microsoft.com/library/7b46a7d9-c6f1-46d1-a947-ae97471bba87)  
  Práce s vlákny koncepty v [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] programování, včetně příkladu kódu.  
  
  [Multithreading u komponent](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
  Jak používat multithreading u [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] komponenty.  
  
  [Podpora multithreadingu ve starším kódu (Visual C++)](http://msdn.microsoft.com/library/24425b1f-5031-4c6b-aac7-017115a40e7c)  
  Práce s vlákny koncepty a příklady kódu pro programátory C++ používající knihovnu MFC.  
  
## <a name="see-also"></a>Viz také  
 [Ladění vláken a procesů](../debugger/debug-threads-and-processes.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)



