---
title: Podpora pro projekt a vlastnosti konfigurace | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project properties, supporting with Visual Studio SDK
- configuration properties, suppporting with Visual Studio SDK
ms.assetid: 9fcfaa0f-7b41-4b68-82ec-7a151dca5d7e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 823bfa0453d3e33fea2daa51779b1fe4800a1a86
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31133570"
---
# <a name="support-for-project-and-configuration-properties"></a>Podpora pro projekt a vlastnosti konfigurace
**Vlastnosti** okno v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE) můžete zobrazit vlastnosti projektu a konfigurace. Stránky vlastností můžete zadat pro vlastní typ projektu, takže uživatel může nastavit vlastnosti pro vaši aplikaci.  
  
 Výběrem uzlu projektu v **Průzkumníku řešení** a pak levým na **vlastnosti** na **projektu** nabídky, můžete otevřít dialogové okno obsahující projekt a konfigurace Vlastnosti. V [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] a [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)]a typy odvozené z těchto jazyků tohoto dialogového okna se zobrazí jako stránce s kartami v projektu [Obecné, prostředí, dialogové okno Možnosti](../../ide/reference/general-environment-options-dialog-box.md). Další informace najdete v tématu [není v sestavení: Návod: vystavení projektu a vlastnosti konfigurace (C#)](http://msdn.microsoft.com/en-us/d850d63b-25e2-4505-9f3d-eb038d7c1d0e).  
  
 Spravovaná rozhraní balíčku pro projekty (MPFProj) poskytuje pomocné třídy pro vytváření a správu nového projektu systému. Zdrojový kód a kompilace pokyny naleznete v [sady MPF projektů – Visual Studio 2013](http://mpfproj12.codeplex.com/).  
  
## <a name="persistence-of-project-and-configuration-properties"></a>Trvalost projektu a vlastnosti konfigurace  
 Vlastnosti projektu a konfigurace jsou ukládány v souboru projektu, který má příponu názvu souboru, například přidružený typ projektu, .csproj, .vbproj a .myproj. Soubor šablony projektů jazyka obvykle používají ke generování souboru projektu. Existují však ve skutečnosti několik způsobů, jak přidružit typy projektů a šablon. Další informace najdete v tématu [Directory popis šablony (. Soubory VSDIR)](../../extensibility/internals/template-directory-description-dot-vsdir-files.md).  
  
 Vlastnosti projektu a konfigurace jsou vytvořené pomocí přidávání položek do souboru šablony. Tyto vlastnosti jsou pak k dispozici žádné vytvořených pomocí typu projektu, který používá tato šablona projektů. [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] projekty a MPFProj používejte [není v sestavení: Přehled nástroje MSBuild](http://msdn.microsoft.com/en-us/b588fd73-a45b-4706-908f-cc131bccfbde) schématu pro soubory šablon. Tyto soubory obsahují PropertyGroup – část pro každou konfiguraci. Vlastnosti projekty jsou obvykle ukládány v první části PropertyGroup, který má argumentem konfigurace nastavena na hodnotu null. řetězec.  
  
 Následující kód ukazuje základní soubor projektu nástroje MSBuild spuštění.  
  
```  
<Project MSBuildVersion="2.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <PropertyGroup>  
    <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>  
    <Name>SomeProjectSix</Name>  
    <SchemaVersion>2.0</SchemaVersion>  
  </PropertyGroup>  
  <PropertyGroup Condition=" '$(Configuration)' == 'Debug' ">  
    <Optimize>false</Optimize>  
  </PropertyGroup>  
  <PropertyGroup Condition=" '$(Configuration)' == 'Release' ">  
    <Optimize>true</Optimize>  
```  
  
 V tomto souboru projektu `<Name>` a `<SchemaVersion>` jsou vlastnosti projektu a `<Optimize>` je vlastnost konfigurace.  
  
 Je zodpovědností projekt, který má zachovat vlastnosti projektu a konfiguraci souboru projektu.  
  
> [!NOTE]
>  Projekt můžete optimalizovat trvalost zachování pouze hodnoty vlastností, které se liší od výchozí hodnoty.  
  
## <a name="support-for-project-and-configuration-properties"></a>Podpora pro projekt a vlastnosti konfigurace  
 `Microsoft.VisualStudio.Package.SettingsPage` Třída implementuje stránky vlastností projektu a konfigurace. Výchozí implementaci `SettingsPage` nabízí veřejné vlastnosti pro uživatele v mřížce obecná vlastnost. `Microsoft.VisualStudio.Package.HierarchyNode.GetPropertyPageGuids` Metoda vybere třídy odvozené od třídy `SettingsPage` pro mřížek vlastností projektu. `Microsoft.VisualStudio.Package.ProjectNode.GetConfigPropertyPageGuids` Metoda vybere třídy odvozené od třídy `SettingsPage` pro mřížek vlastností konfigurace. Typ vašeho projektu by měly přepsat tyto metody a vyberte příslušné vlastnosti stránky.  
  
 `SettingsPage` Třídy a `Microsoft.VisualStudio.Package.ProjectNode` třída nabízí tyto metody se zachovat vlastnosti projektu a konfigurace:  
  
-   `Microsoft.VisualStudio.Package.ProjectNode.GetProjectProperty` a `Microsoft.VisualStudio.Package.ProjectNode.SetProjectProperty` zachovat vlastnosti projektu.  
  
-   `Microsoft.VisualStudio.Package.SettingsPage.GetConfigProperty` a `Microsoft.VisualStudio.Package.SettingsPage.SetConfigProperty` zachovat vlastnosti konfigurace.  
  
    > [!NOTE]
    >  Implementace `Microsoft.VisualStudio.Package.SettingsPage` a `Microsoft.VisualStudio.Package.ProjectNode` třídy pomocí `Microsoft.Build.BuildEngine` metody (MSBuild) k získání a nastavení vlastností projektu a konfigurace ze souboru projektu.  
  
 Třída odvozena od `SettingsPage` musí implementovat `Microsoft.VisualStudio.Package.SettingsPage.ApplyChanges` a `Microsoft.VisualStudio.Package.SettingsPage.BindProperties` udržení projektu nebo konfigurace vlastností souboru projektu.  
  
## <a name="provideobjectattribute-and-registry-path"></a>ProvideObjectAttribute a cesta v registru  
 Třídy odvozené od `SettingsPage` jsou navrženy tak, aby se sdílené mezi VSPackages. Aby bylo možné pro VSPackage pro vytvoření třídy odvozené od `SettingsPage`, přidejte `Microsoft.VisualStudio.Shell.ProvideObjectAttribute` do třídy odvozené od `Microsoft.VisualStudio.Shell.Package`.  
  
 [!code-csharp[VSSDKSupportProjectConfigurationProperties#1](../../extensibility/internals/codesnippet/CSharp/support-for-project-and-configuration-properties_1.cs)]
 [!code-vb[VSSDKSupportProjectConfigurationProperties#1](../../extensibility/internals/codesnippet/VisualBasic/support-for-project-and-configuration-properties_1.vb)]  
  
 VSPackage, ke kterému je připojen atribut je důležitý. Pokud není zaregistrována VSPackage [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], je zaregistrován id třídy (CLSID) objektu, která se dají vytvořit tak, aby volání <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry.CreateInstance%2A> můžete ho vytvořit.  
  
 Objekt, který je možné vytvořit cestu registru je dáno kombinování <xref:Microsoft.VisualStudio.Shell.Package.UserRegistryRoot%2A>, slovo, CLSID a identifikátor guid typu objektu. Pokud `MyProjectPropertyPage` třída má identifikátor guid {3c693da2-5bca-49b3-bd95-ffe0a39dd723} a zda je UserRegistryRoot HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0Exp, poté cestu registru by HKEY_CURRENT_USER\Software\Microsoft\VisualStudio \8.0Exp\CLSID\\{3c693da2-5bca-49b3-bd95-ffe0a39dd723}.  
  
## <a name="project-and-configuration-property-attributes-and-layout"></a>Projekt a atributy vlastností konfigurace a rozložení  
 <xref:System.ComponentModel.CategoryAttribute>, <xref:System.ComponentModel.DisplayNameAttribute>, A <xref:System.ComponentModel.DescriptionAttribute> atributy určují rozložení, označování a popis vlastností projektu a konfigurace na stránce Obecné vlastnosti. Tyto atributy určit kategorii, zobrazí název a popis možnosti, v uvedeném pořadí.  
  
> [!NOTE]
>  Ekvivalentní atributy, SRCategory, LocDisplayName a SRDescription, používat prostředky řetězce pro lokalizaci a jsou definovány v [sady MPF projektů – Visual Studio 2013](http://mpfproj12.codeplex.com/).  
  
 Předpokládejme následující fragment kódu:  
  
 [!code-vb[VSSDKSupportProjectConfigurationProperties#2](../../extensibility/internals/codesnippet/VisualBasic/support-for-project-and-configuration-properties_2.vb)]
 [!code-csharp[VSSDKSupportProjectConfigurationProperties#2](../../extensibility/internals/codesnippet/CSharp/support-for-project-and-configuration-properties_2.cs)]  
  
 `MyConfigProp` Vlastnosti konfigurace se zobrazí na stránce vlastností konfigurace jako **Moje vlastnost konfigurace** v kategorii **Moje kategorie**. Pokud je vybrána možnost, popis, **Moje popis**, zobrazí se v panelu Popis.  
  
## <a name="see-also"></a>Viz také  
 [Přidávání a odebírání stránky vlastností](../../extensibility/adding-and-removing-property-pages.md)   
 [Projekty](../../extensibility/internals/projects.md)   
 [Soubory popisu adresáře šablon (.Vsdir)](../../extensibility/internals/template-directory-description-dot-vsdir-files.md)
