---
title: T4 – Direktiva Assembly | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 2d0588688a6545471cfaa480d0efac868fe708de
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="t4-assembly-directive"></a>T4 – direktiva Assembly
V [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] návrhu textové šablony, `assembly` – direktiva načte sestavení tak, aby váš kód šablony můžete používat jeho typů. Podobně jako při přidávání odkaz na sestavení v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektu.  
  
 Obecné informace o zápisu textové šablony, najdete v části [zápis textové šablony T4](../modeling/writing-a-t4-text-template.md).  
  
> [!NOTE]
>  Není nutné `assembly` direktivy v běhu (předběžně zpracované) textové šablony. Místo toho přidejte nezbytné sestavení, které chcete **odkazy** z vaší [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektu.  
  
## <a name="using-the-assembly-directive"></a>Použití direktivy assembly  
 Syntaxe této direktivy je následující:  
  
```  
<#@ assembly name="[assembly strong name|assembly file name]" #>  
```  
  
 Název sestavení by měl být jeden z následujících názvů:  
  
-   Silný název sestavení v globální mezipaměti, jako například `System.Xml.dll`. Můžete také použít dlouhých úseků jako `name="System.Xml, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"`. Další informace naleznete v tématu <xref:System.Reflection.AssemblyName>.  
  
-   Absolutní cesta k sestavení  
  
 Můžete použít `$(variableName)` syntaxe tak, aby odkazovaly [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] proměnné, jako `$(SolutionDir)`, a `%VariableName%` na referenční proměnné prostředí. Příklad:  
  
```  
<#@ assembly name="$(SolutionDir)\MyProject\bin\Debug\SomeLibrary.Dll" #>  
```  
  
 Direktiva assembly nemá žádný účinek na předzpracované textové šablony. Místo toho zahrnout nezbytné odkazy v **odkazy** část vaší [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektu. Další informace najdete v tématu [generování textu běhu pomocí textových šablon T4](../modeling/run-time-text-generation-with-t4-text-templates.md).  
  
## <a name="standard-assemblies"></a>Standardní sestavení  
 Následující sestavení se načítají automaticky, takže pro ně nemusíte psát direktivy sestavení:  
  
-   `Microsoft.VisualStudio.TextTemplating.1*.dll`  
  
-   `System.dll`  
  
-   `WindowsBase.dll`  
  
 Pokud používáte vlastní direktivu, může procesor direktiv načíst další sestavení. Pokud například píšete šablony pro jazyk domény (DSL), nemusíte psát direktivy sestavení pro následující sestavení:  
  
-   `Microsoft.VisualStudio.Modeling.Sdk.1*.dll`  
  
-   `Microsoft.VisualStudio.Modeling.Sdk.Diagrams.1*.dsl`  
  
-   `Microsoft.VisualStudio.TextTemplating.Modeling.1*.dll`  
  
-   Sestavení obsahující váš kód DSL  
  
##  <a name="msbuild"></a> Pomocí vlastnosti projektu nástroje MSBuild a Visual Studio  
 Visual Studio makra jako $(solutiondir) – nefungují v nástroji MSBuild. Chcete-li transformovat šablony v sestavovacím počítači, je nutné místo toho použít vlastnosti projektu.  
  
 Úpravou souboru .csproj nebo .vbproj definujte vlastnost projektu. Tento příklad definuje vlastnost s názvem `myLibFolder`:  
  
```xml  
<!-- Define a project property, myLibFolder: -->  
<PropertyGroup>  
    <myLibFolder>$(MSBuildProjectDirectory)\..\libs</myLibFolder>  
</PropertyGroup>  
  
<!-- Tell the MSBuild T4 task to make the property available: -->  
<ItemGroup>  
    <T4ParameterValues Include="myLibFolder">  
      <Value>$(myLibFolder)</Value>  
    </T4ParameterValues>  
  </ItemGroup>  
  
```  
  
 Tuto vlastnost projektu nyní můžete použít v textových šablonách, které se správně transformují jak v sadě Visual Studio, tak v nástroji MSBuild:  
  
```  
<#@ assembly name="$(myLibFolder)\MyLib.dll" #>  
```  
  
## <a name="see-also"></a>Viz také  
 [T4 – direktiva Include](../modeling/t4-include-directive.md)