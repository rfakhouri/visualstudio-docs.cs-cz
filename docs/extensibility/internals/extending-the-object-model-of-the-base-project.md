---
title: Rozšíření objektového modelu základního projektu | Dokumentace Microsoftu
ms.date: 03/22/2018
ms.topic: conceptual
helpviewer_keywords:
- automation object model, extending
- project subtypes, extending automation object model
- automation object model
ms.assetid: 2f95cc53-dff6-476c-bacd-500fb0ff7725
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 607a63dc84db2811a4a2d158be07f158b849e1ad
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66329045"
---
# <a name="extend-the-object-model-of-the-base-project"></a>Rozšíření objektového modelu základního projektu

Podtyp projektu mohou rozšířit objektového modelu automatizace základního projektu na následujících místech:

- Project.Extender("\<ProjectSubtypeName>"): To umožňuje podtyp projektu nabízí objekt pomocí vlastní metody ze <xref:EnvDTE.Project> objektu. Podtyp projektu můžete použít zařízení Extender automatizace ke zveřejnění `Project` objektu. <xref:EnvDTE80.IInternalExtenderProvider> Rozhraní implementované v agregátoru podtyp hlavního projektu by měl nabídnout jeho objekt pro `VSHPROPID_ExtObjectCATID` z <xref:Microsoft.VisualStudio.Shell.Interop.__VSSPROPID2> (odpovídající `itemid` hodnotu [VSITEMID. Kořen](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID.Root>)) CATID.

- ProjectItem.Extender("\<ProjectSubtypeName>"): To umožňuje podtyp projektu nabízí objekt pomocí vlastní metody z konkrétní <xref:EnvDTE.ProjectItem> objekt v rámci projektu. Podtyp projektu můžete zveřejnit tento objekt použít zařízení Extender automatizace. <xref:EnvDTE80.IInternalExtenderProvider> Rozhraní implementované v agregátoru podtyp hlavního projektu je potřeba nabízejí jeho objekt pro `VSHPROPID_ExtObjectCATID` z <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> (odpovídá požadovanou <xref:Microsoft.VisualStudio.VSConstants.VSITEMID>) CATID.

- Project.Properties: Tuto kolekci zpřístupní vlastnosti konfigurace nezávislé `Project` objektu. Další informace o `Project` vlastnosti, viz <xref:EnvDTE.Project.Properties%2A>. Podtyp projektu slouží k přidání vlastností do této kolekce zařízení Extender automatizace. <xref:EnvDTE80.IInternalExtenderProvider> Rozhraní implementované v agregátoru podtyp hlavního projektu je potřeba nabízejí jeho objekt pro `VSHPROPID_BrowseObjectCATID` z <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> (odpovídající `itemid` hodnotu [VSITEMID. Kořen](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID.Root>)) CATID.

- Configuration.Properties: Tato kolekce zpřístupní vlastnosti závislé na konfiguraci projektu pro konkrétní konfiguraci (například ladění). Další informace naleznete v tématu <xref:EnvDTE.Configuration>. Podtyp projektu slouží k přidání vlastností do této kolekce zařízení Extender automatizace. <xref:EnvDTE80.IInternalExtenderProvider> Rozhraní implementované v agregátoru podtyp hlavní projekt nabízí svého objektu pro CATID `VSHPROPID_CfgBrowseObjectCATID` (odpovídající `itemid` hodnotu [VSITEMID. Kořen](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID.Root>)). <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject> Rozhraní se používá k rozlišení jednoho objektu procházet konfigurace z jiného.

## <a name="see-also"></a>Viz také:

- <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>