---
title: Automatizace pro konfiguraci a objekty SelectedItem | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- automation [Visual Studio SDK], SelectedItem object
- automation [Visual Studio SDK], builds
ms.assetid: 120377f1-51aa-4445-b2f7-06ab7fc2b47f
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 42faf8127c1ab70d3470aa497a0cdab6058060f8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68157256"
---
# <a name="automation-for-configuration-and-selecteditem-objects"></a>Automatizace pro konfiguraci a objekty SelectedItem
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

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
