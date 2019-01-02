---
title: Projekt modelování | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- automation [Visual Studio SDK], implementing project objects
- project models, automation
ms.assetid: c8db8fdb-88c1-4b12-86fe-f3c30a18f9ee
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d835ee2062a6feec2fbb13991cc448b0b0b7b7a1
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53968375"
---
# <a name="project-modeling"></a>Modelování projektu
Dalším krokem v poskytování automatizace pro váš projekt je implementovat objekty standardní projektu: <xref:EnvDTE.Projects> a `ProjectItems` kolekce; `Project` a <xref:EnvDTE.ProjectItem> ; a zbývající objekty, které jsou jedinečné pro danou implementaci. Tyto standardní objekty jsou definovány v souboru Dteinternal.h. Implementace standardní objekty je k dispozici v ukázce BscPrj. Tyto třídy jako modely můžete použít k vytvoření vlastní projekt standard objekty, které stojí vedle sebe s projektu objekty z jiných typů projektů.  
  
 Spotřebitel automatizace předpokládá se, abyste mohli volat <xref:EnvDTE.Solution>("`<UniqueProjName>")` a <xref:EnvDTE.ProjectItems> (`n`) kde n je číslo indexu pro získání konkrétní projekt v řešení. Volání této služby automation způsobí, že prostředí pro volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.GetProperty%2A> na hierarchii příslušný projekt VSITEMID_ROOT předání jako parametru ItemID a VSHPROPID_ExtObject jako parametr VSHPROPID. `IVsHierarchy::GetProperty` Vrátí `IDispatch` ukazatel na objekt automatizace poskytování základních `Project` rozhraní, které jste implementovali.  
  
 Tady je syntaxe `IVsHierarchy::GetProperty`.  
  
 `HRESULT GetProperty (`  
  
 `VSITEMID` `itemid`,  
  
 `VSHPROPID` `propid`,  
  
 `VARIANT``*pvar`  
  
 `);`  
  
 Podle vnoření projekty a kolekce k vytvoření skupiny položek projektu. Hierarchie vypadá takto.  
  
```  
Projects  
  |- Project  
      |- ProjectItems (a collection of ProjectItem)  
          |- ProjectItem (single object) or ProjectItems (another collection)  
```  
  
 Vnoření znamená, že <xref:EnvDTE.ProjectItem> objekt může být <xref:EnvDTE.ProjectItems> kolekce v době, protože `ProjectItems` kolekce může obsahovat vnořené objekty. Ukázka základní projekt neukazuje tento vnoření. Implementací `Project` objektu účast ve struktuře stromu, který charakterizuje návrhu celkové modelu automatizace.  
  
 Automatizace aplikace project sleduje cestu v následujícím diagramu.  
  
 ![Visual Studio projekt objekty](../../extensibility/internals/media/projectobjects.gif "ProjectObjects")  
Automatizace projektu  
  
 Pokud se rozhodnete implementovat není `Project` objektu prostředí stále vrátí obecnou `Project` objekt, který obsahuje pouze název projektu.  
  
## <a name="see-also"></a>Viz také  
 <xref:EnvDTE.Projects>   
 <xref:EnvDTE.ProjectItem>   
 <xref:EnvDTE.ProjectItems>