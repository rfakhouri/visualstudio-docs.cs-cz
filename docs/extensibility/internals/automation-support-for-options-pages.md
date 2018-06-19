---
title: Podpora automatizace pro možnosti stránky | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Tools Options pages [Visual Studio SDK], automation support
- automation [Visual Studio SDK], creating Tools Options pages
ms.assetid: 0b25b82c-7432-4e0a-9e84-350269ba8260
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d27ad706d4203a3573a734a1cd11b19e3c9df6a1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31128569"
---
# <a name="automation-support-for-options-pages"></a>Podpora automatizace pro možnosti stránky
VSPackages můžete zadat vlastní **možnosti** dialogových oknech na **nástroje** nabídky (stránek možnosti nástrojů) v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] a je zpřístupnit automatizace modelu.  
  
## <a name="tools-options-pages"></a>Stránek možnosti nástrojů  
 Chcete-li vytvořit **možnosti nástrojů** stránky, VSPackage musíte zadat implementaci ovládacího prvku uživatel vrátil prostředí pomocí VSPackage implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A> metoda, (nebo pro spravovaný kód <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A> Metoda).  
  
 Je volitelný, ale doporučujeme povolit přístup k této nové stránce prostřednictvím modelu automatizace. Můžete to udělat pomocí následujících kroků:  
  
1.  Rozšíření <xref:EnvDTE._DTE.Properties%2A> objekt prostřednictvím implementace objektu IDispatch odvozený.  
  
2.  Vrátí implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> – metoda (nebo pro spravovaný kód <xref:Microsoft.VisualStudio.Shell.Package.GetAutomationObject%2A> metoda) k objektu IDispatch odvozený.  
  
3.  Když příjemce automatizace volá <xref:EnvDTE._DTE.Properties%2A> metodu vlastní **možnost** stránka vlastností, používá prostředí <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> metoda získat vlastní **možnosti nástrojů** stránky automatizace implementace.  
  
4.  Objekt automatizace VSPackage je pak sloužit ke každé <xref:EnvDTE.Property> vrácený <xref:EnvDTE._DTE.Properties%2A>.  
  
 Příklad implementace stránku vlastní možnosti nástrojů, najdete v části [VSSDK ukázky](http://aka.ms/vs2015sdksamples).  
  
## <a name="see-also"></a>Viz také  
 [Zveřejňování objektů projektu](../../extensibility/internals/exposing-project-objects.md)