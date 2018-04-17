---
title: T4 – Direktiva Include | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 4cfa7742a75b24288ef3617d8195a75e13d8e817
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="t4-include-directive"></a>T4 – direktiva Include
V šabloně text v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], mohou zahrnovat text z jiného souboru pomocí `<#@include#>` – direktiva. Můžete umístit `include` direktivy kdekoli v textové šablony před první třídy funkce bloku `<#+ ... #>`. Zahrnuté soubory může také obsahovat `include` direktivy a další direktivy. Díky tomu můžete kód šablony a často používaný text sdílet mezi šablonami.  
  
## <a name="using-include-directives"></a>Použití direktiv include  
  
```  
<#@ include file="filePath" [once="true"] #>  
```  
  
-   `filePath` může být absolutní, nebo relativně k aktuální soubor šablony.  
  
     Kromě toho konkrétní [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rozšíření můžete určit jejich vlastní adresáře pro vyhledávání zahrnout soubory. Například pokud jste nainstalovali vizualizace a modelování SDK (DSL Tools), do následující složky se přidá do seznamu zahrnout: `Program Files\Microsoft Visual Studio 10.0\Common7\IDE\Extensions\Microsoft\DSL SDK\DSL Designer\11.0\TextTemplates`.  
  
     Tyto další složky vkládaných souborů mohou záviset na příponě vkládaného souboru. Patří například nástroje DSL složky je k dispozici pouze pro včetně souborů, které mají příponu souboru `.tt`  
  
-   `filePath` může obsahovat proměnné prostředí oddělené s "%". Příklad:  
  
    ```  
    <#@ include file="%HOMEPATH%\MyIncludeFile.t4" #>  
    ```  
  
-   Název součástí souboru není nutné používat rozšíření `".tt"`.  
  
     Můžete chtít použít jiné rozšíření, jako je `".t4"` pro zahrnuté soubory. Důvodem je, že při přidání `.tt` souboru do projektu, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] automaticky nastaví jeho **Custom Tool** vlastnost `TextTemplatingFileGenerator`. Vkládané soubory obvykle nechcete transformovat individuálně.  
  
     Na druhé straně byste měli vědět, že v některých případech přípona souboru ovlivňuje, v jakých dalších složkách se budou hledat vkládané soubory. To může být důležité, pokud máte vkládaný soubor, který obsahuje jiné soubory.  
  
-   Vložený obsah se zpracuje téměř jako kdyby byl součástí textové šablony, která ho vkládá. Však můžete zahrnout soubor, který obsahuje blok funkce třída `<#+...#>` i v případě `include` – direktiva následuje běžného textu a bloky standardního ovládacího prvku.  
  
-   Použití `once="true"` pro zajištění šablonu zahrnuty pouze jednou, i když je volána z více než jeden další soubor zahrnout.  
  
     Díky této funkce snadno vytvářet knihovnu opakovaně použitelné T4 fragmenty, který můžete použít v proběhne bez obav, některé jiné fragment kódu má již zahrnuty je.  Předpokládejme například, že je vaše knihovna velmi podrobné fragmenty kódu, které pracují s zpracování šablony a C# generace.  Ty se pak používá některé více specifické pro úlohy nástroje, například generování výjimek, které pak můžete použít z jakékoli šablony více specifické pro aplikaci. Pokud si nakreslíte graf závislostí, uvidíte, že některé fragmenty kódu budou vloženy několikrát. Ale `once` parametr zabrání následné zahrnutí.  
  
 **MyTextTemplate.tt:**  
  
```  
<#@ output extension=".txt" #>  
Output message 1 (from top template).  
<#@ include file="TextFile1.t4"#>  
Output message 5 (from top template).  
<#  
   GenerateMessage(6); // defined in TextFile1.t4  
   AnotherGenerateMessage(7); // defined in TextFile2.t4  
#>  
  
```  
  
 **TextFile1.t4:**  
  
```  
   Output Message 2 (from included file).  
<#@include file="TextFile2.t4" #>  
   Output Message 4 (from included file).  
<#+ // Start of class feature control block.  
void GenerateMessage(int n)  
{  
#>  
   Output Message <#= n #> (from GenerateMessage method).  
<#+  
}  
#>  
  
```  
  
 **TextFile2.t4:**  
  
```  
        Output Message 3 (from included file 2).  
<#+ // Start of class feature control block.  
void AnotherGenerateMessage(int n)  
{  
#>  
       Output Message <#= n #> (from AnotherGenerateMessage method).  
<#+  
}  
#>  
  
```  
  
 **Výsledná vygenerována souboru MyTextTemplate.txt:**  
  
```  
Output message 1 (from top template).  
   Output Message 2 (from included file).  
        Output Message 3 (from included file 2).  
  
   Output Message 4 (from included file).  
  
Output message 5 (from top template).  
   Output Message 6 (from GenerateMessage method).  
       Output Message 7 (from AnotherGenerateMessage method).  
  
```  
  
##  <a name="msbuild"></a> Pomocí vlastnosti projektu nástroje MSBuild a Visual Studio  
 I když používáte Visual Studio makra jako $(solutiondir) – v direktivu nepodporují se v nástroji MSBuild. Chcete-li transformovat šablony v sestavovacím počítači, je nutné místo toho použít vlastnosti projektu.  
  
 Úpravou souboru .csproj nebo .vbproj definujte vlastnost projektu. Tento příklad definuje vlastnost s názvem `myIncludeFolder`:  
  
```xml  
<!-- Define a project property, myIncludeFolder: -->  
<PropertyGroup>  
    <myIncludeFolder>$(MSBuildProjectDirectory)\..\libs</myIncludeFolder>  
</PropertyGroup>  
  
<!-- Tell the MSBuild T4 task to make the property available: -->  
<ItemGroup>  
    <T4ParameterValues Include="myIncludeFolder">  
      <Value>$(myIncludeFolder)</Value>  
    </T4ParameterValues>  
  </ItemGroup>  
  
```  
  
 Tuto vlastnost projektu nyní můžete použít v textových šablonách, které se správně transformují jak v sadě Visual Studio, tak v nástroji MSBuild:  
  
```  
<#@ include file="$(myIncludeFolder)\defs.tt" #>  
```