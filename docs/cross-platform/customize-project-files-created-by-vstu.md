---
title: Přizpůsobení souborů projektu vytvořených nástrojem VSTU | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-unity-tools
ms.topic: conceptual
ms.assetid: 60b8cc1d-cacc-404d-b768-77e81bc354f8
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- unity
ms.openlocfilehash: 7393d023b8c581b95d3ac39b8501ca9dbb30228d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31060266"
---
# <a name="customize-project-files-created-by-vstu"></a>Přizpůsobení souborů projektu vytvořených nástrojem VSTU
Visual Studio Tools for Unity poskytuje Unity stylu zpětné volání při generování souboru projektu. Zaregistrovat se `VisualStudioIntegration.ProjectFileGeneration` událostí k úpravě souboru projektu vždy, když jsou obnoveny.

## <a name="demonstrates"></a>Demonstruje
 Postup přizpůsobení souborů projektu sady Visual Studio generované Visual Studio Tools for Unity.

## <a name="example"></a>Příklad

```csharp
using System;
using System.IO;
using System.Linq;
using System.Text;
using System.Xml.Linq;

using UnityEngine;
using UnityEditor;

using SyntaxTree.VisualStudio.Unity.Bridge;

[InitializeOnLoad]
public class ProjectFileHook
{
    // necessary for XLinq to save the xml project file in utf8
    class Utf8StringWriter : StringWriter
    {
        public override Encoding Encoding
        {
            get { return Encoding.UTF8; }
        }
    }

    static ProjectFileHook()
    {
        ProjectFilesGenerator.ProjectFileGeneration += (string name, string content) =>
        {
            // parse the document and make some changes
            var document = XDocument.Parse(content);
            document.Root.Add(new XComment("FIX ME"));

            // save the changes using the Utf8StringWriter
            var str = new Utf8StringWriter();
            document.Save(str);

            return str.ToString();
        };
    }
}
```

## <a name="see-also"></a>Viz také
 [Příklad: Zpětné volání protokolu](../cross-platform/share-the-unity-log-callback-with-vstu.md)
