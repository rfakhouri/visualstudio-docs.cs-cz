---
title: 'Postupy: Nastavení názvu vlákna ve spravovaném kódu | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Thread.Name property
- threading [Visual Studio], names
- thread names
- debugging [Visual Studio], threads
ms.assetid: c0c4d74a-0314-4b71-81c9-b0b019347ab8
caps.latest.revision: 31
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: b800fbd2f39d75f110a059c70b87a203eb72e7d6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68157671"
---
# <a name="how-to-set-a-thread-name-in-managed-code"></a>Postupy: Nastavení názvu vlákna ve spravovaném kódu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pojmenování vlákna je možné v jakékoli edici sady Visual Studio. Pojmenování vláken je užitečné pro udržování přehledu o vlákna **vlákna** okna. Vzhledem k tomu, **vlákna** okno není k dispozici v edicích Visual Studio Express, pojmenování vlákno má malý nástroj ve verzích Express.  
  
 Chcete-li nastavení názvu vlákna ve spravovaném kódu, použijte <xref:System.Threading.Thread.Name%2A> vlastnost.  
  
## <a name="example"></a>Příklad  
  
```  
Public Class Needle  
    ' This method will be called when the thread is started.  
    Sub Baz()  
        Console.WriteLine("Needle Baz is running on another thread")  
    End Sub  
End Class  
  
Sub Main()  
    Console.WriteLine("Thread Simple Sample")  
    Dim oNeedle As New Needle()  
   ' Create a Thread object.   
    Dim oThread As New System.Threading.Thread(AddressOf oNeedle.Baz)  
    ' Set the Thread name to "MainThread".  
    oThread.Name = "MainThread"  
    ' Starting the thread invokes the ThreadStart delegate  
    oThread.Start()  
End Sub  
```  
  
## <a name="see-also"></a>Viz také  
 [Ladění vícevláknových aplikací](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Postupy: Nastavení názvu vlákna v nativním kódu](../debugger/how-to-set-a-thread-name-in-native-code.md)
