---
title: "Jaký & č. 39; s nových ve správě zdrojového kódu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- what's new [Visual Studio SDK], source control
- source control [Visual Studio SDK], what's new
ms.assetid: bcf85418-18fb-4824-9dae-d14bf3d56a77
caps.latest.revision: "27"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 9fc1c5956a4d3c20f8b9abec36d554f3ec56c8c9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="what39s-new-in-source-control"></a>Jaký & č. 39; s nových ve správě zdrojového kódu
V [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] řešením pro řízení hluboko integrované zdroje můžete zadat implementací VSPackage Správa zdrojového kódu. Tato část popisuje funkce správy zdrojového kódu VSPackages a poskytuje přehled o implementaci.  
  
## <a name="the-source-control-vspackage"></a>VSPackage řízení zdroje  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]podporuje dva typy řešení pro řízení zdrojů. Ve všech verzích [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], stále můžete integrovat zdroj ovládacího prvku Plug-in založené na rozhraní API modulu plug-in. Můžete také vytvořit VSPackage pro zdrojového kódu, která poskytuje přímý integraci, [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] cesty vhodné pro řešení pro řízení zdrojů, které vyžadují vysokou úroveň vyspělosti a nezávislé.  
  
 VSPackage můžete přidat téměř k libovolnému druhu funkcí, které [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Správa zdrojového kódu VSPackage nabízí funkci řízení kompletní zdrojový pro [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], z uživatelského rozhraní uživateli na back-end komunikaci se službou správy zdrojového kódu.  
  
 Implementace Správa zdrojového kódu VSPackage vyžaduje strategie "všechny nebo nic". Tvůrce zdrojového kódu VSPackage musí investovat významné množství úsilí v jeho implementaci počet rozhraní pro řízení zdrojového a nové prvky uživatelského rozhraní (dialogových oken, nabídek a panelů nástrojů) tak, aby pokrývalo funkci řízení celý zdrojový i rozhraní požadované žádné balíčku pro integraci se úspěšně [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 Následující kroky poskytují obecný přehled co je potřeba k implementaci balíček zdroj ovládacího prvku. Podrobnosti najdete v tématu [vytváření VSPackage zdroj ovládacího prvku](../../extensibility/internals/creating-a-source-control-vspackage.md).  
  
1.  Vytvořte VSPackage proffers privátní zdroj řízení služby.  
  
2.  Implementace rozhraní v související ovládací prvek služby zdroje, které jsou proffered podle [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] (například <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider> rozhraní).  
  
3.  Správa zdrojového kódu VSPackage zaregistrujte.  
  
4.  Implementujte správu zdrojů uživatelského rozhraní, včetně položek nabídky, dialogová okna, panely nástrojů a kontextové nabídky.  
  
5.  Všechny zdrojové ovládací prvek související události jsou předá ke správě zdrojového kódu VSackage, když je aktivní a musí být zpracována vaší VSPackage.  
  
6.  Správa zdrojového kódu VSPackage musí naslouchat na události, jako jsou ty implementuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3> rozhraní a také sledovat projektu dokumentu (TPD) události (jak je implementované <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2> rozhraní) a proveďte potřebné akce.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>   
 [Přehled](../../extensibility/internals/source-control-integration-overview.md)   
 [Vytvoření balíčku VSPackage správy zdrojového kódu](../../extensibility/internals/creating-a-source-control-vspackage.md)