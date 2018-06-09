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
ms.workload:
- office
ms.openlocfilehash: 407094a1598fa9870866830ac0c40b78a9f615a8
ms.sourcegitcommit: 269b55b413d2c82e6aa56c6ab8e53da7926fb2e8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/08/2018
ms.locfileid: "35237962"
---
# <a name="replaceable-parameters"></a>Nahraditelné parametry

Nahraditelné parametry, nebo *tokeny*, dá se použít uvnitř soubory projektu zadat hodnoty pro položky řešení služby SharePoint, jejichž skutečnými hodnotami nejsou známá v době návrhu. Jsou podobně jako u standardní tokeny šablony sady Visual Studio. Další informace najdete v tématu [parametry šablony](../ide/template-parameters.md).

## <a name="token-format"></a>Formát tokenu

Tokeny nezačíná a nekončí znak dolaru ($). Tokeny se nahradí skutečnými hodnotami, když na projekt se zabalí do balíčku řešení služby SharePoint (soubor WSP) v nasazení. Například token **$SharePoint.Package.Name$** může vyřešit řetězec "Test SharePoint balíček".

## <a name="token-rules"></a>Token pravidla

Následující pravidla platí při tokenů:

- Tokeny lze zadat kdekoli v řádku.

- Tokeny nemůže zahrnovat více řádků.

- Stejný token může být zadána vícekrát na stejném řádku a ve stejném souboru.

- Na stejném řádku je možné zadat jiný tokeny.

Tokeny, které nejsou postupujte podle těchto pravidel se ignorují bez zadání upozornění nebo chyby.

Okamžitě po transformaci manifestu se provádí nahrazení tokeny pomocí řetězcových hodnot. Tato nahrazení umožňuje uživateli upravit manifestu šablony s tokeny.

### <a name="token-name-resolution"></a>Token překlad

Ve většině případů token přeloží na konkrétní hodnotu bez ohledu na to, kde se nachází. Ale pokud token je spojena s balíčku nebo funkce, je token hodnota závisí na kterém se nachází. Pokud je funkce v balíčku pak se token `$SharePoint.Package.Name$` přeloží na hodnotu "Balíček A". Pokud stejné funkce je v balíčku B, pak `$SharePoint.Package.Name$` přeloží na "Balíček B".

## <a name="tokens-list"></a>Seznam tokenů

V následující tabulce jsou uvedeny dostupné tokeny:

|Název|Popis|
|----------|-----------------|
|$SharePoint.Project.FileName$|Obsahující název souboru, jako například projektu **NewProj.csproj**.|
|$SharePoint.Project.FileNameWithoutExtension$|Název souboru obsahujícího projekt bez přípony názvu souboru. Například **NewProj**.|
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
|$SharePoint.Feature.DeploymentPath$|Název složky, která obsahuje funkci v balíčku. Tento token rovná vlastnost "Cesta pro nasazení" v Návrháři funkce. Příkladem hodnoty je **Project1_Feature**.|
|$SharePoint.Feature.Id$|ID služby SharePoint obsahující funkce. Tento token, stejně jako u všech tokenů úrovni funkcí, můžete používat jenom soubory obsažené v balíčku pomocí funkce a není přímo do balíčku mimo funkci přidat.|
|$SharePoint.ProjectItem.Name$|Název položky projektu (není její název souboru), jako získaných z **ISharePointProjectItem.Name**.|
|$SharePoint.Type. \<GUID >. AssemblyQualifiedName$|Kvalifikovaný název sestavení typu odpovídající identifikátor GUID tokenu. Formát identifikátoru GUID je malá písmena a odpovídá formátu Guid.ToString("D") (tedy xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx).|
|$SharePoint.Type. \<GUID >. Úplný název$|Úplný název typu odpovídající identifikátor GUID v tokenu. Formát identifikátoru GUID je malá písmena a odpovídá formátu Guid.ToString("D") (tedy xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx).|

## <a name="add-extensions-to-the-token-replacement-file-extensions-list"></a>Přidejte rozšíření do tokenu nahrazení souboru rozšíření seznamu

Tokeny lze teoreticky ve všech souborů, které patří do položky projektu služby SharePoint zahrnuté v balíčku, ve výchozím nastavení, Visual Studio hledá tokeny pouze v souboru balíčku, ale manifest soubory a soubory, které mají následující přípony:

- XML

- ASCX

- ASPX

- Webová část

- DWP

Tato rozšíření jsou definovány `<TokenReplacementFileExtensions>` element v *Microsoft.VisualStudio.SharePoint.targets* soubor umístěný ve složce *% ProgramFiles (x86) %\MSBuild\Microsoft\VisualStudio\v14.0\ SharePointTools* složky.

Můžete ale přidat další přípony souborů do seznamu. Přidat `<TokenReplacementFileExtensions>` element pro všechny PropertyGroup v souboru projektu služby SharePoint, který je definován před \<Import > souboru cíle služby SharePoint.

> [!NOTE]
> Protože tokenu nahrazení dojde po kompiluje projektu, byste neměli přidávat přípony souborů pro typy souborů, které jsou kompilovány, třeba cs, vb nebo RESX. Tokeny nahrazená pouze v souborech, které nejsou zkompilovat.

Chcete-li například přidat přípony názvů souborů *.myextension* a *.yourextension* do seznamu přípon názvů souborů tokenu nahrazení, přidejte následující *.csproj* soubor:

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

Rozšíření můžete přidat přímo na *.targets* souboru. Tím však mění seznamu rozšíření pro všechny projekty SharePoint zabalené místního systému, ne jenom vlastní. Změna seznamu rozšíření pro všechny projekty SharePoint může být vhodné, když jste jedinou developer, nebo pokud to vyžadují většina vašich projektů. Ale tento přístup není přenosné, protože je specifické pro systém. Doporučuje se místo toho přidejte rozšíření do souboru projektu.

## <a name="see-also"></a>Viz také:

- [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)