---
title: "Sdílení zpětného volání protokolu Unity s VSTU | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d71f906-6e50-4399-b59b-d38c6dfef7ee
caps.latest.revision: "2"
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload: unity
ms.openlocfilehash: 6c078affefbb24a9fbbb65c854911f4b91f12183
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="share-the-unity-log-callback-with-vstu"></a>Sdílení zpětného volání protokolu Unity s VSTU
Visual Studio Tools for Unity registruje zpětné volání protokolu Unity mohli Streamovat její konzole k sadě Visual Studio. Pokud editor skriptů také zaregistrovat zpětné volání protokolu Unity, zpětného volání VSTU může narušovat vaší zpětné volání. Aby tato možnost, použijte `VisualStudioIntegration.LogCallback` událostí spolupracovat s VSTU.  

## <a name="demonstrates"></a>Demonstruje  
 Tom, jak sdílet zpětné volání protokolu Unity vytvořené Visual Studio Tools for Unity.  

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
