---
title: Sdílení zpětného volání protokolu Unity s VSTU | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- tgt-pltfrm-cross-plat
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d71f906-6e50-4399-b59b-d38c6dfef7ee
caps.latest.revision: 5
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: 8e1e0f2062195830443a169c67d9b75d2b1915ec
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669688"
---
# <a name="share-the-unity-log-callback-with-vstu"></a>Sdílení zpětného volání protokolu Unity s VSTU
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [sdílení zpětného volání protokolu Unity s VSTU](https://docs.microsoft.com/visualstudio/cross-platform/share-the-unity-log-callback-with-vstu).  
  
  
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

