---
title: Ladění vícevláknových aplikací
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
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
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 8cb43c9a32f3dfd0a6383d466f7cd283acf0ab3a
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65691284"
---
# <a name="debug-multithreaded-applications-in-visual-studio"></a>Ladění vícevláknových aplikací v sadě Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vlákno je řada pokynů, pro které operační systém přiděluje čas procesoru. Každý proces, na kterém běží v operačním systému se skládá z alespoň jednoho vlákna. Procesy, které mají více než jedno vlákno, se nazývají s více vlákny.

 Počítače s více procesory, vícejádrovými procesory nebo procesy využívající hyperthreading lze spustit více vláken současně. Paralelní zpracování více podprocesů může značně zlepšit výkon aplikace, ale to může také ztížit ladění protože zavádí potřebu sledovat více vláken.

 Kromě toho multithreading přináší některé nové typy možných chyb. Často například dvě nebo více vláken mít přístup ke stejnému prostředku, ale pouze jedno vlákno může bezpečně přistupovat k prostředku najednou. Některé forma vzájemného vyloučení je nezbytné, abyste měli jistotu, že pouze jedno vlákno k prostředku najednou. Pokud nesprávně provedeného vzájemného vyloučení můžete vytvořit *zablokování* podmínky, kdy žádné vlákno nelze spustit. Zablokování může být zásadním problémem při ladění.

 Visual Studio poskytuje **vlákna** oken, okno vlákna GPU, okno paralelního sledování a další funkce, které bylo vícevláknové ladění snazší. Tyto postupy je nejlepší způsob, jak Další informace o funkcích vláken. Zobrazit [názorný postup: Ladění vícevláknových aplikacích](../debugger/walkthrough-debugging-a-multithreaded-application.md) a [názorný postup: Ladění aplikace C++ AMP](https://msdn.microsoft.com/library/40e92ecc-f6ba-411c-960c-b3047b854fb5).

 Visual Studio také poskytuje výkonné zarážky a trasování, což může být velmi užitečné při ladění aplikací s více vlákny. Filtry zarážky slouží k umístění zarážek na jednotlivá vlákna. Zobrazit [použití zarážek](../debugger/using-breakpoints.md)

 Ladění aplikace s více vlákny s uživatelským rozhraním může být zvláště obtížné. V takovém případě zvažte spuštění aplikace na druhém počítači a použití vzdáleného ladění. Informace najdete v tématu [vzdálené ladění](../debugger/remote-debugging.md).

## <a name="in-this-section"></a>V tomto oddílu
 [Ladění vláken a procesů](../debugger/debug-threads-and-processes.md) vysvětluje základní informace o ladění vláken a procesů.

 [Ladění více procesů](../debugger/debug-multiple-processes.md) vysvětluje, jak ladění více procesů.

 [Postupy: Použití okna vláken](../debugger/how-to-use-the-threads-window.md) vhodné procedury pro ladění vláken s **vlákna** okna.

 [Postupy: Přepnout na jiné vlákno během ladění](../debugger/how-to-switch-to-another-thread-while-debugging.md) tři způsoby, jak přepnout kontext ladění na jiný podproces.

 [Postupy: Příznak a odstranění označení vlákna](../debugger/how-to-flag-and-unflag-threads.md) opatřete značkou nebo příznakem vlákna, které chcete věnovat zvláštní pozornost při ladění.

 [Postupy: Nastavení názvu vlákna v nativním kódu](../debugger/how-to-set-a-thread-name-in-native-code.md) dát název, který se zobrazí v vašeho vlákna **vlákna** okna.

 [Postupy: Nastavení názvu vlákna do spravovaného kódu](../debugger/how-to-set-a-thread-name-in-managed-code.md) dát název, který se zobrazí v vašeho vlákna **vlákna** okna.

 [Návod: Ladění vícevláknových aplikacích](../debugger/walkthrough-debugging-a-multithreaded-application.md).
Seznámení s funkcemi, s důrazem na funkce jak ladění vlákna do [!INCLUDE[vs_orcas_long](../includes/vs-orcas-long-md.md)].

 [Postupy: Ladění na vysoký výkon clusteru](../debugger/how-to-debug-on-a-high-performance-cluster.md) techniky ladění aplikace, která běží na vysoký výkon clusteru.

 [Tipy pro ladění vláken v nativním kódu](../debugger/tips-for-debugging-threads-in-native-code.md) jednoduché techniky, které mohou být užitečné při ladění nativních vláken.

 [Používání okna úloh](../debugger/using-the-tasks-window.md) zobrazuje seznam všech objektů spravované nebo nativní úloh, včetně jejich stavu a dalších užitečných informací.

 [Použití okna paralelní zásobníky](../debugger/using-the-parallel-stacks-window.md) ukazuje volání zásobníků s více vlákny (nebo úlohami) v jednom zobrazení a také coalesces zásobníku segmentů, které jsou společné mezi vlákny (nebo úlohami).

 [Návod: Ladění paralelní aplikace](../debugger/walkthrough-debugging-a-parallel-application.md) návod, který ukazuje, jak použít paralelní úkoly a Paralelní zásobníky systému windows.

 [Postupy: Použití okna paralelního sledování](../debugger/how-to-use-the-parallel-watch-window.md) zkontrolujte hodnoty a výrazy napříč více vlákny.

 [Postupy: Použití okna vláken GPU](../debugger/how-to-use-the-gpu-threads-window.md) vyhledejte a práce s vlákny, která běží na GPU během ladění.

## <a name="related-sections"></a>Související oddíly

[Použití zarážek](../debugger/using-breakpoints.md)
- Použijte filtry zarážek, když chcete umístit zarážky na jednotlivá vlákna.

- Zarážky s trasováním umožňuje trasování spuštění programu bez přerušení. To může být užitečné pro studium problémů například zablokování.

  [Práce s vlákny](https://msdn.microsoft.com/library/7b46a7d9-c6f1-46d1-a947-ae97471bba87) v koncepce práce s vlákny [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] programování, včetně příkladu kódu.

  [Multithreading u komponent](https://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779) jak používat multithreading u [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] komponenty.

  [Podpora multithreadingu ve starším kódu (Visual C++)](https://msdn.microsoft.com/library/24425b1f-5031-4c6b-aac7-017115a40e7c) dělení na vlákna koncepty a příklady kódu pro programátory C++ používající knihovnu MFC.

## <a name="see-also"></a>Viz také
 [Ladění vláken a procesů](../debugger/debug-threads-and-processes.md) [vzdálené ladění](../debugger/remote-debugging.md)
