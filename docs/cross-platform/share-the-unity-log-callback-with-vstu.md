---
title: Sdílení zpětného volání protokolu Unity s VSTU | Dokumentace Microsoftu
ms.custom: ''
ms.date: 07/26/2018
ms.technology: vs-unity-tools
ms.topic: conceptual
ms.assetid: 5d71f906-6e50-4399-b59b-d38c6dfef7ee
author: johmil
ms.author: therealjohn
manager: crdun
ms.workload:
- unity
ms.openlocfilehash: 7717dd1c95d77437f21d5d12e44d44c3dd3aa69e
ms.sourcegitcommit: 150fa6ec89ea2d086c0af9ababbaf6103a12eff1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/06/2018
ms.locfileid: "52953912"
---
# <a name="share-the-unity-log-callback-with-vstu"></a>Sdílení zpětného volání protokolu Unity s VSTU
Visual Studio Tools for Unity zaregistruje zpětné volání protokolu Unity Streamovat konzoly do sady Visual Studio. Pokud editor skriptů také zaregistrovat zpětné volání protokolu Unity, zpětné volání VSTU může narušit zpětného volání. Aby tato možnost, použijte `VisualStudioIntegration.LogCallback` události spolupracovat s VSTU.

## <a name="demonstrates"></a>Demonstruje
 Jak sdílet zpětného volání protokolu Unity, vytvoří Visual Studio Tools for Unity.

## <a name="example"></a>Příklad

```csharp
#if ENABLE_VSTU
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
#endif
```

## <a name="see-also"></a>Viz také:
 [Příklad: Generování souboru projektu](../cross-platform/customize-project-files-created-by-vstu.md)
