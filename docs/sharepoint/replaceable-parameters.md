---
title: "Nahraditelné parametry | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
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
ms.assetid: 3c46bbb1-0a98-495c-9fd1-dc57a6aedc11
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 80f9770fe0e6a0294ec43e450acc75f55b8ddbe2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="replaceable-parameters"></a>Nahraditelné parametry
  Nahraditelné parametry, nebo *tokeny*, dá se použít uvnitř soubory projektu zadat hodnoty pro položky řešení služby SharePoint, jejichž skutečnými hodnotami nejsou známá v době návrhu. Jsou podobně jako u standardní [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] tokeny šablony. Další informace najdete v tématu [parametry šablony](/visualstudio/ide/template-parameters).  
  
## <a name="token-format"></a>Formát tokenu  
 Tokeny nezačíná a nekončí znak dolaru ($). Použití tokenů se nahradí skutečnými hodnotami, když na projekt je zabalené do souboru balíčku (WSP) řešení služby SharePoint v době nasazení. Například token **$SharePoint.Package.Name$** může vyřešit řetězec "Test SharePoint balíček."  
  
## <a name="token-rules"></a>Token pravidla  
 Následující pravidla platí při tokenů:  
  
-   Tokeny lze zadat kdekoli v řádku.  
  
-   Tokeny nemůže zahrnovat více řádků.  
  
-   Stejný token může být zadána vícekrát na stejném řádku a ve stejném souboru.  
  
-   Na stejném řádku je možné zadat jiný tokeny.  
  
 Tokeny, které se neřídí tato pravidla se ignorují bez zadání upozornění nebo chyby.  
  
 Okamžitě po manifestu transformaci, což umožňuje manifestu šablony upravit uživatelem, aby používala tokeny se provádí nahrazení tokeny pomocí řetězcových hodnot.  
  
### <a name="token-name-resolution"></a>Token překlad  
 Ve většině případů token přeloží na konkrétní hodnotu bez ohledu na to, kde se nachází. Ale pokud token je spojena s balíčku nebo funkce, je token hodnota závisí na kterém se nachází. Například pokud je funkce v balíčku pak se token `$SharePoint.Package.Name$` přeloží na hodnotu "Balíček A." Pokud stejné funkce je v balíčku B, pak `$SharePoint.Package.Name$` přeloží na "Balíček B."  
  
## <a name="tokens-list"></a>Seznam tokenů  
 V následující tabulce jsou uvedeny dostupné tokeny.  
  
|Název|Popis|  
|----------|-----------------|  
|$SharePoint.Project.FileName$|Název souboru obsahujícího projektu, například "NewProj.csproj".|  
|$SharePoint.Project.FileNameWithoutExtension$|Název souboru obsahujícího projekt bez přípony názvu souboru. Například "NewProj".|  
|$SharePoint.Project.AssemblyFullName$|Zobrazovaný název (silný název) obsahující projekt výstupu sestavení.|  
|$SharePoint.Project.AssemblyFileName$|Název projektu obsahující výstupu sestavení.|  
|$SharePoint.Project.AssemblyFileNameWithoutExtension$|Název projektu obsahující výstupu sestavení bez přípony názvu souboru.|  
|$SharePoint.Project.AssemblyPublicKeyToken$|Token veřejného klíče obsahující projektu výstupu sestavení, převedeno na řetězec. (16 znaků v "x2" šestnáctkovém formátu.)|  
|$SharePoint.Package.Name$|Název obsahující balíček.|  
|$SharePoint.Package.FileName$|Název souboru definice obsahující balíček.|  
|$SharePoint.Package.FileNameWithoutExtension$|Název definiční soubor obsahující balíčku (bez přípony).|  
|$SharePoint.Package.Id$|ID služby SharePoint obsahující balíček. Pokud funkce se používá ve více než jeden balíček, tato hodnota se změní.|  
|$SharePoint.Feature.FileName$|Název souboru definice obsahující funkce, jako je například Feature1.feature.|  
|$SharePoint.Feature.FileNameWithoutExtension$|Název souboru bez přípony názvu souboru definice funkce.|  
|$SharePoint.Feature.DeploymentPath$|Název složky, která obsahuje funkci v balíčku. Tento token rovná vlastnost "Cesta pro nasazení" v Návrháři funkce. Příkladem hodnoty je, "Project1_Feature1".|  
|$SharePoint.Feature.Id$|ID služby SharePoint obsahující funkce. Tento token, jako se všechny funkce úrovně tokeny, lze použít pouze pomocí souborů zahrnutých v balíčku pomocí funkce, není přidal přímo do balíčku mimo funkci.|  
|$SharePoint.ProjectItem.Name$|Název položky projektu (není její název souboru), jako získaných z **ISharePointProjectItem.Name**.|  
|$SharePoint.Type. \<GUID >. AssemblyQualifiedName$|Typ odpovídající kvalifikovaný název sestavení [!INCLUDE[TLA2#tla_guid](../sharepoint/includes/tla2sharptla-guid-md.md)] tokenu. Formát [!INCLUDE[TLA2#tla_guid](../sharepoint/includes/tla2sharptla-guid-md.md)] je malá písmena a odpovídá formátu Guid.ToString("D") (tedy xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx).|  
|$SharePoint.Type. \<GUID >. Úplný název$|Úplný název typu odpovídající identifikátor GUID v tokenu. Formát identifikátoru GUID je malá písmena a odpovídá formátu Guid.ToString("D") (tedy xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx).|  
  
## <a name="adding-extensions-to-the-token-replacement-file-extensions-list"></a>Přidání rozšíření do tokenu nahrazení souboru rozšíření seznamu  
 Tokeny teoreticky se dá použít ve všech souborů, které patří do projektu služby SharePoint položky zahrnuté v balíčku, ve výchozím nastavení, [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] hledání pro tokeny pouze v soubory balíčku, manifestu soubory a soubory, které mají následující přípony:  
  
-   [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)]  
  
-   ASCX  
  
-   ASPX  
  
-   Webová část  
  
-   DWP  
  
 Tato rozšíření jsou definovány `<TokenReplacementFileExtensions>` element v souboru Microsoft.VisualStudio.SharePoint.targets umístěný v... \\< soubory programu\>\MSBuild\Microsoft\VisualStudio\v11.0\SharePointTools složky.  
  
 Můžete ale přidat další přípony souborů do seznamu. Chcete-li to provést, přidejte `<TokenReplacementFileExtensions>` element pro všechny PropertyGroup v souboru projektu služby SharePoint, který je definován před \<Import > souboru cíle služby SharePoint.  
  
> [!NOTE]  
>  Protože tokenu nahrazení dojde po kompiluje projektu, byste neměli přidávat přípony souborů pro typy souborů, které jsou kompilovány, třeba cs, vb nebo RESX. Tokeny nahrazená pouze v souborech, které nejsou zkompilovat.  
  
 Například by pokud chcete přidat do seznamu přípon názvů souborů tokenu nahrazení souboru název rozšíření ".myextension" a ".yourextension", přidejte následující do souboru .csproj:  
  
```  
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
  
 Alternativně můžete přidat rozšíření přímo do souboru .targets. To však mění seznamu rozšíření pro všechny projekty SharePoint zabalené místního systému, ne jenom vlastní. To může být vhodné, pokud jste jediným vývojáře v systému, nebo pokud to vyžadují většina vašich projektů. Ale protože je specifické pro systém, tento přístup není úplně přenosný a proto se doporučuje, přidejte libovolná rozšíření, do souboru projektu místo.  
  
## <a name="see-also"></a>Viz také  
 [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)  
  
  