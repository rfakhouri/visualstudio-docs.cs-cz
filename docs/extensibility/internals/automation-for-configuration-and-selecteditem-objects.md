---
title: Automatizace pro konfiguraci a objekty SelectedItem | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- automation [Visual Studio SDK], SelectedItem object
- automation [Visual Studio SDK], builds
ms.assetid: 120377f1-51aa-4445-b2f7-06ab7fc2b47f
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 8a9446a5c63df7f20d6e4dbdc3cb60bf20183bb5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="automation-for-configuration-and-selecteditem-objects"></a>Pro konfiguraci a SelectedItem objekty automatizace
Můžete automatizovat sestavení a procesů vybrané položky v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="automation-for-builds"></a>Automatizace pro sestavení  
 Sestavení nebo konfigurace má model automatizace, který je zadán při implementaci <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider>. Další informace najdete v tématu [Principy konfigurací sestavení](../../ide/understanding-build-configurations.md).  
  
 Pokud vytvoříte VSPackage a chtějí mít kontrolu nad možnosti konfigurace, musíte použít model automatizace.  
  
## <a name="automation-for-selecteditem"></a>Automatizace pro SelectedItem  
 Není nutné poskytovat implementaci `SelectedItem` objekt, protože obsahuje standardní implementace sady Visual Studio. Však můžete implementovat `SelectedItem` objektu, pokud dáváte přednost. Musí implementovat objekt, který obsahuje `SelectedItem` rozhraní a vrátí reakci na volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A> nastavena metoda s VSITEMID <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID>.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A>   
 [Přispívání do modelu automatizace](../../extensibility/internals/contributing-to-the-automation-model.md)   
 [Principy konfigurací sestavení](../../ide/understanding-build-configurations.md)