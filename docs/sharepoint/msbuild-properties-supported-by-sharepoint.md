---
title: "Vlastnosti nástroje MSBuild podporované službou SharePoint | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, MSBuild properties
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 115896965eb47eb6dc4a9cdbb0b9df8dd8972c5f
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="msbuild-properties-supported-by-sharepoint"></a>Vlastnosti nástroje MSBuild podporované službou SharePoint
  Všechny [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] mohou být používány v souboru, soubor projektu nebo soubor projektu uživatele Microsoft.VisualStudio.SharePoint.targets definovánu vlastnost [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] projektů služby SharePoint. Kromě nejběžnější [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] vlastnosti poskytl projektu služby SharePoint definuje další vlastnosti, které jsou specifické pro projekty SharePoint.  
  
 Seznam běžné [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] najdete v části vlastnosti, [běžné vlastnosti projektu nástroje MSBuild](http://go.microsoft.com/fwlink/?LinkID=168687). Úplný seznam vlastnostech podporovaných zprostředkovatelem programovací jazyk, najdete v souboru .targets, soubor projektu (.csproj nebo .vbproj) nebo soubor projektu uživatele (csproj.user nebo. vbproj.user).  
  
## <a name="msbuild-properties-specific-to-sharepoint"></a>Konkrétní vlastnosti nástroje MSBuild do služby SharePoint  
 Následující tabulka uvádí [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] vlastnosti, které platí konkrétně do projektů služby SharePoint v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Existují další vlastnosti, ale jsou pro interní použití.  
  
|Název vlastnosti|Popis|  
|-------------------|-----------------|  
|SharePointSiteUrl|Řetězec, který představuje [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)] na stránku služby SharePoint.|  
|SandboxedSolution|Logická hodnota, která určuje, zda je řešení řešení v izolovaném prostoru.|  
|ActiveDeploymentConfiguration|Konfigurace aktivní nasazení.|  
|IncludeAssemblyInPackage|Logická hodnota, která určuje, zda je sestavení součástí souboru balíčku.|  
|PreDeploymentCommand|Řetězcovou hodnotu, kterou představuje spuštění příkazu v kroku před nasazením příkaz.|  
|PostDeploymentCommand|Hodnotu řetězce, který představuje spuštění příkazu v kroku příkaz po nasazení.|  
|CustomBeforeSharePointTargets|Řetězec, který představuje cestu [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] souboru cíle. Pokud cíle soubor existuje a je definován, je importována před všechny cíle dat služby SharePoint. Tato vlastnost umožňuje přizpůsobit proces balíčku předběžné definování vlastnosti týkající se balení beze změny souboru uvidíte cíle služby SharePoint, ale soubor cíle stále platí pro všechny projekty SharePoint.|  
|CustomAfterSharePointTargets|Řetězec, který představuje cestu [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] souboru cíle. Pokud cíle soubor existuje a je definován, je po všech importovaných dat cíle služby SharePoint. Tato vlastnost umožňuje přizpůsobit proces balíčku přepsáním vlastnosti týkající se vytváření balíčků a cíle, aniž by museli měnit uvidíte soubor cíle služby SharePoint, ale soubor cíle stále platí pro všechny projekty SharePoint.|  
|LayoutPath|Řetězec, který představuje kořenový adresář každý ze souborů k zabalené dočasně umístění předtím, než budou přidány do souboru WSP. Tato cesta může být užitečné při přepsání BeforeLayout a AfterLayout cíle přidat, odebrat nebo upravit soubory a zabalí, protože se používají pro úpravu obsah souboru WSP znát.|  
|BasePackagePath|Řetězec, který představuje složku, ve kterém je umístěn daný balíček. Tato hodnota používá výstupnímu adresáři projektu, například Bin\Debug.|  
|PackageExtension|Řetězec, který představuje příponu názvu souboru pro připojení k balíčku. Výchozí hodnota je wsp.|  
|AssemblyDeploymentTarget|Řetězec, který představuje umístění, kde je sestavení projektu nasazen na serveru SharePoint. Jeho hodnota může být GlobalAssemblyCache (výchozí) nebo webovou aplikaci. Tuto vlastnost lze nastavit i v okně Vlastnosti.|  
|PackageWithValidation|Logická hodnota, která určuje, zda se před balení provádí ověřování. Tato vlastnost umožňuje ignorování chyb ověření při vytváření balíčků.|  
|ValidatePackageDependsOn|Řetězec, který definuje další cíle ke spuštění před ValidatePackage cíl.|  
|TokenReplacementFileExensions|Řetězec, který definuje, které obsahují jejich tokeny nahrazena v průběhu balení.|  
  
## <a name="using-msbuild-properties-in-the-properties-page"></a>Na stránce vlastností pomocí vlastnosti nástroje MSBuild  
 Flexibilitu, místo použití pevně řetězce v **před nasazením příkazového řádku** a **po nasazení příkazového řádku** polí na stránce Vlastnosti služby SharePoint můžete použít webu služby SharePoint vlastnosti jako argumenty. Například místo zadávání konkrétní [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)] řetězec pro web služby SharePoint, můžete místo toho použít `$(SharePointSiteUrl)`.  
  
> [!NOTE]  
>  Můžete použít buď [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] proměnné syntaxe `$(` *propertyName* `)` nebo syntaxe proměnné prostředí `%` *propertyName* `%` Chcete-li určit vlastnost.  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace nástroje MSBuild](/visualstudio/msbuild/msbuild-reference)  
  
  