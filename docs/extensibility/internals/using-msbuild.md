---
title: "Pomocí nástroje MSBuild | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSPackages, compiling with MSBuild
- MSBuild, extensibility
- packages, compiling with MSBuild
ms.assetid: 9d38c388-1f64-430e-8f6c-e88bc99a4260
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 3b9d05b85cacfcdf90a883ffd08d4dec316eaafc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="using-msbuild"></a>Pomocí nástroje MSBuild
MSBuild poskytuje dobře definovaný a rozšiřitelné formátu XML pro vytvoření souborů projektu, které plně popisují položky projektu vytvořeny, vytvářet úlohy a konfigurace sestavení.  
  
## <a name="general-msbuild-considerations"></a>MSBuild Obecné aspekty  
 MSBuild soubory projektu, například [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] .csproj a [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] .vbproj soubory obsahují data, která se používá v čase vytvoření buildu, ale může také obsahovat data, která se používá v době návrhu. Čas sestavení data se ukládají pomocí nástroje MSBuild primitiv, včetně [Item – Element (MSBuild)](../../msbuild/item-element-msbuild.md) a [Property – Element (MSBuild)](../../msbuild/property-element-msbuild.md). Návrh data, která jsou specifická pro typ projektu a všechny související projektu podtypů data, je uložen v libovolném formátu XML pro ně vyhrazené.  
  
 MSBuild nemá nativní podpora pro objekty konfigurace, ale poskytuje podmíněné atributy pro zadání data specifická pro konfiguraci. Příklad:  
  
```xml  
<OutputDir Condition="'$(Configuration)'=="release'">Bin\MyReleaseConfig</OutputDir>  
```  
  
 Další informace o podmíněné atributy najdete v tématu [podmíněné konstrukce](../../msbuild/msbuild-conditional-constructs.md).  
  
### <a name="extending-msbuild-for-your-project-type"></a>Rozšíření pro typ vašeho projektu nástroje MSBuild  
 Rozhraní API a nástroje MSBuild rozhraní se může v budoucích verzích změnit [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Proto je vhodné použít třídy spravované balíček framework (MPF), protože poskytují stínění z změny.  
  
 Spravovaná rozhraní balíčku pro projekty (MPFProj) poskytuje pomocné třídy pro vytváření a správu nového projektu systému. Zdrojový kód a kompilace pokyny naleznete v [sady MPF projektů – Visual Studio 2013](http://mpfproj12.codeplex.com/).  
  
 Třídy specifické pro projekt sady MPF jsou následující:  
  
|Třída|Implementace|  
|-----------|--------------------|  
|`Microsoft.VisualStudio.Package.ProjectNode`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents>|  
|`Microsoft.VisualStudio.Package.ProjectFactory`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory>|  
|`Microsoft.VisualStudio.Package.HierarchyNode`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>|  
|`Microsoft.VisualStudio.Package.ProjectConfig`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildableProjectCfg><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg>|  
|`Microsoft.VisualStudio.Package.SettingsPage`|<xref:Microsoft.VisualStudio.OLE.Interop.IPropertyPageSite>|  
  
 `Microsoft.VisualStudio.Package.ProjectElement`Třída je obálka pro položky nástroje MSBuild.  
  
#### <a name="single-file-generators-vs-msbuild-tasks"></a>Jeden soubor generátory vs. Úlohy nástroje MSBuild  
 Jedním souborem jsou dostupné v době návrhu pouze generátory, ale úlohy nástroje MSBuild lze použít v době návrhu a čase vytvoření buildu. Flexibilní tedy používejte úlohy nástroje MSBuild k transformaci a generování kódu. Další informace najdete v tématu [vlastní nástroje](../../extensibility/internals/custom-tools.md).  
  
## <a name="see-also"></a>Viz také  
 [MSBuild – Reference](../../msbuild/msbuild-reference.md)   
 [Nástroje MSBuild](../../msbuild/msbuild.md)   
 [Vlastní nástroje](../../extensibility/internals/custom-tools.md)