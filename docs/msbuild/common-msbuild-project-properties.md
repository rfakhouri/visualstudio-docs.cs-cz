---
title: "Běžné vlastnosti projektu nástroje MSBuild | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- msbuild, common properties
- msbuild, project file properties
- ExcludeDeploymentUrl property
- project file properties (MSBuild)
ms.assetid: 9857505d-ae15-42f1-936d-6cd7fb9dd276
caps.latest.revision: "36"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b78c2c1276f04a53a4f7a01e70a7d98efdba0514
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="common-msbuild-project-properties"></a>Obecné vlastnosti projektu nástroje MSBuild
V následující tabulce jsou uvedeny často používá vlastnosti, které jsou definovány v souborech projektu sady Visual Studio nebo součástí .TARGETS – soubory, které poskytuje nástroje MSBuild.  
  
 Soubory projektu v sadě Visual Studio (.csproj, .vbproj, vcxproj a dalších) obsahovat kód MSBuild XML, který běží při sestavování projektu s použitím prostředí IDE. Projekty obvykle importovat jeden nebo více souborů .targets definovat jejich procesu sestavení. Další informace najdete v tématu [. Cílem soubory](../msbuild/msbuild-dot-targets-files.md).  
  
## <a name="list-of-common-properties-and-parameters"></a>Seznam běžných vlastností a parametrů  
  
|Vlastnost nebo název parametru|Popis|  
|--------------------------------|-----------------|  
|AdditionalLibPaths|Určuje další složky, ve kterých by měl vypadat kompilátory pro referenční sestavení.|  
|AddModules|Způsobí, že kompilátor, aby byl typ všechny informace ze zadaného soubory k dispozici jsou kompilace projektu. Tato vlastnost je ekvivalentní `/addModules` přepínače kompilátoru.|  
|ALToolPath|Cesta, kde můžete najít AL.exe. Tato vlastnost potlačuje aktuální verzi AL.exe povolení použití jiné verze.|  
|ApplicationIcon|Ikona soubor .ico, který mají být předána do kompilátoru pro vložení jako Win32 ikona. Vlastnost je ekvivalentní `/win32icon` přepínače kompilátoru.|  
|ApplicationManifest|Určuje cestu k souboru, který se používá ke generování manifestu informací o externí řízení uživatelských účtů (UAC). Platí pouze pro Visual Studio projektech zacílených na [!INCLUDE[windowsver](../deployment/includes/windowsver_md.md)].<br /><br /> Ve většině případů je vložený manifest. Ale pokud používáte COM bez registrace nebo [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení a potom manifest může být externí soubor, která je nainstalována spolu s sestavení vaší aplikace. Další informace naleznete ve vlastnosti NoWin32Manifest v tomto tématu.|  
|AssemblyOriginatorKeyFile|Určuje soubor, který se používá k podepsání sestavení (.snk nebo .pfx) a která je předána [resolvekeysource – úloha](../msbuild/resolvekeysource-task.md) ke generování skutečný klíč, který se používá k podepsání sestavení.|  
|AssemblySearchPaths|Seznam umístění pro vyhledávání během sestavení referenční sestavení řešení. Pořadí zobrazení cesty v tomto seznamu je důležité, protože cesty uvedené výše má přednost před pozdější položky.|  
|AssemblyName|Název sestavení závěrečný výstup po sestavení projektu.|  
|BaseAddress|Určuje základní adresu sestavení hlavní výstupu. Tato vlastnost je ekvivalentní `/baseaddress` přepínače kompilátoru.|  
|BaseOutputPath|Určuje základní cesta pro výstupní soubor. Pokud je nastavena, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] použije `OutputPath = $(BaseOutputPath)\$(Configuration)\`. Příklad syntaxe:`<BaseOutputPath>c:\xyz\bin\</BaseOutputPath>`|  
|BaseIntermediateOutputPath|Složku nejvyšší úrovně, kde jsou vytvořeny všechny specifické konfigurace zprostředkující výstupní složky. Výchozí hodnota je `obj\`. Následující kód je příklad:`<BaseIntermediateOutputPath>c:\xyz\obj\</BaseIntermediateOutputPath>`|  
|BuildInParallel|Logická hodnota, která určuje, zda jsou odkazy na projekt vytvořené nebo čištění paralelní Pokud více procesorů [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] se používá. Výchozí hodnota je `true`, což znamená, že projekty budou vytvořeny v paralelní Pokud systému obsahuje více jader nebo procesorů.|  
|BuildProjectReferences|Logická hodnota, která označuje, zda jsou vytvořené odkazy na projekt [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]. Nastavit `false` Pokud vytváříte projektu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE), `true` Pokud jinak.|  
|CleanFile|Název souboru, který se použije jako "vyčištění mezipaměti". Vyčištění mezipaměti je seznam generovaného souborů k odstranění během operace čištění. Soubor je umístěn zprostředkující výstupní cesta procesem sestavení.<br /><br /> Tato vlastnost určuje pouze názvy souborů, které nemají informace o cestě.|  
|Znakové stránky|Určuje znakovou stránku pro všechny soubory zdrojového kódu v kompilace. Tato vlastnost je ekvivalentní `/codepage` přepínače kompilátoru.|  
|CompilerResponseFile|Soubor volitelné odpověď, který se dá předat do kompilátoru úlohy.|  
|Konfigurace|Konfigurace, který vytváříte, "Ladění" nebo "Verze".|  
|CscToolPath|Cesta csc.exe, [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] kompilátoru.|  
|CustomBeforeMicrosoftCommonTargets|Název souboru projektu nebo cíle soubor, který má být importován automaticky před importem běžné cíle.|  
|DebugSymbols|Logická hodnota, která určuje, zda symboly generované sestavení.<br /><br /> Nastavení **/p:DebugSymbols = false** na příkazovém řádku znemožňuje generování souborů symbol program databáze (.pdb).|  
|DefineConstants|Definuje podmíněného kompilátoru konstanty. Dvojice symbol/hodnota jsou odděleny středníky a zadávají pomocí následující syntaxe:<br /><br /> *symbol1 = value1; symbol2 = value2*<br /><br /> Vlastnost je ekvivalentní `/define` přepínače kompilátoru.|  
|DefineDebug|Logická hodnota, která určuje, zda chcete konstanta ladění definované.|  
|DefineTrace|Logická hodnota, která určuje, zda chcete konstanta trasování definované.|  
|DebugType|Definuje úroveň ladicí informace, které mají být vygenerovány. Platné hodnoty jsou "úplný," "pdbonly" a "none."|  
|DelaySign|Logická hodnota, která označuje, zda se má zpoždění podepsání sestavení spíše než úplné přihlášení.|  
|Deterministické|Logická hodnota, která určuje, zda by měl kompilátor vytvořit identické sestavení pro identické vstupy. Tento parametr odpovídá `/deterministic` přepnout z `vbc.exe` a `csc.exe` kompilátory.|
|DisabledWarnings|Potlačí zadaný upozornění. Musí být zadán pouze číselnou část identifikátor upozornění. Několik upozornění jsou odděleny středníky. Tento parametr odpovídá `/nowarn` přepínače kompilátoru vbc.exe.|  
|DisableFastUpToDateCheck|Logická hodnota, která se vztahuje na [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] pouze. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Sestavení manager používá procesu označovaného jako FastUpToDateCheck k určení, zda je třeba znovu vytvořit projekt, být aktuální. Tento proces je rychlejší než při použití [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] to bylo možné určit. Nastavení vlastnosti DisableFastUpToDateCheck na `true` umožňuje vynechat [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] sestavení manager a vynutit používání [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] k určení, zda je aktuální projekt.|  
|DocumentationFile|Název souboru, který se vygeneruje jako souborů dokumentace XML. Tento název obsahuje pouze název souboru a nemá žádné informace o cestě.|  
|ErrorReport|Určuje, jak by měla úlohu kompilátoru zprávy o chybách interní kompilátoru. Platné hodnoty jsou "řádek", "Odeslat" nebo "none." Tato vlastnost je ekvivalentní `/errorreport` přepínače kompilátoru.|  
|Excludedeploymenturl –|[Generatedeploymentmanifest – úloha](../msbuild/generatedeploymentmanifest-task.md) přidá deploymentProvider – značka manifestu nasazení, pokud projekt soubor obsahuje následující prvky:<br /><br /> -UpdateUrl<br />-InstallUrl<br />-PublishUrl<br /><br /> Pomocí excludedeploymenturl –, ale můžete zabránit deploymentProvider – značka se přidává do manifestu nasazení, i když nejsou zadány žádné z výše uvedených adres URL. K tomu, přidejte do souboru projektu následující vlastnost:<br /><br /> `<ExcludeDeploymentUrl>true</ExcludeDeploymentUrl>`**Poznámka:** excludedeploymenturl – není vystavený v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE a lze nastavit pouze tak, že ručně upravíte soubor projektu. Nastavení této vlastnosti nemá vliv na publikování v rámci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]; to znamená, deploymentProvider – značka stále přidá adresa URL zadaná PublishUrl.|  
|FileAlignment|Určuje, v bajtech, kde chcete-li zarovnat na části výstupní soubor. Platné hodnoty jsou 512, 1024, 2048, 4096, 8192. Tato vlastnost je ekvivalentní `/filealignment` přepínače kompilátoru.|  
|FrameworkPathOverride|Určuje umístění mscorlib.dll a souboru microsoft.visualbasic.dll. Tento parametr je ekvivalentní `/sdkpath` přepínače kompilátoru vbc.exe.|  
|GenerateDocumentation|(Visual Basic .NET pouze) Parametr typu boolean, která určuje, zda dokumentace je generován sestavení. Pokud `true`, sestavení generuje dokumentaci informace a vloží ho do souboru .xml společně s název spustitelného souboru nebo knihovny, která sestavení úloha vytvořena.|
|IntermediateOutputPath|Úplné zprostředkující výstupní cesta odvozené z `BaseIntermediateOutputPath`, pokud není zadána žádná cesta. Například \obj\debug\\. Pokud je tato vlastnost přepsána, potom nastavení `BaseIntermediateOutputPath` nemá žádný vliv.|  
|Kontejner_klíčů|Název kontejneru klíčů silného názvu.|  
|KeyOriginatorFile|Název souboru klíče silného názvu.|  
|NoWin32Manifest|Určuje, jestli kompilátor generuje manifest Win32 výchozí do výstupního sestavení. Výchozí hodnota `false` znamená, že je vydána manifest Win32 výchozí pro všechny aplikace. Tato vlastnost je ekvivalentní `/nowin32manifest` použitím přepínače vbc.exe.|  
|ModuleAssemblyName|Název sestavení, které má být součástí kompilovaného modulu. Vlastnost je ekvivalentní `/moduleassemblyname` přepínače kompilátoru.|  
|NoLogo|Logická hodnota, která určuje, zda chcete, aby logo kompilátoru vypnout. Tato vlastnost je ekvivalentní `/nologo` přepínače kompilátoru.|  
|NoStdLib|Logická hodnota, která označuje, zda nedošlo odkazující na standardní knihovnu (mscorlib.dll). Výchozí hodnota je `false`.|  
|NoVBRuntimeReference|Logická hodnota, která určuje, zda [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] runtime (souboru Microsoft.VisualBasic.dll) by měly být zahrnuty jako odkaz v projektu.|  
|NoWin32Manifest|Logická hodnota, která označuje, zda budou vloženy manifestu informace o řízení uživatelských účtů (UAC) v aplikaci je spustitelný soubor. Platí pouze pro Visual Studio projektech zacílených na [!INCLUDE[windowsver](../deployment/includes/windowsver_md.md)]. V projektech, které jsou nasazeny pomocí [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] a COM bez registrace, tento element je ignorována. `False`(výchozí hodnota) určuje, že spustitelný soubor aplikace vložený manifestu informace o řízení uživatelských účtů (UAC). `True`Určuje, že nebude vloženo informace manifestu nástroje Řízení uživatelských účtů.<br /><br /> Tato vlastnost se vztahuje pouze na [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projekty cílení na [!INCLUDE[windowsver](../deployment/includes/windowsver_md.md)]. V projektech, které jsou nasazeny pomocí [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] a COM bez registrace, tato vlastnost je ignorována.<br /><br /> Měli byste přidat NoWin32Manifest pouze v případě, že nechcete, aby [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] pro vložení manifestu všechny informace v aplikaci je spustitelný soubor; tento proces se nazývá *virtualizace*. Chcete-li používat virtualizaci, nastavte `<ApplicationManifest>` ve spojení s `<NoWin32Manifest>` následujícím způsobem:<br /><br /> -Pro [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projekty, odeberte `<ApplicationManifest>` uzlu. (V [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projekty, `<NoWin32Manifest>` se ignoruje při `<ApplicationManifest>` existuje uzlu.)<br />-Pro [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] projekty, nastavte `<ApplicationManifest>` k `False` a `<NoWin32Manifest>` k `True`. (V [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] projekty, `<ApplicationManifest>` přepsání `<NoWin32Manifest>`.)|  
|Optimalizace|Logická hodnota, pokud je nastavena na hodnotu `true`, umožňuje optimalizace kompilátoru. Tato vlastnost je ekvivalentní `/optimize` přepínače kompilátoru.|  
|OptionCompare|Určuje, jak jsou vytvářeny porovnání řetězců. Platné hodnoty jsou "binární" nebo "text". Tato vlastnost je ekvivalentní `/optioncompare` použitím přepínače vbc.exe.|  
|OptionExplicit|Logická hodnota, pokud je nastavena na hodnotu `true`, vyžaduje explicitní deklarace proměnné ve zdrojovém kódu. Tato vlastnost je ekvivalentní `/optionexplicit` přepínače kompilátoru.|  
|OptionInfer|Logická hodnota, pokud je nastavena na hodnotu `true`, umožňuje odvození proměnné typu. Tato vlastnost je ekvivalentní `/optioninfer` přepínače kompilátoru.|  
|OptionStrict|Logická hodnota, pokud je nastavena na hodnotu `true`, způsobí, že úlohu sestavení vynutit sémantiku striktní typ omezení typu implicitní převody. Tato vlastnost je ekvivalentní `/optionstrict` přepínače kompilátoru vbc.exe.|  
|OutputPath|Určuje cestu k výstupnímu adresáři, relativně k adresáři projektu, například "bin\Debug".|  
|Element OutputType|Určuje formát souboru výstupního souboru. Tento parametr může mít jednu z následujících hodnot:<br /><br /> -Knihovny. Vytvoří knihovnu kódu. (Výchozí hodnota).<br />-Exe. Vytvoří konzolovou aplikaci.<br />-Module. Vytvoří modul.<br />-Winexe. Vytvoří aplikace systému Windows.<br /><br /> Tato vlastnost je ekvivalentní `/target` přepínače kompilátoru vbc.exe.|  
|OverwriteReadOnlyFiles|Logická hodnota, která určuje, zda chcete povolit sestavení přepsat soubory jen pro čtení nebo aktivovat k chybě.|  
|PdbFile|Název souboru na soubor .pdb, která jsou generování. Tato vlastnost je ekvivalentní `/pdb` přepínače kompilátoru csc.exe.|  
|Platforma|Operační systém, které vytváříte pro. Platné hodnoty jsou "Libovolný procesor", "x 86" a "x64".|  
|ProduceReferenceAssembly|Logická hodnota, pokud je nastavena na hodnotu `true` umožňuje produkce [referenční sestavení](https://github.com/dotnet/roslyn/blob/master/docs/features/refout.md) pro aktuální sestavení. `Deterministic`musí být `true` při použití této funkce. Tato vlastnost odpovídá `/refout` přepnout z `vbc.exe` a `csc.exe` kompilátory.|
|RemoveIntegerChecks|Logická hodnota, která určuje, zda chcete zakázat kontroly chyby přetečení celé číslo. Výchozí hodnota je `false`. Tato vlastnost je ekvivalentní `/removeintchecks` přepínače kompilátoru vbc.exe.|  
|SGenUseProxyTypes|Logická hodnota, která určuje, zda proxy typy by měla být generována SGen.exe.<br /><br /> SGen – cíl používá tuto vlastnost nastavit příznak UseProxyTypes. Tato vlastnost bude jako výchozí nastavena na hodnotu true a neexistuje žádné uživatelské rozhraní pro toto nastavení změnit. Pokud chcete vygenerovat sestavení serializace pro typy – webová služba, přidejte tuto vlastnost k souboru projektu a před importem Microsoft.Common.Targets nebo C#/VB.targets ho nastavit na hodnotu false.|  
|SGenToolPath|Cesta volitelné nástroj, která určuje, kde můžete získat SGen.exe, pokud je aktuální verze SGen.exe přepsat.|  
|StartupObject|Určuje třídu nebo modul, který obsahuje metodu Main nebo Sub Main postupu. Tato vlastnost je ekvivalentní `/main` přepínače kompilátoru.|  
|ProcessorArchitecture|Architektura procesoru, která se používá, když jsou vyřešeny odkazy na sestavení. Platné hodnoty jsou "msil", "x86," "amd64," nebo "ia64."|  
|RootNamespace|Kořenového oboru názvů pro použití při název vložený prostředek. Tento obor názvů je součástí názvu manifestu vložený prostředek.|  
|Satellite_AlgorithmId|Číslo ID algoritmu hash AL.exe použít při vytváření satelitních sestavení.|  
|Satellite_BaseAddress|Základní adresa pro použití při satelitní specifické pro jazykovou verzi sestavení jsou vytvořené pomocí `CreateSatelliteAssemblies` cíl.|  
|Satellite_CompanyName|Název společnosti, který má být předán AL.exe během vytváření satelitních sestavení.|  
|Satellite_Configuration|Název konfigurace k předání do AL.exe během vytváření satelitních sestavení.|  
|Satellite_Description|Text elementu description k předání do AL.exe během vytváření satelitních sestavení.|  
|Satellite_EvidenceFile|Vloží zadaný soubor v satelitní sestavení, která má název prostředku "Security.Evidence."|  
|Satellite_FileVersion|Určuje řetězec pro pole verze souboru v satelitní sestavení.|  
|Satellite_Flags|Určuje hodnotu v poli příznaky v satelitní sestavení.|  
|Satellite_GenerateFullPaths|Způsobí, že úlohu sestavení použít absolutní cesty pro všechny soubory v chybovou zprávu.|  
|Satellite_LinkResource|Odkazy na soubory zadané prostředků do satelitní sestavení.|  
|Satellite_MainEntryPoint|Určuje plně kvalifikovaný název (class.method) metody, která použít jako vstupní bod, pokud modul je převést na spustitelný soubor během vytváření satelitních sestavení.|  
|Satellite_ProductName|Určuje řetězec pro pole produktu v satelitní sestavení.|  
|Satellite_ProductVersion|Určuje řetězec pro pole ProductVersion v satelitní sestavení.|  
|Satellite_TargetType|Určuje formát souboru výstupního souboru satelitní sestavení jako "library", "exe" nebo "win." Výchozí hodnota je "knihovna."|  
|Satellite_Title|Určuje řetězec pro pole název v satelitní sestavení.|  
|Satellite_Trademark|Určuje řetězec pro pole ochranná známka v satelitní sestavení.|  
|Satellite_Version|Určuje informace o verzi pro satelitní sestavení.|  
|Satellite_Win32Icon|Vloží soubor .ico, který ikony v satelitní sestavení.|  
|Satellite_Win32Resource|Vloží prostředek systému Win32 (.res soubor) do satelitní sestavení.|  
|SubsystemVersion|Určuje minimální verze subsystému, můžete použít vygenerovaný spustitelný soubor. Tato vlastnost je ekvivalentní `/subsystemversion` přepínače kompilátoru. Informace o výchozí hodnota této vlastnosti najdete v tématu [/subsystemversion (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/subsystemversion) nebo [/subsystemversion (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/subsystemversion-compiler-option).|  
|TargetCompactFramework|Verze rozhraní .NET Compact Framework potřebné ke spuštění aplikace, které vytváříte. Určení to umožňuje odkazovat na určité framework sestavení, které nelze odkazovat jinak.|  
|targetFrameworkVersion|Verze [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] které jsou potřeba ke spuštění aplikace, které vytváříte. Určení to umožňuje odkazovat na určité framework sestavení, které nelze odkazovat jinak.|  
|TreatWarningsAsErrors|Parametr typu boolean, pokud `true`, způsobí, že všechny upozornění jsou považovány za chyby. Tento parametr je ekvivalentní `/nowarn` přepínače kompilátoru.|  
|UseHostCompilerIfAvailable|Parametr typu boolean, pokud `true`, způsobí, že úlohu sestavení použít objekt kompilátor, pokud je k dispozici. Tento parametr je použit pouze systémem [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|  
|Utf8Output|Parametr typu boolean, pokud `true`, protokoly výstupu kompilátoru pomocí kódování UTF-8. Tento parametr je ekvivalentní `/utf8Output` přepínače kompilátoru.|  
|VbcToolPath|Volitelná cesta určující jiné umístění pro vbc.exe, pokud je aktuální verze vbc.exe přepsat.|  
|VbcVerbosity|Určuje podrobností [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] výstupu kompilátoru. Platné hodnoty jsou "Tichý", "Normální" (výchozí hodnota), nebo "Verbose."|  
|VisualStudioVersion|Určuje verzi sady Visual Studio, pod kterým tento projekt považovat, aby byl spuštěn. Pokud není tato vlastnost určena, MSBuild ji nastaví na přiměřenou výchozí hodnotu.<br /><br /> Tato vlastnost se používá v několika typů projektu určit sadu cílů, které se používají pro sestavení. Pokud `ToolsVersion` je nastaven na 4.0 nebo vyšší pro projekt, `VisualStudioVersion` slouží k určení, které dílčí nástrojů používat. Další informace najdete v tématu [sada nástrojů (atribut ToolsVersion)](../msbuild/msbuild-toolset-toolsversion.md).|  
|WarningsAsErrors|Určuje seznam upozornění na považovat za chyby. Tento parametr je ekvivalentní `/warnaserror` přepínače kompilátoru.|  
|WarningsNotAsErrors|Určuje seznam upozornění, která nejsou považovány za chyby. Tento parametr je ekvivalentní `/warnaserror` přepínače kompilátoru.|  
|Win32Manifest|Název souboru manifestu, který má být vložen v posledním sestavení. Tento parametr je ekvivalentní `/win32Manifest` přepínače kompilátoru.|  
|Win32Resource|Název souboru Win32 prostředek má být vložen v posledním sestavení. Tento parametr je ekvivalentní `/win32resource` přepínače kompilátoru.|  
  
## <a name="see-also"></a>Viz také  
 [Společné položky projektu nástroje MSBuild](../msbuild/common-msbuild-project-items.md)