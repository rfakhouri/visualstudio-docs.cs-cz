---
title: Přepnutí na jiné vlákno během ladění
ms.custom: seodec18
ms.date: 04/27/2017
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- threads, switching [debugging]
ms.assetid: 5cd76c52-76fa-4fcc-b37e-e9f0ecac0e9e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 163d14de4880ed1c5e2ae6a3170ec5ae1ae47485
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55005186"
---
# <a name="how-to-switch-to-another-thread-while-debugging-in-visual-studio-c-visual-basic-c"></a>Postupy: Přepnutí na jiné vlákno během ladění v sadě Visual Studio (C#, Visual Basic, C++)
Při ladění aplikace s více vlákny, můžete použít některou z několika metod přepnutí z vlákna, které jste pracovali jste se do jiného vlákna.

> [!NOTE]
> Pokud chcete určit pořadí, ve kterém spuštění vlákna, budete muset [zablokovat a odblokovat vlákna](../debugger/get-started-debugging-multithreaded-apps.md).

Při kontrole vláken v editoru kódu a jiné vícevláknové ladění systému windows, žlutá šipka označuje aktuální vlákno. Zelená šipka s vlnitým ocáskem znamená, že není aktuální vlákno má aktuální kontext ladicího programu.
  
### <a name="to-switch-to-any-thread-that-appears"></a>Chcete-li přepnout do libovolného vlákna, která se zobrazí 
  
-   V **vlákna** nebo **paralelní sledování** okna, dvakrát klikněte na vlákno.  
  
### <a name="to-switch-to-a-thread-in-a-source-window"></a>Chcete-li přepnout na vlákno v okně zdroje  
  
-   V levém hřbetu, klikněte pravým tlačítkem na ikonu značky vlákna ![značky vlákna](../debugger/media/dbg-thread-marker.png "ThreadMarker"), přejděte na **přepnout na**a pak klikněte na název tohoto vlákna, do kterého chcete přejít . V místní nabídce zobrazí vlákna v tomto konkrétním umístění.  
  
     Pokud se nezobrazí žádné značky vlákna, klepněte pravým tlačítkem myši **vlákna** okno a ověřte, že **zobrazit vlákna ve zdroji** zaškrtnuto.  
  
### <a name="to-switch-to-a-thread-in-the-debug-location-toolbar"></a>Chcete-li přepnout na vlákno na panelu nástrojů umístění ladění  
  
1.  Na **umístění ladění** nástrojů, klikněte na tlačítko **vlákna** seznamu.  
  
2.  V seznamu klikněte na tlačítko vlákna, do kterého chcete přejít.  
  
## <a name="see-also"></a>Viz také  
 [Ladění vícevláknových aplikací](../debugger/debug-multithreaded-applications-in-visual-studio.md)
