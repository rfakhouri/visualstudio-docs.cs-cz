---
title: Ověření podtypů projektu v době běhu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project subtypes
- check subtypes
ms.assetid: b87780ec-36a3-4e9a-9ee2-7abdc26db739
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b8898da6850c01c1a248b57b0fbc5f46be2a8ff4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31136826"
---
# <a name="verifying-subtypes-of-a-project-at-run-time"></a>Ověření podtypů projektu v době běhu
VSPackage, který závisí na dílčí vlastních projektů by měla obsahovat logiky hledání, která podtypu tak, aby ho může selhat řádně Pokud dílčí není k dispozici. Následující postup ukazuje, jak ověřit přítomnost zadaným podtypem.  
  
### <a name="to-verify-the-presence-of-a-subtype"></a>K ověření přítomnosti podtypu  
  
1.  Získat hierarchii projekt z projektu a řešení objekty jako <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> objekt přidáním následující kód do vaší VSPackage.  
  
    ```  
    EnvDTE.DTE dte;  
    dte = (EnvDTE.DTE)Package.GetGlobalService(typeof(EnvDTE.DTE));  
  
    EnvDTE.Project project;  
    project = dte.Solution.Projects.Item(1);  
  
    IVsSolution solution;  
    solution = (IVsSolution)Package.GetGlobalService(typeof(SVsSolution));  
  
    IVsHierarchy hierarchy;  
    hierarchy = solution.GetProjectOfUniqueName(project.UniqueName);  
  
    ```  
  
2.  Hierarchie, které chcete převést <xref:Microsoft.VisualStudio.Shell.Flavor.IVsAggregatableProjectCorrected> rozhraní.  
  
    ```  
    IVsAggregatableProjectCorrected AP;  
    AP = hierarchy as IVsAggregatableProjectCorrected;  
  
    ```  
  
3.  Získání seznamu typu projektu identifikátory GUID vyvoláním <xref:Microsoft.VisualStudio.Shell.Flavor.IVsAggregatableProjectCorrected.GetAggregateProjectTypeGuids%2A>.  
  
    ```  
    string projTypeGuids = AP.GetAggregateProjectTypeGuids().ToUpper();  
  
    ```  
  
4.  Zkontrolujte seznam identifikátoru GUID zadaným podtypem.  
  
    ```  
    // Replace the string "MyGUID" with the GUID of the subtype.  
    string guidMySubtype = "MyGUID";  
    if (projTypeGuids.IndexOf(guidMySubtype) > 0)  
    {  
        // The specified subtype is present.  
    }  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Projekt podtypů](../extensibility/internals/project-subtypes.md)   
 [Návrh podtypů projektu](../extensibility/internals/project-subtypes-design.md)   
 [Vlastnosti a metody rozšířené prostřednictvím podtypů projektů](../extensibility/internals/properties-and-methods-extended-by-project-subtypes.md)