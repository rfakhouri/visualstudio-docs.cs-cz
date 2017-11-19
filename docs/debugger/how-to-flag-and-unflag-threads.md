---
title: "Postupy: označení a odstranění označení vlákna | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
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
helpviewer_keywords: treads, switching [debugging]
ms.assetid: 952d579d-6911-413e-b3e5-54e7e797e70c
caps.latest.revision: "33"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d4ff3c0d06d7f668ad3d61f785320def8b9ddd0e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-flag-and-unflag-threads"></a>Postupy: Označení a odstranění označení vlákna
Můžete označit příznakem vlákno, které chcete udělit zvláštní pozornost označením ikonou v **vláken**, **paralelní zásobníky** (zobrazení vláken), **paralelního sledování**a  **Vlákna GPU** systému windows. Tato ikona vám může pomoct a ostatní označení vlákna odlišit od jiných vláken.  
  
Označení vláken také přijímat zvláštní zacházení v **vláken** seznam na **ladění umístění** panelu nástrojů a v dalších vícevláknové ladění systému windows. Můžete zobrazit všechna vlákna nebo pouze označení vláken v **vláken** seznamu nebo v dalších oknech.
  
### <a name="to-flag-or-unflag-a-thread"></a>Příznak nebo odstranění označení vlákna 
  
-   V **vláken** nebo **paralelního sledování** okně Najít vlákno, které vás zajímají a kliknutím na ikonu příznaku zaškrtněte nebo zrušte příznak. 
-   V **paralelní zásobníky** okna, klikněte pravým tlačítkem na vlákno nebo skupinu vláken a vyberte **příznak nebo <thread>**  nebo **Unflag / <thread>** .
  
### <a name="to-unflag-all-threads"></a>K odstranění označení všechna vlákna  
  
-   V **vláken** okna, klikněte pravým tlačítkem na libovolného vlákna a pak klikněte na **odstranění označení všechna vlákna**.
-   V **paralelního sledování** vyberte všechny příznakem vláken, klikněte pravým tlačítkem a vyberte **Unflag**.  
  
### <a name="to-display-only-flagged-threads"></a>Chcete-li zobrazit pouze označení vlákna  
  
-   Vyberte **zobrazit příznakem vláken pouze** tlačítko v jednom z více vláken ladění windows.  
  
### <a name="to-flag-just-my-code"></a>Chcete-li příznak pouze můj kód  
  
1.  Na panelu nástrojů v horní části **vláken** okně klikněte na ikonu vlajky.  
  
2.  V rozevíracím seznamu, klikněte na **pouze můj kód příznak**.  
  
### <a name="to-flag-threads-that-are-associated-with-selected-modules"></a>Chcete-li příznak vláken, které jsou spojeny s vybrané moduly  
  
1.  Na panelu nástrojů **vláken** okně klikněte na ikonu vlajky.  
  
2.  V rozevíracím seznamu, klikněte na **příznak vlastního modulu výběru**.  
  
3.  V **vyberte moduly** dialogovém okně vyberte moduly, které chcete.  
  
4.  (Volitelné) V **vyhledávání** zadejte řetězec pro vyhledání určitých modulech.  
  
5.  Click **OK**.  
  
## <a name="see-also"></a>Viz také  
 [Ladění vícevláknových aplikací](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Začínáme ladění vícevláknové aplikace](../debugger/get-started-debugging-multithreaded-apps.md)  
 [Návod: Ladění vícevláknových aplikací pomocí okna vláken](../debugger/how-to-use-the-threads-window.md)