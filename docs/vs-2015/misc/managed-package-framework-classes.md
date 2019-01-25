---
title: Managed Package Framework tříd | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: devlang-csharp
ms.topic: conceptual
helpviewer_keywords:
- managed package framework, helper classes
- managed package helper classes
- Visual Studio SDK, managed package helper classes
- classes [Visual Studio SDK], managed package framework
ms.assetid: 15aedcc3-c79a-460b-b620-43223f1ae81e
caps.latest.revision: 24
manager: jillfra
ms.openlocfilehash: d8e2bbf51aa6266411558e91f3c17905d0c8605c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54786064"
---
# <a name="managed-package-framework-classes"></a>Managed Package Framework třídy
Třídy spravované balíčků framework (MPF) slouží k vytváření balíčků VSPackage pomocí spravovaného kódu. Poskytuje výchozí implementaci pro mnoho rozhraní VSPackage. Skrýt podrobnosti implementace a složitosti, MPF vám umožní vytvořit [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] integrace produktů s minimální část kódu.  
  
> [!WARNING]
>  Většina sestavení, které obsahují Managed Package Framework třídy, které se dodávají se sadou Visual Studio SDK. Můžete stáhnout zdrojový kód pro spravované zabalí rozhraní pro projekty v [Managed Package Framework pro projekty](http://mpfproj11.codeplex.com/).  
  
## <a name="mpf-namespaces"></a>Obory názvů MPF  
 V následující tabulce jsou uvedeny MPF obory názvů poskytované [!INCLUDE[vsipsdk](../includes/vsipsdk-md.md)].  
  
|Obor názvů|Obsah|  
|----------------|--------------|  
|<xref:Microsoft.VisualStudio>|Obsahuje třídy užitečné pro zpracování chyb modelu COM, [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] konstanty a Win32 pro systém windows.|  
|<xref:Microsoft.VisualStudio.Package>|Obsahuje spravovaný kód obálky pro [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] MSBuild, projekty a editory.|  
|<xref:Microsoft.VisualStudio.Shell>|Zahrnuje MPF základních tříd, ze které odvozujete implementace mnoho běžně používané objekty sady Visual Studio.|  
|<xref:Microsoft.VisualStudio.Shell.Design>|Obsahuje [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] rozšíření návrháře.|  
|<xref:Microsoft.VisualStudio.Shell.Design.Serialization>|Obsahuje [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] rozšíření serializace návrháře.|  
|<xref:Microsoft.VisualStudio.Shell.Design.Serialization.CodeDom>|Obsahuje [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] rozšíření návrháře CodeDom.|  
|<xref:Microsoft.VisualStudio.Shell.Flavor>|Podporuje projektu podtypů (označované také jako "typy").|  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření VSPackages a rozhraní Managed Package Framework](../misc/vspackages-and-the-managed-package-framework.md)   
 [Pomocí sady Visual Studio sestavení vzájemné spolupráce](../extensibility/internals/using-visual-studio-interop-assemblies.md)   
 [Rozšíření VSPackages a rozhraní Managed Package Framework](../misc/vspackages-and-the-managed-package-framework.md)