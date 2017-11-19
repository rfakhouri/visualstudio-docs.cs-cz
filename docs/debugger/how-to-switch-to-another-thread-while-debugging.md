---
title: "Postupy: přepnutí na jiné vlákno během ladění | Microsoft Docs"
ms.custom: 
ms.date: 04/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords: threads, switching [debugging]
ms.assetid: 5cd76c52-76fa-4fcc-b37e-e9f0ecac0e9e
caps.latest.revision: "26"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 14432de4519ed49292810af5f96399bbf87e43cd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-switch-to-another-thread-while-debugging-in-visual-studio"></a>Postupy: přepnutí na jiné vlákno během ladění v sadě Visual Studio
Při ladění vícevláknové aplikace, můžete přejít z vlákno, které pracujete s na jiné vlákno jedné z několika metod.

> [!NOTE]
> Pokud chcete určit pořadí, ve kterém vláken spuštění, budete muset [ukotvení a odblokování vláken](/debugger/get-started-debugging-multithreaded-apps.md).

Při kontrole vláken v editoru kódu a jiné vícevláknové ladění windows žlutá šipka označuje aktuální vlákno. Zelenou šipku s složené tail znamená, že má jiný aktuální vlákno aktuálního kontextu ladicího programu.
  
### <a name="to-switch-to-any-thread-that-appears"></a>Přejděte na všechny vlákno, které se zobrazí 
  
-   V **vláken** nebo **paralelního sledování** okna, klikněte dvakrát na vlákno.  
  
### <a name="to-switch-to-a-thread-in-a-source-window"></a>Chcete-li přepnout na vlákno v okně zdroje  
  
-   V levém oddělovací mezery, klikněte pravým tlačítkem myši ikonu značky vlákno ![vlákno značky](../debugger/media/dbg-thread-marker.png "ThreadMarker"), přejděte na příkaz **přepnout**a pak klikněte na název daném vláknu, ke kterému chcete přejít . Místní nabídky zobrazuje pouze vláken v tomto konkrétní umístění.  
  
     Pokud žádný přístup z více vláken značky se zobrazí, klikněte pravým tlačítkem myši **vláken** okna a ověřte, že **zobrazit vláken ve zdroji** je vybrána.  
  
### <a name="to-switch-to-a-thread-in-the-debug-location-toolbar"></a>Chcete-li přepnout na vlákno v panelu nástrojů ladění umístění  
  
1.  Na **ladění umístění** nástrojů, klikněte na tlačítko **vláken** seznamu.  
  
2.  V seznamu klikněte na vlákno, ke kterému chcete přejít.  
  
## <a name="see-also"></a>Viz také  
 [Ladění vícevláknových aplikací](../debugger/debug-multithreaded-applications-in-visual-studio.md)