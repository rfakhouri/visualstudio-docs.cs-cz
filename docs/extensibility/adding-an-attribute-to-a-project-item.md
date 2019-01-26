---
title: Přidání atributu do položky projektu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- attributes [Visual Studio], adding to a project item
ms.assetid: 404a71d5-cce5-44e7-9eaf-d747c794fedb
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c1195299ae63ddb2e14d36fffe79bbc06b909072
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55003042"
---
# <a name="add-an-attribute-to-a-project-item"></a>Přidání atributu do položky projektu
Metody <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.GetItemAttribute%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetItemAttribute%2A> získat a nastavit hodnotu vlastnosti položky projektu. SetItemAttribute vytvoří atribut Pokud ještě neexistuje, jeho přidání do metadata položky projektu.  
  
## <a name="add-an-attribute-to-a-project-item"></a>Přidání atributu do položky projektu  
  
-   Následující kód používá <xref:EnvDTE.DTE> automatizační objekt a <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetItemAttribute%2A> metoda pro přidání atributu do položky projektu. ID položky projektu se získávají z název položky projektu "program.cs". Atribut "MyAttribute" je přidána do tuto položku projektu a byla přidělena hodnota "MyValue".  
  
    ```csharp  
    EnvDTE.DTE dte = (EnvDTE.DTE)Package.GetGlobalService(typeof(EnvDTE.DTE));  
    EnvDTE.Project project = dte.Solution.Projects.Item(1);  
  
    string uniqueName = project.UniqueName;  
    IVsSolution solution =     (IVsSolution)Package.GetGlobalService(typeof(SVsSolution));  
    IVsHierarchy hierarchy;  
    solution.GetProjectOfUniqueName(uniqueName, out hierarchy);  
    IVsBuildPropertyStorage buildPropertyStorage = hierarchy as IVsBuildPropertyStorage;  
    if (buildPropertyStorage != null)  
    {  
        uint itemId;  
        string fullPath =         (string)project.ProjectItems.Item("Program.cs").Properties.Item("FullPath").Value;  
        hierarchy.ParseCanonicalName(fullPath, out itemId);  
        buildPropertyStorage.SetItemAttribute(  
            itemId, "MyAttribute", "MyValue");  
    }  
  
    ```  
  
## <a name="see-also"></a>Viz také:  
 [Zachovat data v souboru projektu MSBuild](../extensibility/internals/persisting-data-in-the-msbuild-project-file.md)