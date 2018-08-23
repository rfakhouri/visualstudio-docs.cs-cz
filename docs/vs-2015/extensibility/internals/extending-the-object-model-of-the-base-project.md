---
title: Rozšíření objektového modelu základního projektu | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- automation object model, extending
- project subtypes, extending automation object model
- automation object model
ms.assetid: 2f95cc53-dff6-476c-bacd-500fb0ff7725
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: dc9a5494ad888da9707af0d8af40dc5ea3d242b0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667661"
---
# <a name="extending-the-object-model-of-the-base-project"></a>Rozšíření objektového modelu základního projektu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [rozšíření objektového modelu projektu Base](https://docs.microsoft.com/visualstudio/extensibility/internals/extending-the-object-model-of-the-base-project).  
  
Podtyp projektu mohou rozšířit objektového modelu automatizace základního projektu na následujících místech:  
  
-   Project.Extender ("\<ProjectSubtypeName >") – díky tomu podtyp projektu nabízí objekt pomocí vlastní metody ze <xref:EnvDTE.Project>. Podtyp projektu můžete použít zařízení Extender automatizace ke zveřejnění `Project` objektu. <xref:EnvDTE80.IInternalExtenderProvider>Rozhraní implementované v agregátoru podtyp hlavního projektu by měl nabídnout jeho objekt pro `VSHPROPID_ExtObjectCATID` z <xref:Microsoft.VisualStudio.Shell.Interop.__VSSPROPID2> (odpovídající `itemid` hodnota VSITEMID_ROOT, z `VSITEMID`) CATID.  
  
-   ProjectItem.Extender ("\<ProjectSubtypeName >") – díky tomu podtyp projektu nabízí objekt pomocí vlastní metody z konkrétní <xref:EnvDTE.ProjectItem> objekt v rámci projektu. Podtyp projektu můžete zveřejnit tento objekt použít zařízení Extender automatizace. <xref:EnvDTE80.IInternalExtenderProvider> Rozhraní implementované v agregátoru podtyp hlavního projektu je potřeba nabízejí jeho objekt pro `VSHPROPID_ExtObjectCATID` z <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> (odpovídá požadovanou `VSITEMID`) CATID.  
  
-   Project.Properties – zpřístupní tuto kolekci nezávislé vlastnosti konfigurace `Project` objektu. Další informace o vlastnosti projektu, naleznete v tématu <xref:EnvDTE.Project.Properties%2A>. Podtyp projektu slouží k přidání vlastností do této kolekce zařízení Extender automatizace. <xref:EnvDTE80.IInternalExtenderProvider> Rozhraní implementované v agregátoru podtyp hlavního projektu je potřeba nabízejí jeho objekt pro `VSHPROPID_BrowseObjectCATID` z VSHPROPID2 (odpovídající `itemid` hodnota VSITEMID_ROOT, z <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>) CATID.  
  
-   Configuration.Properties – této kolekce zveřejňuje vlastnosti závislé konfigurace projektu pro konkrétní konfiguraci (například ladění). Další informace najdete v tématu <xref:EnvDTE.Configuration>. Podtyp projektu slouží k přidání vlastností do této kolekce zařízení Extender automatizace. <xref:EnvDTE80.IInternalExtenderProvider> Rozhraní implementované v agregátoru podtyp hlavní projekt nabízí svého objektu pro CATID `VSHPROPID_CfgBrowseObjectCATID` (odpovídající `itemid` hodnotu <xref:Microsoft.VisualStudio.VSConstants.VSITEMID>). <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject>Rozhraní se používá k rozlišení jednoho objektu procházet konfigurace z jiného.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>

