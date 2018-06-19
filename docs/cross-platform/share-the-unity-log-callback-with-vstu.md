---
title: Sdílení zpětného volání protokolu Unity s VSTU | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-unity-tools
ms.topic: conceptual
ms.assetid: 5d71f906-6e50-4399-b59b-d38c6dfef7ee
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- unity
ms.openlocfilehash: 31fa20bd4fd5a28e705198f9112e309e627871cf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31060002"
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
