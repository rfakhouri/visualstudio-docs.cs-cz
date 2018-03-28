---
title: Rozšíření objektový Model základní projektu | Microsoft Docs
ms.date: 03/22/2018
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- automation object model, extending
- project subtypes, extending automation object model
- automation object model
ms.assetid: 2f95cc53-dff6-476c-bacd-500fb0ff7725
caps.latest.revision: ''
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: a0fdda35744aaddf8789818afd1f938897470147
ms.sourcegitcommit: 768118d470da9c7164d2f23ca918dfe26a4be72f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/28/2018
---
# <a name="extending-the-object-model-of-the-base-project"></a>Rozšíření objektový Model základní projektu

Podtyp projektu může rozšířit objektový model automatizace základní projektu na těchto místech:

-   Project.Extender ("\<ProjectSubtypeName >") – to umožňuje podtypem projektu na nabídku s vlastních metod z objektu <xref:EnvDTE.Project>. Podtyp projektu pomocí automatizace Extender lze zobrazit `Project` objektu. <xref:EnvDTE80.IInternalExtenderProvider> Rozhraní implementované v agregátoru dílčí hlavní projekt by měl nabízejí jeho objekt pro `VSHPROPID_ExtObjectCATID` z <xref:Microsoft.VisualStudio.Shell.Interop.__VSSPROPID2> (odpovídající `itemid` hodnotu [VSITEMID. Kořenová](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Root>)) CATID.

-   ProjectItem.Extender ("\<ProjectSubtypeName >") – to umožňuje podtypem projektu a nabídnout objekt s vlastních metod z konkrétní <xref:EnvDTE.ProjectItem> objekt v rámci projektu. Podtyp projektu pomocí automatizace Extender lze zobrazit tento objekt. <xref:EnvDTE80.IInternalExtenderProvider> Musí nabízejí jeho objekt pro rozhraní implementované v agregátoru dílčí hlavní projekt `VSHPROPID_ExtObjectCATID` z <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> (odpovídající požadované <xref:Microsoft.VisualStudio.VSConstants.VSITEMID>) CATID.

-   Project.Properties - tuto kolekci zpřístupní vlastnosti konfigurace nezávislé `Project` objektu. Další informace o vlastnosti projektu najdete v tématu <xref:EnvDTE.Project.Properties%2A>. Podtyp projektu lze automatizace Extender do této kolekce přidat jeho vlastnosti. <xref:EnvDTE80.IInternalExtenderProvider> Musí nabízejí jeho objekt pro rozhraní implementované v agregátoru dílčí hlavní projekt `VSHPROPID_BrowseObjectCATID` z VSHPROPID2 (odpovídající `itemid` hodnotu [VSITEMID. Kořenová](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Root>), z <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>) CATID.

-   Configuration.Properties - tuto kolekci zpřístupní závislá na konfiguraci vlastnosti projektu pro konkrétní konfiguraci (například ladění). Další informace naleznete v tématu <xref:EnvDTE.Configuration>. Podtyp projektu lze automatizace Extender do této kolekce přidat jeho vlastnosti. <xref:EnvDTE80.IInternalExtenderProvider> Rozhraní implementované v agregátoru dílčí hlavní projekt nabízí jeho objekt CATID `VSHPROPID_CfgBrowseObjectCATID` (odpovídající `itemid` hodnotu [VSITEMID. Kořenová](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Root>)). <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject>Rozhraní se používá k rozlišení jeden objekt konfigurace procházet z jiné.

## <a name="see-also"></a>Viz také

- <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>