---
title: Vytváření Software Development Kit | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 8496afb4-1573-4585-ac67-c3d58b568a12
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 55b62ac0ac448023793f511389146ebb1b07da0f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31109175"
---
# <a name="creating-a-software-development-kit"></a>Vytváření Software Development Kit
(SDK) software development kit je kolekce rozhraní API, která jako jednu položku v sadě Visual Studio, můžete odkazovat. **Správce odkazů** dialogové okno obsahuje seznam všech sady SDK, které jsou relevantní pro projekt. Když přidáte sady SDK do projektu, rozhraní API jsou k dispozici v sadě Visual Studio.  
  
 Existují dva typy sad SDK:  
  
-   Sady SDK pro platformu jsou povinné součásti pro vývoj aplikací pro platformu. Například [!INCLUDE[win81](../debugger/includes/win81_md.md)] SDK je potřeba k vývoji [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikace.  
  
-   Rozšíření sady SDK jsou volitelné součásti, které rozšiřují platformu, ale nejsou povinné pro vývoj aplikací pro platformu.  
  
 Následující části popisují obecné infrastruktury sady SDK a jak vytvořit sadu SDK platformy a sady extension SDK.  
  
-   [Sady SDK platformy](#PlatformSDKs)  
  
-   [Rozšíření sady SDK](#ExtensionSDKs)  
  
##  <a name="PlatformSDKs"></a> Sady SDK platformy  
 Sady SDK pro platformu vyžadovaných pro vývoj aplikací pro platformu. Například [!INCLUDE[win81](../debugger/includes/win81_md.md)] SDK je potřeba k vývoji aplikací pro [!INCLUDE[win81](../debugger/includes/win81_md.md)].  
  
### <a name="installation"></a>Instalace  
 Všechny platformy sady SDK se nainstalují v HKLM\Software\Microsoft\Microsoft SDK\\\v [stopami na PALEC] [TPV]\\ @InstallationFolder = [SDK kořenové]. Podle toho [!INCLUDE[win81](../debugger/includes/win81_md.md)] SDK je nainstalována v HKLM\Software\Microsoft\Microsoft SDKs\Windows\v8.1.  
  
### <a name="layout"></a>Rozložení  
 Sady SDK platformy bude mít následující rozložení:  
  
```  
\[InstallationFolder root]  
            SDKManifest.xml  
            \References  
                  \[config]  
                        \[arch]  
            \DesignTime  
                  \[config]  
                        \[arch]  
```  
  
|Uzel|Popis|  
|----------|-----------------|  
|Složka s odkazy|Obsahuje binární soubory, které obsahují rozhraní API, která může být programového proti. Ty můžou zahrnovat soubory metadat Windows (WinMD) nebo sestavení.|  
|DesignTime složky|Obsahuje soubory, které jsou potřeba pouze v době vedlejší-run nebo ladění. Může patří dokumentace XML, knihoven, záhlaví, binární soubory sady nástrojů návrhu, MSBuild artefaktů a tak dále<br /><br /> Dokumentace XML, v ideálním případě umístěn ve složce \DesignTime, ale bude pokračovat umístit společně se souborem odkaz v sadě Visual Studio dokumentace XML pro odkazy. Například doc XML pro odkaz \References\\[Konfigurace]\\[arch]\sample.dll bude \References\\[Konfigurace]\\[arch]\sample.xml a lokalizované verze tohoto dokumentu se \References\\[Konfigurace]\\[arch]\\[locale]\sample.xml.|  
|Konfigurace složky|Může být pouze tři složky: ladění, maloobchodní a CommonConfiguration. Autoři sady SDK můžete umístit své soubory pod CommonConfiguration, pokud stejnou sadu SDK soubory by měly využívat, bez ohledu na to, konfiguraci, která se zaměří na příjemci SDK.|  
|Architektura složky|Libovolné složky podporovaná architektura může existovat. Visual Studio podporuje následující typy architektury: x86, x64, ARM a neutrální. Poznámka: Win32 mapuje x86 a AnyCPU mapuje neutrální.<br /><br /> MSBuild vyhledá pouze za \CommonConfiguration\neutral sady SDK pro platformu.|  
|SDKManifest.xml|Tento soubor popisuje, jak Visual Studio by měla využívat sadu SDK. Podívejte se na manifestu sady SDK pro [!INCLUDE[win81](../debugger/includes/win81_md.md)]:<br /><br /> `<FileList             DisplayName = "Windows"             PlatformIdentity = "Windows, version=8.1"             TargetFramework = ".NET for Windows Store apps, version=v4.5.1; .NET Framework, version=v4.5.1"             MinVSVersion = "14.0">              <File Reference = "Windows.winmd">                <ToolboxItems VSCategory = "Toolbox.Default" />             </File> </FileList>`<br /><br /> **DisplayName:** hodnotu, která zobrazí prohlížeč objektů v seznamu k procházení.<br /><br /> **PlatformIdentity:** existenci tento atribut odpovídá Visual Studio a nástroje MSBuild, sadu SDK je sadu SDK platformy a neměli zkopírují odkazy z něj přidat místně.<br /><br /> **TargetFramework:** tento atribut slouží Visual Studio k zajištění, který jenom projektů cílených stejné architektury jako zadaný v poli Hodnota tohoto atributu můžou využívat sadu SDK.<br /><br /> **MinVSVersion:** tento atribut slouží Visual Studio k využívání sady SDK, které se vztahují k němu.<br /><br /> **Referenční dokumentace:** tento atribut musí být zadaný pro pouze odkazy, které obsahují ovládací prvky. Informace o tom, jak určit, zda odkaz obsahuje ovládací prvky najdete níže.|  
  
##  <a name="ExtensionSDKs"></a> Rozšíření sady SDK  
 Následující části popisují, co je potřeba provést k nasazení rozšíření sady SDK.  
  
### <a name="installation"></a>Instalace  
 Rozšíření sady SDK můžete nainstalovat pro konkrétního uživatele nebo pro všechny uživatele bez zadání klíče registru. Chcete-li nainstalovat sadu SDK pro všechny uživatele, použijte následující cestu:  
  
 `%Program Files%\Microsoft SDKs\<target platform>\v<platform version number>\ExtensionSDKs`  
  
 Pro instalaci specifický pro uživatele použijte následující cestu:  
  
 `%USERPROFILE%\AppData\Local\Microsoft SDKs\<target platform>\v<platform version number>\ExtensionSDKs`  
  
 Pokud chcete použít jiné umístění, musíte udělat jednu ze dvou akcí:  
  
1.  Zadejte jej v klíči registru:  
  
     `HKLM\Software\Microsoft\Microsoft SDKs\<target platform>\v<platform version number>\ExtensionSDKs\<SDKName>\<SDKVersion>\`  
  
     a přidejte podklíč (výchozí), který má hodnotu `<path to SDK><SDKName><SDKVersion>`.  
  
2.  Přidání vlastnosti nástroje MSBuild `SDKReferenceDirectoryRoot` se v souboru projektu. Hodnota této vlastnosti je částečně dvojtečkou oddělený seznam adresáře, ve kterých jsou umístěny rozšíření sady SDK, kterou chcete odkazovat.  
  
### <a name="installation-layout"></a>Instalace rozložení  
 Rozšíření sady SDK mít následující rozložení instalace:  
  
```  
\<ExtensionSDKs root>  
           \<SDKName>  
                 \<SDKVersion>  
                        SDKManifest.xml  
                        \References  
                              \<config>  
                                    \<arch>  
                        \Redist  
                              \<config>  
                                    \<arch>  
                        \DesignTime  
                               \<config>  
                                     \<arch>  
  
```  
  
1.  \\< SDKName\>\\< SDKVersion\>: název a verzi rozšíření sady SDK je odvozený od odpovídající názvy složek v cestě ke kořenu SDK. MSBuild použije tuto identitu pro vyhledání sady SDK na disku, a zobrazí tuto identitu v sadě Visual Studio **vlastnosti** okno a **správce odkazů** dialogové okno.  
  
2.  Složky odkazů: binární soubory, které obsahují rozhraní API. Může jít o soubory metadat Windows (WinMD) nebo sestavení.  
  
3.  Redistribuce složky: soubory, které jsou nutné pro modul runtime nebo ladění a měli získat zabalené jako součást aplikaci uživatele. Všechny binární soubory musí být umístěny pod \redist\\< konfigurace\>\\< architektura\>, a binárními názvy by měla mít následující formát zajistit jedinečnost:  **\<společnosti >.\< produkt >. \<účel >. \<rozšíření >**. Například Microsoft.Cpp.Build.dll. Všechny soubory s názvy, které může dojít ke konfliktu s názvy souborů od ostatních sad SDK (například javascript, css, pri, xaml, png nebo jpg soubory) musí být umístěny pod \redist\\< konfigurace\>\\< architektura\> \\< sdkname\>\ s výjimkou souborů, které jsou přidruženy XAML ovládací prvky. Tyto soubory musí být umístěny pod \redist\\< konfigurace\>\\< architektura\>\\< componentname\>\\.  
  
4.  Složka DesignTime: soubory, které jsou potřeba v pouze vedlejší-run nebo ladění čas a by neměl být zabalené jako součást aplikace uživatele. Může jít o dokumentace XML, knihoven, záhlaví, binární soubory sady nástrojů návrhu, MSBuild artefaktů a tak dále. Všechny sady SDK, který je určený pro spotřeba k nativnímu projektu musí mít *SDKName*props souboru. Na obrázku je ukázka tohoto typu souboru.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
      <PropertyGroup>  
        <ExecutablePath>C:\Temp\ExecutablePath;$(ExecutablePath)</ExecutablePath>  
        <IncludePath>$(FrameworkSDKRoot)\..\v8.1\ExtensionSDKs\cppimagingsdk\1.0\DesignTime\CommonConfiguration\Neutral\include;$(IncludePath)</IncludePath>  
        <AssemblyReferencePath>C:\Temp\AssemblyReferencePath;(AssemblyReferencePath)</AssemblyReferencePath>  
        <LibraryPath>$(FrameworkSDKRoot)\..\v8.1\ExtensionSDKs\cppimagingsdk\1.0\DesignTime\Debug\ARM;$(LibraryPath)</LibraryPath>  
        <SourcePath>C:\Temp\SourcePath\X64;$(SourcePath)</SourcePath>  
        <ExcludePath>C:\Temp\ExcludePath\X64;$(ExcludePath)</ExcludePath>  
        <_PropertySheetDisplayName>DevILSDK, 1.0</_PropertySheetDisplayName>  
      </PropertyGroup>  
    </Project>  
  
    ```  
  
     Referenční dokumentace XML – dokumenty jsou umístěny společně se referenčního souboru. Například referenčním dokumentu XML pro **\References\\< konfigurace\>\\< architektura\>\sample.dll** sestavení **\References\\ < konfigurace\>\\< architektura\>\sample.xml**, a lokalizované verze tohoto dokumentu je **\References\\< konfigurace\>\\< Architektura\>\\< národní prostředí\>\sample.xml**.  
  
5.  Konfigurace složky: tři podsložky: ladění, prodejní verze a CommonConfiguration. Autoři sady SDK můžete umístit své soubory pod CommonConfiguration, pokud stejnou sadu SDK soubory by měly využívat, bez ohledu na konfiguraci cílové sady SDK uživatelem.  
  
6.  Architektura složky: jsou podporovány následující typy architektury: x86, x64, ARM, neutrální. Win32 mapuje x86 a AnyCPU mapuje neutrální.  
  
### <a name="sdkmanifestxml"></a>SDKManifest.xml  
 Tento soubor popisuje, jak Visual Studio by měla využívat sadu SDK. Následuje příklad.  
  
```  
<FileList>  
DisplayName = "My SDK"  
ProductFamilyName = "My SDKs"  
TargetFramework = ".NETCore, version=v4.5.1; .NETFramework, version=v4.5.1"  
MinVSVersion = "14.0"  
MaxPlatformVersion = "8.1"  
AppliesTo = "WindowsAppContainer + WindowsXAML"  
SupportPrefer32Bit = "True"  
SupportedArchitectures = "x86;x64;ARM"  
SupportsMultipleVersions = "Error"  
CopyRedistToSubDirectory = "."  
DependsOn = "SDKB, version=2.0"  
MoreInfo = "http://msdn.microsoft.com/MySDK">  
<File Reference = "MySDK.Sprint.winmd" Implementation = "XNASprintImpl.dll">  
<Registration Type = "Flipper" Implementation = "XNASprintFlipperImpl.dll" />  
<Registration Type = "Flexer" Implementation = "XNASprintFlexerImpl.dll" />  
<ToolboxItems VSCategory = "Toolbox.Default" />  
</File>  
</FileList>  
```  
  
 Následující seznam obsahuje elementy souboru.  
  
1.  DisplayName: hodnota, která se zobrazí v správce odkazů, Průzkumník řešení, prohlížeč objektů a jiných umístění v uživatelském rozhraní pro sadu Visual Studio.  
  
2.  ProductFamilyName: Celkový SDK názvu produktu. Například [!INCLUDE[winjs_long](../debugger/includes/winjs_long_md.md)] SDK je s názvem "Microsoft.WinJS.1.0" a "Microsoft.WinJS.2.0", které patří do stejné rodiny rodiny produktů SDK, "Microsoft.WinJS". Tento atribut umožňuje sadě Visual Studio a nástroje MSBuild, aby toto připojení. Pokud tento atribut neexistuje, je název SDK použít jako název rodiny produktů.  
  
3.  FrameworkIdentity: určuje závislost na jeden nebo více součásti knihovny Windows, které hodnota tohoto atributu je uvést do manifestu aplikace náročné. Tento atribut se vztahuje pouze na knihovny součásti systému Windows.  
  
4.  TargetFramework: Určuje sady SDK, které jsou k dispozici v správce odkazů a sady nástrojů. Toto je seznam oddělený středníkem cílový framework zástupných názvů, například "rozhraní .NET Framework, verze = v2.0; rozhraní .NET Framework, verze = v4.5.1". V případě více verzích rozhraní stejný cíl se používá správce odkazů nejnižší zadaná verze za účelem filtrování. Například pokud "rozhraní .NET Framework, verze = v2.0; rozhraní .NET Framework, verze = v4.5.1" není zadaný, použije Správce odkazů "rozhraní .NET Framework, verze = v2.0". Pokud je zadaný profil konkrétní cílový framework, pouze tento profil slouží Správce odkazů za účelem filtrování. Například když "Silverlight, verze = v4.0, profil = WindowsPhone" není zadaný, správce odkazů filtry na pouze Windows Phone profilu; cílení na full Silverlight 4.0 Framework projektu nezná sady SDK v správce odkazů.  
  
5.  MinVSVersion: minimální verzi sady Visual Studio.  
  
6.  MaxPlatformVerson: Maximální cílová verze platformy slouží k určení verze platformy, na kterých nebude fungovat Extension SDK. Například by měl balíček Microsoft Visual C++ Runtime v11.0 odkazovat jenom projekty Windows 8. Windows 8 projektu MaxPlatformVersion tedy 8.0. To znamená, že správce odkazů filtruje balíček Microsoft Visual C++ Runtime pro Windows 8.1 projektu nástroje MSBuild vyvolá chybu při [!INCLUDE[win81](../debugger/includes/win81_md.md)] projekt odkazuje na ho. Poznámka: Tento element je podporované počínaje [!INCLUDE[vs_dev12](../extensibility/includes/vs_dev12_md.md)].  
  
7.  AppliesTo –: Určuje sady SDK, které jsou k dispozici ve Správci odkaz zadáním příslušné typy projektů Visual Studio. Devět hodnoty jsou rozpoznány: WindowsAppContainer, VisualC, VB, CSharp, WindowsXAML, JavaScript, spravované a nativní. Autor sady SDK můžete použít a ("+"), nebo ("&#124;"), nikoli ("!") operátorů sloužící k určení přesně oboru typy projektů, které se vztahují k sadě SDK.  
  
     WindowsAppContainer identifikuje projekty pro [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikace.  
  
8.  SupportPrefer32Bit: Podporované hodnoty jsou "True" a "False". Výchozí hodnota je "True". Pokud je hodnota nastavena na hodnotu "False", MSBuild vrátí chybu pro [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] projekty (nebo upozornění pro běžných projektů) Pokud projekt, který odkazuje na sadu SDK Prefer32Bit povolena. Další informace o Prefer32Bit najdete v tématu [stránka sestavení, Návrhář projektu (C#)](../ide/reference/build-page-project-designer-csharp.md) nebo [stránka kompilovat, Návrhář projektu (Visual Basic)](../ide/reference/compile-page-project-designer-visual-basic.md).  
  
9. SupportedArchitectures: středníky oddělený seznam architektur, které podporuje sadu SDK. MSBuild zobrazí upozornění, pokud Cílová architektura sady SDK v náročné projektu není podporován. Pokud se tento atribut nezadá, MSBuild nikdy zobrazuje tento typ upozornění.  
  
10. SupportsMultipleVersions: Pokud tento atribut je nastaven na **chyba** nebo **upozornění**, MSBuild označuje, že několik verzí téže rodiny SDK nemůže odkazovat na stejné projektu. Pokud tento atribut neexistuje nebo je nastaven na **povolit**, MSBuild nezobrazí tento typ chyby nebo upozornění.  
  
11. AppX: Určuje cestu k balíčky aplikací pro knihovně součásti systému Windows na disku. Tato hodnota je předán komponentu registrace knihovny součásti systému Windows během místní ladění. Zásady vytváření názvů pro název souboru je  **\<společnosti >.\< Produkt >. \<Architektura >. \<Configuration >. \<Verze > .appx**. Architektura a konfigurace jsou volitelné název a hodnotu atributu, pokud nemohou být použity ke knihovně součásti systému Windows. Tato hodnota se vztahuje pouze na knihovny součásti systému Windows.  
  
12. CopyRedistToSubDirectory: Určuje, odkud mají být zkopírovány souborů ve složce \redist relativní vůči kořenovému adresáři balíčku aplikace (to znamená **umístění balíčku** vybrali v Průvodci vytvořením balíčku aplikace) a kořenový rozložení runtime. Výchozí umístění je kořenový adresář balíčku aplikace a rozložení F5.  
  
13. DependsOn: Seznam SDK identit, které definují sady SDK, na kterých závisí Tato sada SDK. Tento atribut se zobrazí v podokně podrobností Správce odkazů.  
  
14. MoreInfo: adresa URL pro webové stránky, která poskytuje nápovědu a další informace. Tato hodnota se používá v na odkaz Další informace v pravém podokně Správce odkazů.  
  
15. Typ registrace: Určuje WinMD registrace v manifest aplikace a je vyžadovaný pro nativní WinMD, který má protějšek implementace knihovny DLL.  
  
16. Odkaz na soubor: pro tyto odkazy, které obsahují ovládací prvky nebo jsou nativní WinMDs zadat. Informace o tom, jak určit, zda odkaz obsahuje ovládací prvky najdete v tématu [určení umístění položek sady nástrojů](#ToolboxItems) níže.  
  
##  <a name="ToolboxItems"></a> Určení umístění položek sady nástrojů  
 Element ToolBoxItems SDKManifest.xml schématu, které určuje kategorii a umístění položky panelu nástrojů v platformy a rozšíření sady SDK. Následující příklady ukazují, jak zadat jiné umístění. To se vztahuje na odkazy WinMD nebo DLL.  
  
1.  Umístěte ovládací prvky v kategorii výchozí sady nástrojů.  
  
    ```  
    <File Reference = "sample.winmd">  
        <ToolboxItems VSCategory = "Toolbox.Default"/>       
    </File>  
    ```  
  
2.  Umístěte ovládací prvky pod názvem určité kategorie.  
  
    ```  
    <File Reference = "sample.winmd">  
        <ToolboxItems VSCategory= "MyCategoryName"/>  
    </File>  
    ```  
  
3.  Umístěte ovládací prvky pod názvy určité kategorie.  
  
    ```  
    <File Reference = "sample.winmd">  
        <ToolboxItems VSCategory = "Graph">  
        <ToolboxItems/>  
        <ToolboxItems VSCategory = "Data">  
        <ToolboxItems />  
    </File>  
    ```  
  
4.  Umístěte ovládací prvky pod názvy různých kategorií Blend a Visual Studio.  
  
    ```  
    // Blend accepts a slightly different structure for the category name because it allows a path rather than a single category.  
    <File Reference = "sample.winmd">  
        <ToolboxItems VSCategory = "Graph" BlendCategory = "Controls/sample/Graph">   
        <ToolboxItems />  
    </File>  
    ```  
  
5.  Výčet konkrétní ovládacích prvků jinak v programu Blend a Visual Studio.  
  
    ```  
    <File Reference = "sample.winmd">  
        <ToolboxItems VSCategory = "Graph">  
        <ToolboxItems/>  
        <ToolboxItems BlendCategory = "Controls/sample/Graph">  
        <ToolboxItems/>  
    </File>  
    ```  
  
6.  Zobrazení výčtu konkrétní ovládací prvky a umístěte je Visual Studio běžné cestě nebo pouze ve skupině všechny ovládací prvky.  
  
    ```  
    <File Reference = "sample.winmd">  
        <ToolboxItems VSCategory = "Toolbox.Common">  
        <ToolboxItems />  
        <ToolboxItems VSCategory = "Toolbox.All">  
        <ToolboxItems />  
    </File>  
    ```  
  
7.  Výčet konkrétní ovládací prvky a zobrazit pouze konkrétní sady v ChooseItems bez nich se v panelu nástrojů.  
  
    ```  
    <File Reference = "sample.winmd">  
        <ToolboxItems VSCategory = "Toolbox.ChooseItemsOnly">  
        <ToolboxItems />  
    </File>  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Návod: Vytvoření sady SDK, pomocí C++](../extensibility/walkthrough-creating-an-sdk-using-cpp.md)   
 [Návod: Vytvoření sady SDK, pomocí jazyka C# nebo Visual Basic](../extensibility/walkthrough-creating-an-sdk-using-csharp-or-visual-basic.md)   
 [Správa odkazů v projektu](../ide/managing-references-in-a-project.md)