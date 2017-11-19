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
ms.openlocfilehash: 42a3b8bdd8930c9006ba49fd0f2e2dd2491b38cb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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