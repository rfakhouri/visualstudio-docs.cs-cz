---
title: Nahraditelné parametry | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, tokens
- tokens [SharePoint development in Visual Studio]
- replaceable parameters [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, replaceable parameters
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload: office
ms.openlocfilehash: f6e311f7c0268cecb94498fffda702438ea921b0
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120367"
---
# <a name="replaceable-parameters"></a>Nahraditelné parametry
  Nahraditelné parametry, nebo *tokeny*, dá se použít uvnitř soubory projektu zadat hodnoty pro položky řešení služby SharePoint, jejichž skutečnými hodnotami nejsou známá v době návrhu. Jsou to podobně jako u standardní [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] tokeny šablony. Další informace najdete v tématu [parametry šablony](/visualstudio/ide/template-parameters).  
  
## <a name="token-format"></a>Formát tokenu
 Tokeny nezačíná a nekončí znak dolaru ($). Při nasazení, použití tokenů jsou nahrazeny skutečnými hodnotami při projektu je zabalené do balíčku řešení služby SharePoint (*WSP* souboru). Například token **$SharePoint.Package.Name$** může vyřešit řetězec "Test SharePoint balíček".  
  
## <a name="token-rules"></a>Token pravidla
 Následující pravidla platí při tokenů:  
  
-   Tokeny lze zadat kdekoli v řádku.  
  
-   Tokeny nemůže zahrnovat více řádků.  
  
-   Stejný token může být zadán více než jednou na stejném řádku a ve stejném souboru.  
  
-   Na stejném řádku je možné zadat jiný tokeny.  
  
 Tokeny, které se neřídí tato pravidla jsou ignorovány a nezpůsobovalo neustálé upozornění nebo chyby.  
  
 Okamžitě po transformaci manifestu se provádí nahrazení tokeny pomocí řetězcových hodnot. Tato nahrazení umožňuje uživateli upravit manifestu šablony s tokeny.  
  
### <a name="token-name-resolution"></a>Token překlad
 Ve většině případů token přeloží na konkrétní hodnotu bez ohledu na to, kde se nachází. Ale pokud token je spojena s balíčku nebo funkce, je token hodnota závisí na kterém se nachází. Například pokud je funkce v balíčku pak se token `$SharePoint.Package.Name$` přeloží na hodnotu "Balíček A." Pokud stejné funkce je v balíčku B, pak `$SharePoint.Package.Name$` přeloží na "Balíček B."  
  
## <a name="tokens-list"></a>Seznam tokenů
 V následující tabulce jsou uvedeny dostupné tokeny.  
  
|Název|Popis|  
|----------|-----------------|  
|$SharePoint.Project.FileName$|Obsahující název souboru, jako je třeba projektu *NewProj.csproj*.|  
|$SharePoint.Project.FileNameWithoutExtension$|Název souboru obsahujícího projekt bez přípony názvu souboru. Například "NewProj".|  
|$SharePoint.Project.AssemblyFullName$|Zobrazovaný název (silný název) obsahující projekt výstupu sestavení.|  
|$SharePoint.Project.AssemblyFileName$|Název projektu obsahující výstupu sestavení.|  
|$SharePoint.Project.AssemblyFileNameWithoutExtension$|Název projektu obsahující výstupu sestavení bez přípony názvu souboru.|  
|$SharePoint.Project.AssemblyPublicKeyToken$|Token veřejného klíče obsahující projektu výstupu sestavení, převedeno na řetězec. (16 znaků v "x2" šestnáctkovém formátu.)|  
|$SharePoint.Package.Name$|Název obsahující balíček.|  
|$SharePoint.Package.FileName$|Název souboru definice obsahující balíček.|  
|$SharePoint.Package.FileNameWithoutExtension$|Název definiční soubor obsahující balíčku (bez přípony).|  
|$SharePoint.Package.Id$|ID služby SharePoint obsahující balíček. Pokud funkce se používá ve více než jeden balíček, tato hodnota se změní.|  
|$SharePoint.Feature.FileName$|Název definice soubor obsahující funkce, jako například *Feature1.feature*.|  
|$SharePoint.Feature.FileNameWithoutExtension$|Název souboru bez přípony názvu souboru definice funkce.|  
|$SharePoint.Feature.DeploymentPath$|Název složky, která obsahuje funkci v balíčku. Tento token rovná vlastnost "Cesta pro nasazení" v Návrháři funkce. Příkladem hodnoty je, "Project1_Feature1".|  
|$SharePoint.Feature.Id$|ID služby SharePoint obsahující funkce. Tento token, jako se všechny funkce úrovně tokeny, lze použít pouze pomocí souborů zahrnutých v balíčku pomocí funkce, není přidal přímo do balíčku mimo funkci.|  
|$SharePoint.ProjectItem.Name$|Název položky projektu (není její název souboru), jako získaných z **ISharePointProjectItem.Name**.|  
|$SharePoint.Type. \<GUID >. AssemblyQualifiedName$|Typ odpovídající kvalifikovaný název sestavení [!INCLUDE[TLA2#tla_guid](../sharepoint/includes/tla2sharptla-guid-md.md)] tokenu. Formát [!INCLUDE[TLA2#tla_guid](../sharepoint/includes/tla2sharptla-guid-md.md)] je malá písmena a odpovídá formátu Guid.ToString("D") (tedy xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx).|  
|$SharePoint.Type. \<GUID >. Úplný název$|Úplný název typu odpovídající identifikátor GUID v tokenu. Formát identifikátoru GUID je malá písmena a odpovídá formátu Guid.ToString("D") (tedy xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx).|  
  
## <a name="add-extensions-to-the-token-replacement-file-extensions-list"></a>Přidejte rozšíření do seznamu tokenu nahrazení souboru rozšíření
 Tokeny teoreticky se dá použít ve všech souborů, které patří do projektu služby SharePoint položky zahrnuté v balíčku, ve výchozím nastavení, [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] hledání pro tokeny pouze v soubory balíčku, manifestu soubory a soubory, které mají následující přípony:  
  
-   [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)]  
  
-   ASCX  
  
-   ASPX  
  
-   Webová část  
  
-   DWP  
  
 Tato rozšíření jsou definovány `<TokenReplacementFileExtensions>` element v souboru Microsoft.VisualStudio.SharePoint.targets umístěný v... \\< soubory programu\>\MSBuild\Microsoft\VisualStudio\v11.0\SharePointTools složky.  
  
 Můžete ale přidat další přípony souborů do seznamu. Přidat `<TokenReplacementFileExtensions>` element pro všechny PropertyGroup v souboru projektu služby SharePoint, který je definován před \<Import > souboru cíle služby SharePoint.  
  
> [!NOTE]  
>  Protože tokenu nahrazení dojde po kompiluje projektu, doporučujeme nepřidávat příponám souborů pro typy souborů, které jsou kompilovány, jako například *.cs*, *VB* nebo *RESX*. Tokeny nahrazená pouze v souborech, které nejsou zkompilovat.  
  
 Chcete-li například přidat přípony názvů souborů (*.myextension* a *.yourextension*) do seznamu přípon názvů souborů tokenu nahrazení by přidejte následující do projektu (*.csproj* ) souboru:  
  
```xml  
<Project ToolsVersion="4.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <PropertyGroup>  
    <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>  
    <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>  
.  
.  
.  
    <!-- Define the following property to add your extension to the list of token replacement file extensions.  -->  
<TokenReplacementFileExtensions>myextension;yourextension</TokenReplacementFileExtensions>  
</PropertyGroup>  
```  
  
 Můžete přidat rozšíření přímo k cílům (*.targets*) souboru. Však přidání rozšíření mění seznamu rozšíření pro všechny projekty SharePoint zabalené místního systému, nejen vlastní. Toto rozšíření může být vhodné, pokud jste jediným vývojáře v systému, nebo pokud to vyžadují většina vašich projektů. Ale protože je specifické pro systém, tento přístup není přenosné a proto se doporučuje, přidejte libovolná rozšíření, do souboru projektu místo.  
  
## <a name="see-also"></a>Viz také:
 [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)  
  
