---
title: "Projekt modelování | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- automation [Visual Studio SDK], implementing project objects
- project models, automation
ms.assetid: c8db8fdb-88c1-4b12-86fe-f3c30a18f9ee
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 31c3d87a44838ead7663ff4c156985ab1b8e98eb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="project-modeling"></a>Projekt modelování
Dalším krokem při poskytování automatizace pro váš projekt je implementovat objekty standardní projektu: <xref:EnvDTE.Projects> a `ProjectItems` kolekce; `Project` a <xref:EnvDTE.ProjectItem> objekty; a zbývající objekty, které jsou jedinečné pro implementaci. Tyto standardní objekty jsou definovány v souboru Dteinternal.h. Implementace objektů standard je k dispozici v ukázce BscPrj. Tyto třídy můžete použít jako modely vytvořit vlastní standardní projektu objekty, které stát vedle sebe s objekty projektu od ostatních typů projektu.  
  
 Příjemce automatizace předpokládá, abyste mohli volat <xref:EnvDTE.Solution>("`<UniqueProjName>")` a <xref:EnvDTE.ProjectItems> (`n`) kde n je číslo indexu pro získání konkrétní projekt v řešení. Toto volání automatizace vytváření způsobí, že prostředí tak, aby volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.GetProperty%2A> na příslušný projekt hierarchii předávání VSITEMID_ROOT jako parametr ItemID a VSHPROPID_ExtObject jako parametr VSHPROPID. `IVsHierarchy::GetProperty`Vrátí `IDispatch` ukazatel na objekt automatizace poskytování základních `Project` rozhraní, které jste implementovali.  
  
 Toto je syntaxe `IVsHierarchy::GetProperty`.  
  
 `HRESULT GetProperty (`  
  
 `VSITEMID` `itemid`,  
  
 `VSHPROPID` `propid`,  
  
 `VARIANT``*pvar`  
  
 `);`  
  
 Projekty zohlednit vnořování a používat kolekce k vytvoření skupiny položek projektu. Hierarchie vypadá takto.  
  
```  
Projects  
  |- Project  
      |- ProjectItems (a collection of ProjectItem)  
          |- ProjectItem (single object) or ProjectItems (another collection)  
```  
  
 Vnoření znamená, že <xref:EnvDTE.ProjectItem> objekt může být <xref:EnvDTE.ProjectItems> kolekce ve stejnou dobu protože `ProjectItems` kolekce může obsahovat vnořených objektů. Ukázka základní projekt nepředvádí tento vnoření. Implementací `Project` objektu účastnit stromu jako struktura, která charakterizuje návrh celkové automatizace modelu.  
  
 Automatizace projektu sleduje cestu v následujícím diagramu.  
  
 ![Objekty projektu sady Visual Studio](../../extensibility/internals/media/projectobjects.gif "ProjectObjects")  
Automatizace projektu  
  
 Pokud jste neimplementují `Project` objektu prostředí stále vrátí obecnou `Project` objekt, který obsahuje pouze název projektu.  
  
## <a name="see-also"></a>Viz také  
 <xref:EnvDTE.Projects>   
 <xref:EnvDTE.ProjectItem>   
 <xref:EnvDTE.ProjectItems>