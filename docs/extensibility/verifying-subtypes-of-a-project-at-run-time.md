---
title: "Ověření podtypů projektu v době běhu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project subtypes
- check subtypes
ms.assetid: b87780ec-36a3-4e9a-9ee2-7abdc26db739
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2e4ebcf8ca85c0ed6face82dfd91f8c5266013f6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
 [Vlastnosti a metody prodloužena podtypů projektu](../extensibility/internals/properties-and-methods-extended-by-project-subtypes.md)