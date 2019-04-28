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
ms.openlocfilehash: b6992790be2a447c1539024d21d751041d43da2f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62843911"
---
# <a name="add-an-attribute-to-a-project-item"></a>Přidání atributu do položky projektu
Metody <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.GetItemAttribute%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetItemAttribute%2A> získat a nastavit hodnotu vlastnosti položky projektu. SetItemAttribute vytvoří atribut Pokud ještě neexistuje, jeho přidání do metadata položky projektu.

## <a name="add-an-attribute-to-a-project-item"></a>Přidání atributu do položky projektu

- Následující kód používá <xref:EnvDTE.DTE> automatizační objekt a <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetItemAttribute%2A> metoda pro přidání atributu do položky projektu. ID položky projektu se získávají z název položky projektu "program.cs". Atribut "MyAttribute" je přidána do tuto položku projektu a byla přidělena hodnota "MyValue".

    ```csharp
    EnvDTE.DTE dte = (EnvDTE.DTE)Package.GetGlobalService(typeof(EnvDTE.DTE));
    EnvDTE.Project project = dte.Solution.Projects.Item(1);

    string uniqueName = project.UniqueName;
    IVsSolution solution = (IVsSolution)Package.GetGlobalService(typeof(SVsSolution));
    IVsHierarchy hierarchy;
    solution.GetProjectOfUniqueName(uniqueName, out hierarchy);
    IVsBuildPropertyStorage buildPropertyStorage = hierarchy as IVsBuildPropertyStorage;
    if (buildPropertyStorage != null)
    {
        uint itemId;
        string fullPath = (string)project.ProjectItems.Item("Program.cs").Properties.Item("FullPath").Value;
        hierarchy.ParseCanonicalName(fullPath, out itemId);
        buildPropertyStorage.SetItemAttribute(itemId, "MyAttribute", "MyValue");
    }

    ```

## <a name="see-also"></a>Viz také:
- [Zachovat data v souboru projektu MSBuild](../extensibility/internals/persisting-data-in-the-msbuild-project-file.md)
