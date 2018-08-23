---
title: Automatizace pro konfiguraci a objekty SelectedItem | Dokumentace Microsoftu
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
- automation [Visual Studio SDK], SelectedItem object
- automation [Visual Studio SDK], builds
ms.assetid: 120377f1-51aa-4445-b2f7-06ab7fc2b47f
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f9d5da07c4505aef38fbef22b8680a8c0914056a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666343"
---
# <a name="automation-for-configuration-and-selecteditem-objects"></a>Automatizace pro konfiguraci a objekty SelectedItem
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [automatizace pro konfiguraci a objekty SelectedItem](https://docs.microsoft.com/visualstudio/extensibility/internals/automation-for-configuration-and-selecteditem-objects).  
  
Můžete automatizovat sestavení a procesy pro vybranou položku v [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
## <a name="automation-for-builds"></a>Automatizace pro sestavení  
 Sestavení nebo konfigurace má modelu automatizace, který je k dispozici při implementaci <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider>. Další informace najdete v tématu [Principy konfigurací sestavení](../../ide/understanding-build-configurations.md).  
  
 Pokud vytvoříte VSPackage a chcete mít pod kontrolou možnosti konfigurace, musíte použít model automatizace.  
  
## <a name="automation-for-selecteditem"></a>Automatizace pro SelectedItem  
 Není nutné poskytnout implementaci pro `SelectedItem` objektu, protože Visual Studio obsahuje standardní implementace. Ale můžete implementovat `SelectedItem` objektu, pokud dáváte přednost. Musí implementovat objekt, který obsahuje `SelectedItem` rozhraní a vrátí odpověď na volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A> nastavena metoda s VSITEMID <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID>.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A>   
 [Přispívání do modelu automatizace](../../extensibility/internals/contributing-to-the-automation-model.md)   
 [Principy konfigurací sestavení](../../ide/understanding-build-configurations.md)

