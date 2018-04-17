---
title: VSIX rozšíření schéma 2.0 – referenční informace | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- vsix
- extension schema
ms.assetid: 0da81b98-f5e3-40d3-ba9a-94551378d0b4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7459b4292220e6bb1e5a00b912efe7eb99cce825
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="vsix-extension-schema-20-reference"></a>VSIX rozšíření schéma 2.0 – referenční informace
Soubor manifestu nasazení VSIX popisuje obsah balíčku VSIX. Formát souboru se řídí schéma. Verze 2.0 toto schéma podporuje přidání vlastní typy a atributy.  Schéma manifest je rozšiřitelný. Manifestu zavaděč ignoruje XML elementů a atributů, které není pochopit.  
  
> [!IMPORTANT]
>  Visual Studio 2015 může načíst VSIX soubory v sadě Visual Studio 2010, Visual Studio 2012 nebo Visual Studio 2013 formátech.  
  
## <a name="package-manifest-schema"></a>Schéma manifestu balíčku  
 Kořenový element souboru manifestu XML `<PackageManifest>`, s jeden atribut `Version`, což je verze manifestu formátu. Pokud hlavní změn ve formátu, změní se verze formátu. Toto téma popisuje manifestu formátu verze 2.0, který je určený v manifestu nastavení `Version` atributu na hodnotu verze = "2.0".  
  
### <a name="packagemanifest-element"></a>PackageManifest Element  
 V rámci `<PackageManifest>` kořenový element, můžete použít následující prvky:  
  
-   `<Metadata>` -Metadata a reklamy informace o balíčku pro sám sebe. Pouze jeden `Metadata` element je povolen v manifestu.  
  
-   `<Installation>` -Tento oddíl definuje způsob, jakým tento balíček rozšíření lze nainstalovat, včetně položek SKU aplikace, které můžete nainstalovat do. Jediným `Installation` element je povolen v manifestu. Manifest musí mít `Installation` element nebo tento balíček nelze nainstalovat do všech SKU.  
  
-   `<Dependencies>` -Zde jsou definovány volitelný seznam závislosti pro tento balíček.  
  
-   `<Assets>` – Tato část obsahuje všechny prostředky obsažené v tomto balíčku. Bez této části nebude tento balíček surface žádný obsah.  
  
-   `<AnyElement>*` -Manifestu schéma je dostatečně flexibilní na to, aby další prvky. Všechny podřízené elementy nebyl rozpoznán manifestu zavaděčem jsou zveřejněné v rozhraní API Správce rozšíření jako objekty navíc XmlElement. Pomocí těchto podřízených elementů, VSIX rozšíření můžete definovat další data v souboru manifestu, který kód spuštěný v sadě Visual Studio můžete přístup za běhu. V tématu <xref:Microsoft.VisualStudio.ExtensionManager.IExtension.AdditionalElements%2A> a <xref:Microsoft.VisualStudio.ExtensionManager.IExtension.LocalizedAdditionalElements%2A>.  
  
### <a name="metadata-element"></a>Metadata – Element  
 Tato část se metadata o balíčku, svou identitu a informace inzerování. `<Metadata>` obsahuje následující prvky:  
  
-   `<Identity>` -Definuje identifikační informace pro tento balíček a obsahuje následující atributy:  
  
    -   `Id` -Tento atribut musí být jedinečné ID pro zvolený podle autora balíčku. Název musí být kvalifikovány stejným způsobem, jako jsou typy CLR namespaced: Company.Product.Feature.Name. `Id` Atribut je maximálně 100 znaků.  
  
    -   `Version` -Definuje verzi tohoto balíčku a její obsah. Tento atribut řídí formát Správa verzí sestavení CLR: Major.Minor.Build.Revision (1.2.40308.00). Balíček s vyšší číslo verze se považuje za aktualizace balíčku a může být nainstalována přes existující nainstalovaná verze.  
  
    -   `Language` -Tento atribut je výchozí jazyk pro balíček a odpovídá textových dat v této manifestu. Tento atribut následuje konvence kód národního prostředí CLR pro sestavení prostředků, například: en-us, en, fr-fr. Můžete zadat `neutral` deklarovat jazykově neutrální rozšíření, která bude spustit na libovolné verzi sady Visual Studio. Výchozí hodnota je `neutral`.  
  
    -   `Publisher` -Tento atribut určuje vydavatele tohoto balíčku, a to buď společnosti nebo jednotlivé název. `Publisher` Atribut je maximálně 100 znaků.  
  
-   `<DisplayName>` -Tento element určuje název uživatelsky přívětivý balíčku, který se zobrazí v uživatelském rozhraní Správce rozšíření. `DisplayName` Obsahu je omezená na 50 znaků.  
  
-   `<Description>` – Tato volitelná element je krátký popis balíčku a její obsah, který se zobrazí v uživatelském rozhraní Správce rozšíření. `Description` Obsahu může obsahovat libovolný text, který chcete, ale je omezena na 1 000 znaků.  
  
-   `<MoreInfo>` -Tento volitelný element má adresu URL online stránky, která obsahuje úplný popis tohoto balíčku. Protokol musí být zadány jako http.  
  
-   `<License>` – Tato volitelná element je relativní cesta k licenční soubor (.txt, .rtf) obsažené v balíčku.  
  
-   `<ReleaseNotes>` – Tato volitelná element je buď relativní cesta k souboru poznámky k verzi obsažené v balíčku (.txt, .rtf), jinak se adresa URL webu, který se zobrazí v poznámkách k verzi.  
  
-   `<Icon>` – Tato volitelná element je relativní cesta k souboru obrázku (png, bmp, jpeg, ico) obsažené v balíčku. Obrázek ikony musí být 32 x 32 pixelů (nebo bude možné zmenšit tato velikost) a zobrazí se v listview uživatelského rozhraní. Pokud žádné `Icon` zadaný element, uživatelské rozhraní používá výchozí.  
  
-   `<PreviewImage>` – Tato volitelná element je relativní cesta k souboru obrázku (png, bmp, jpeg) obsažené v balíčku. Náhled obrázku musí být 200 x 200 pixelů a zobrazí v podrobnostech uživatelského rozhraní. Pokud žádné `PreviewImage` zadaný element, uživatelské rozhraní používá výchozí.  
  
-   `<Tags>` – Tato volitelná element uvádí další text oddělený středníkem značky, které se používají pro tipy pro hledání. `Tags` Element je maximálně 100 znaků.  
  
-   `<GettingStartedGuide>` – Tato volitelná element je buď relativní cestu do souboru HTML, nebo adresu URL webu, který obsahuje informace o tom, jak používat rozšíření nebo v rámci tohoto balíčku obsahu. Tento průvodce se spustí jako součást instalace.  
  
-   `<AnyElement>*` -Manifestu schéma je dostatečně flexibilní na to, aby další prvky. Všechny podřízené elementy, které nejsou rozpoznány manifestu zavaděčem jsou zveřejněné jako seznam objektů XmlElement. Pomocí těchto podřízených elementů, můžete rozšíření VSIX definovat další data v souboru manifestu a výčet je za běhu.  
  
### <a name="installation-element"></a>Element instalace  
 Tento oddíl definuje způsob, jakým tento balíček lze nainstalovat a SKU aplikace, které můžete nainstalovat do. Tato část obsahuje následující atributy:  
  
-   `Experimental` – Nastavte tento atribut na hodnotu true, pokud máte rozšíření, která je aktuálně nainstalována pro všechny uživatele, ale vyvíjíte aktualizovaná verze na stejném počítači. Například pokud jste nainstalovali MyExtension 1.0 pro všechny uživatele, ale chcete ladit MyExtension 2.0 na stejném počítači, nastavte experimentální = "true". Tento atribut je k dispozici ve Visual Studiu 2015 Update 1 nebo novější.  
  
-   `Scope` -Tento atribut může mít hodnotu "Globální" nebo "ProductExtension":  
  
    -   "Globální" Určuje, že instalace není v oboru konkrétní SKU. Například tato hodnota se používá při instalaci sady SDK rozšíření.  
  
    -   "ProductExtension" Určuje, zda je nainstalován tradiční VSIX rozšíření (verze 1.0) pro obor pro jednotlivé SKU Visual Studio. Jedná se o výchozí hodnotu.  
  
-   `AllUsers` -Tento volitelný atribut určuje, zda tento balíček se nainstalují pro všechny uživatele. Ve výchozím nastavení, tento atribut je nastavena hodnota false, která určuje, že balíček je na uživatele. (Pokud tuto hodnotu nastavíte na hodnotu true, instalaci uživatel musí zvýšit úroveň administrativní oprávnění k instalaci výsledné VSIX.  
  
-   `InstalledByMsi` -Tento volitelný atribut určuje, zda tento balíček je nainstalována pomocí souboru MSI. Balíčky nainstalované pomocí souboru MSI jsou nainstalované a spravovat MSI (programy a funkce) a ne Visual Studio rozšíření správcem.  Ve výchozím nastavení, tento atribut je nastavena hodnota false, která určuje, že balíček není nainstalovaný pomocí souboru MSI.  
  
-   `SystemComponent` -Tento volitelný atribut určuje, zda tento balíček považovat za součást systému. Součásti systému nezobrazovat v uživatelském rozhraní Správce rozšíření a nelze ji aktualizovat. Ve výchozím nastavení, tento atribut je nastavena hodnota false, která určuje, že balíček není součást systému.  
  
-   `AnyAttribute*` -Na `Installation` element přijímá zprostředkovává sadu atributů, které se zveřejní za běhu jako slovník dvojice název hodnota.  
  
-   `<InstallationTarget>` -Tento element určuje umístění, kde VSIX instalační program nainstaluje balíček. Pokud hodnota `Scope` atribut je "ProductExtension" balíček musí mít jako cíl SKU, který byl nainstalován soubor manifestu jako součást svůj obsah rozbalí do inzerovat jeho dostupnost na rozšíření. `<InstallationTarget>` Element má následující atributy, kdy `Scope` atribut má explicitní nebo výchozí hodnotu "ProductExtension":  
  
    -   `Id` -Tento atribut určuje balíček.  Atribut konvenci, obor názvů: Company.Product.Feature.Name. `Id` Atribut může obsahovat pouze alfanumerické znaky a maximálně 100 znaků. Očekávaných hodnot:  
  
        -   Microsoft.VisualStudio.IntegratedShell  
  
        -   Microsoft.VisualStudio.Pro  
  
        -   Microsoft.VisualStudio.Premium  
  
        -   Microsoft.VisualStudio.Ultimate  
  
        -   Microsoft.VisualStudio.VWDExpress  
  
        -   Microsoft.VisualStudio.VPDExpress  
  
        -   Microsoft.VisualStudio.VSWinExpress  
  
        -   Microsoft.VisualStudio.VSLS  
  
        -   My.Shell.App  
  
    -   `Version` -Tento atribut určuje rozsah verze s minimální a maximální podporované verze skladové jednotky. Balíček můžete podrobnosti verze SKU, které podporuje. Zápis rozsah verze je [10.0-11.0], kde  
  
        -   [-minimální verze (včetně).  
  
        -   ]-maximální verze (včetně).  
  
        -   (-minimální verze výhradní.  
  
        -   )-výhradní maximální verze.  
  
        -   Jedna verze # - jenom určená verze.  
  
        > [!IMPORTANT]
        >  Verze 2.0 schéma VSIX byla zavedena v sadě Visual Studio 2012. Pro toto schéma používají, musí mít Visual Studio 2012 nebo později v počítači nainstalován a použít VSIXInstaller.exe která je součástí tohoto produktu. Můžete určit cílovou starší verze sady Visual Studio s Visual Studio 2012 nebo novější VSIXInstaller, ale pouze pomocí novější verze Instalační služby.  
  
    -   `AnyAttribute*` -Na `<InstallationTarget>` element umožňuje zprostředkovává sadu atributů, které budete zpřístupněny v době běhu jako slovník dvojice název hodnota.  
  
### <a name="dependencies-element"></a>Dependencies – Element  
 Tento prvek obsahuje seznam závislosti, které deklaruje tento balíček. Pokud všechny závislosti jsou nastaveny, tyto balíčky (identifikovaný jejich `Id`) musí být nainstalovány před.  
  
-   `<Dependency>` Element – tento podřízený element má následující atributy:  
  
    -   `Id` -Tento atribut musí být jedinečné ID pro závislý balíček. Tato hodnota identity musí odpovídat `<Metadata><Identity>Id` atribut balíčku, který tento balíček je závislá na. `Id` Atribut konvenci, obor názvů: Company.Product.Feature.Name. Atribut může obsahovat pouze alfanumerické znaky a maximálně 100 znaků.  
  
    -   `Version` -Tento atribut určuje rozsah verze s minimální a maximální podporované verze skladové jednotky. Balíček můžete podrobnosti verze SKU, které podporuje. Zápis rozsah verze je [12,0, 13,0], kde:  
  
        -   [-minimální verze (včetně).  
  
        -   ]-maximální verze (včetně).  
  
        -   (-minimální verze výhradní.  
  
        -   )-výhradní maximální verze.  
  
        -   Jedna verze # - jenom určená verze.  
  
    -   `DisplayName` -Tento atribut je zobrazovaný název závislý balíček, který je používán prvky uživatelského rozhraní, jako je například dialogových oken a chybové zprávy. Atribut je nepovinný, pokud je závislý balíček nainstalován pomocí Instalační služby MSI.  
  
    -   `Location` -Tento volitelný atribut určuje buď v rámci této VSIX vnořené balíčku VSIX relativní cesta nebo adresa URL k umístění stahování pro závislost. Tento atribut slouží k pomůže uživateli vyhledejte balíček požadovaných součástí.  
  
    -   `AnyAttribute*` -Na `Dependency` element přijímá zprostředkovává sadu atributů, které se zveřejní za běhu jako slovník dvojice název hodnota.  
  
### <a name="assets-element"></a>Element prostředky  
 Tento prvek obsahuje seznam `<Asset>` značky pro každý prvek rozšíření nebo obsahu prezentované podle tohoto balíčku.  
  
-   `<Asset>` -Tento prvek obsahuje následující atributy a elementy:  
  
    -   `Type` -Toto je typ rozšíření nebo obsah reprezentována tohoto elementu. Každý `<Asset>` element musí mít jeden `Type`, ale více `<Asset>` elementy může mít stejný `Type`. Tento atribut by měl být reprezentován jako plně kvalifikovaný název, podle konvence oboru názvů. Známé typy jsou:  
  
        1.  Microsoft.VisualStudio.VsPackage  
  
        2.  Microsoft.VisualStudio.MefComponent  
  
        3.  Microsoft.VisualStudio.ToolboxControl  
  
        4.  Microsoft.VisualStudio.Samples  
  
        5.  Microsoft.VisualStudio.ProjectTemplate  
  
        6.  Microsoft.VisualStudio.ItemTemplate  
  
        7.  Microsoft.VisualStudio.Assembly  
  
         Můžete vytvořit vlastní typy a přiřadit jim jedinečné názvy. V době běhu v sadě Visual Studio můžete kód výčet a využít tyto vlastní typy prostřednictvím rozhraní API Správce rozšíření.  
  
    -   Cesta - relativní cestu k souboru nebo složky v balíčku, který obsahuje asset.  
  
    -   `AnyAttribute*` -Zprostředkovává sadu atributů, které budete vystavený v době běhu jako slovník dvojice název hodnota.  
  
         `<AnyElement>*` -Všechny strukturovaných obsah je povoleno mezi `<Asset>` začínat a končit značky. Všechny elementy jsou zveřejněné jako seznam objektů XmlElement. VSIX rozšíření můžete definovat strukturovaných metadata specifická pro typ v souboru manifestu a výčet je za běhu.  
  
### <a name="sample-manifest"></a>Ukázka manifestu  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<PackageManifest Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vsx-schema/2011" xmlns:d="http://schemas.microsoft.com/developer/vsx-schema-design/2011">  
  <Metadata>  
    <Identity Id="0000000-0000-0000-0000-000000000000" Version="1.0" Language="en-US" Publisher="Company" />  
    <DisplayName>Test Package</DisplayName>  
    <Description>Information about my package</Description>  
    <MoreInfo>http://www.fabrikam.com/Extension1/</MoreInfo>  
    <License>eula.rtf</License>  
    <ReleaseNotes>notes.txt</ReleaseNotes>  
    <Icon>Images\icon.png</Icon>  
    <PreviewImage>Images\preview.png</PreviewImage>  
  </Metadata>  
  <Installation InstalledByMsi="false" AllUsers="false" SystemComponent="false" Scope="ProductExtension">  
    <InstallationTarget Id="Microsoft.VisualStudio.Pro" Version="[11.0, 12.0]" />  
  </Installation>  
  <Dependencies>  
    <Dependency Id="Microsoft.Framework.NDP" DisplayName="Microsoft .NET Framework" d:Source="Manual" Version="[4.5,)" />  
    <Dependency Id="Microsoft.VisualStudio.MPF.12.0" DisplayName="Visual Studio MPF 12.0" d:Source="Installed" Version="[12.0]" />  
  </Dependencies>  
  <Assets>  
    <Asset Type="Microsoft.VisualStudio.VsPackage" d:Source="Project" d:ProjectName="%CurrentProject%" Path="|%CurrentProject%;PkgdefProjectOutputGroup|" />  
  </Assets>  
</PackageManifest>  
```  
  
## <a name="see-also"></a>Viz také  
 [Odesílání rozšíření sady Visual Studio](../extensibility/shipping-visual-studio-extensions.md)