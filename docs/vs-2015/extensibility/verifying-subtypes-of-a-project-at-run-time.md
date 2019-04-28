---
title: Ověření podtypů projektu za běhu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project subtypes
- check subtypes
ms.assetid: b87780ec-36a3-4e9a-9ee2-7abdc26db739
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 1e3940097ac53255b7bdd2c12c9ccc64605016e1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62584902"
---
# <a name="verifying-subtypes-of-a-project-at-run-time"></a>Ověření podtypů projektu za běhu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

VSPackage, která závisí na podtyp vlastní projekt by měl obsahovat logiku k vyhledání, která podtypu tak, aby se nemusí zdařit řádně Pokud Podtyp není k dispozici. Následující postup ukazuje, jak ověřit přítomnost zadaným podtypem.  
  
### <a name="to-verify-the-presence-of-a-subtype"></a>Chcete-li ověřit přítomnost podtyp  
  
1. Získat hierarchii projektu z projektu a řešení objektů jako <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> objektu přidáním následujícího kódu do vašeho balíčku VSPackage.  
  
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
  
2. Přetypování hierarchii <xref:Microsoft.VisualStudio.Shell.Flavor.IVsAggregatableProjectCorrected> rozhraní.  
  
    ```  
    IVsAggregatableProjectCorrected AP;  
    AP = hierarchy as IVsAggregatableProjectCorrected;  
  
    ```  
  
3. Získání seznamu identifikátorů GUID typu projektu vyvoláním <xref:Microsoft.VisualStudio.Shell.Flavor.IVsAggregatableProjectCorrected.GetAggregateProjectTypeGuids%2A>.  
  
    ```  
    string projTypeGuids = AP.GetAggregateProjectTypeGuids().ToUpper();  
  
    ```  
  
4. Identifikátor GUID zadaným podtypem najdete v seznamu.  
  
    ```  
    // Replace the string "MyGUID" with the GUID of the subtype.  
    string guidMySubtype = "MyGUID";  
    if (projTypeGuids.IndexOf(guidMySubtype) > 0)  
    {  
        // The specified subtype is present.  
    }  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Podtypy projektů](../extensibility/internals/project-subtypes.md)   
 [Návrh podtypů projektů](../extensibility/internals/project-subtypes-design.md)   
 [Vlastnosti a metody rozšířené prostřednictvím podtypů projektů](../extensibility/internals/properties-and-methods-extended-by-project-subtypes.md)
