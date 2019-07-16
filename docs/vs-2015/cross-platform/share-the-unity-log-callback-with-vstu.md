---
title: Sdílení zpětného volání protokolu Unity s VSTU | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-unity-tools
ms.topic: conceptual
ms.assetid: 5d71f906-6e50-4399-b59b-d38c6dfef7ee
caps.latest.revision: 5
author: conceptdev
ms.author: crdun
manager: jillfra
ms.openlocfilehash: b58d693980ffc55ccfe613d52e868bccca9908b8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68145738"
---
# <a name="share-the-unity-log-callback-with-vstu"></a>Sdílení zpětného volání protokolu Unity s VSTU
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio Tools for Unity zaregistruje zpětné volání protokolu Unity Streamovat konzoly do sady Visual Studio. Pokud editor skriptů také zaregistrovat zpětné volání protokolu Unity, zpětné volání VSTU může narušit zpětného volání. Aby tato možnost, použijte `VisualStudioIntegration.LogCallback` události spolupracovat s VSTU.  
  
## <a name="demonstrates"></a>Demonstruje  
 Jak sdílet zpětného volání protokolu Unity, vytvoří Visual Studio Tools for Unity.  
  
## <a name="example"></a>Příklad  
  
```csharp  
using System;  
  
using UnityEngine;  
using UnityEditor;  
  
using SyntaxTree.VisualStudio.Unity.Bridge;  
  
[InitializeOnLoad]  
public class LogCallbackHook  
{  
    static LogCallbackHook()  
    {  
        VisualStudioIntegration.LogCallback += (string condition, string trace, LogType type) =>  
        {  
            // place code that implements your log callback here  
        };  
    }  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Příklad: Generování souboru projektu](../cross-platform/customize-project-files-created-by-vstu.md)
