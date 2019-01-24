---
title: Použití nástroje MSBuild | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, compiling with MSBuild
- MSBuild, extensibility
- packages, compiling with MSBuild
ms.assetid: 9d38c388-1f64-430e-8f6c-e88bc99a4260
caps.latest.revision: 21
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: a4338649885c75a81fdd08d5d4dd0ca4d00158ec
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54765888"
---
# <a name="using-msbuild"></a>Použití nástroje MSBuild
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nástroj MSBuild poskytuje dobře definovaný a rozšiřitelné formátu XML pro vytvoření souborů projektu, která plně popisují položky projektu sestavit úlohy sestavení a konfigurace sestavení.  
  
 Začátku do konce vzorku bude systém projektu jazyka založené na MSBuild, najdete v ukázkové Ironpythonu podrobné informace v[VSSDK ukázky](../../misc/vssdk-samples.md).  
  
## <a name="general-msbuild-considerations"></a>Nástroj MSBuild Obecné aspekty  
 Soubory projektu MSBuild, například [!INCLUDE[csprcs](../../includes/csprcs-md.md)] csproj a [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .vbproj soubory obsahují data, která se používá v okamžiku sestavení, ale může také obsahovat data, která se používá v době návrhu. Čas sestavení data uložená pomocí nástroje MSBuild primitiv, včetně [Item – Element (MSBuild)](../../msbuild/item-element-msbuild.md) a [Property – Element (MSBuild)](../../msbuild/property-element-msbuild.md). Doby návrhu data, která jsou specifická pro typ projektu a všechny související projekt podtypy data, uložená v volného tvaru XML pro ně vyhrazené.  
  
 MSBuild neobsahuje nativní podporu pro objekty konfigurace, ale poskytuje podmíněné atributy pro zadávání dat pro konkrétní konfiguraci. Příklad:  
  
```  
<OutputDir Condition="'$(Configuration)'=="release'">Bin\MyReleaseConfig</OutputDir>  
```  
  
 Další informace o podmíněné atributy, naleznete v tématu [podmíněné konstrukce](../../msbuild/msbuild-conditional-constructs.md).  
  
### <a name="extending-msbuild-for-your-project-type"></a>Rozšíření nástroje MSBuild pro váš typ projektu  
 Nástroj MSBuild rozhraní a rozhraní API se můžou změnit v budoucích verzích [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Proto je vhodné použít třídy rozhraní framework (MPF) spravovaného balíčku, protože poskytují stínění od změn.  
  
 Managed Package Framework pro projekty (MPFProj) poskytuje pomocné třídy pro vytváření a správu nový systém projektů. Zdrojového kódu a kompilace pokyny najdete v [MPF projektů – Visual Studio 2013](http://mpfproj12.codeplex.com/).  
  
 Třídy specifické pro projekt MPF jsou následující:  
  
|Třída|Implementace|  
|-----------|--------------------|  
|`Microsoft.VisualStudio.Package.ProjectNode`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents>|  
|`Microsoft.VisualStudio.Package.ProjectFactory`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory>|  
|`Microsoft.VisualStudio.Package.HierarchyNode`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>|  
|`Microsoft.VisualStudio.Package.ProjectConfig`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildableProjectCfg><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg>|  
|`Microsoft.VisualStudio.Package.SettingsPage`|<xref:Microsoft.VisualStudio.OLE.Interop.IPropertyPageSite>|  
  
 `Microsoft.VisualStudio.Package.ProjectElement` Třída tvoří obálku pro položky nástroje MSBuild.  
  
#### <a name="single-file-generators-vs-msbuild-tasks"></a>Vs generátorů tvořených jedním souborem. Úlohy nástroje MSBuild  
 Jediný soubor generátory jsou dostupné v době návrhu pouze, ale úlohy nástroje MSBuild lze použít v době návrhu a čas sestavení. Kvůli maximální flexibilitě proto použijte úlohy nástroje MSBuild k transformaci a generování kódu. Další informace najdete v tématu [vlastní nástroje](../../extensibility/internals/custom-tools.md).  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace nástroje MSBuild](../../msbuild/msbuild-reference.md)   
 [MSBuild](http://msdn.microsoft.com/7c49aba1-ee6c-47d8-9de1-6f29a906e20b)   
 [Vlastní nástroje](../../extensibility/internals/custom-tools.md)
