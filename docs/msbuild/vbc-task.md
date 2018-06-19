---
title: Vbc – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Vbc
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Vbc task [MSBuild]
- MSBuild, Vbc task
ms.assetid: 595278b1-2782-4577-b1ba-b4b5ab5625a3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b80612f7d7fa97c8ba31de1a631049f48d1f82be
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31578845"
---
# <a name="vbc-task"></a>Vbc – úloha
Zabalí vbc.exe, který vytváří spustitelné soubory (.exe), dynamické knihovny (DLL) nebo moduly kódu (.netmodule). Další informace o vbc.exe najdete v tématu [Visual Basic – kompilátor příkazového řádku](/dotnet/visual-basic/reference/command-line-compiler/index).  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `Vbc` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`AdditionalLibPaths`|Volitelné `String[]` parametr.<br /><br /> Určuje další složky, ve kterém se má hledat zadaná v atributu odkazy na sestavení.|  
|`AddModules`|Volitelné `String[]` parametr.<br /><br /> Způsobí, že kompilátor zkontrolujte všechny informace ze zadané soubory, které jsou k dispozici do projektu, které jsou aktuálně kompilování typu. Tento parametr odpovídá [/addmodule](/dotnet/visual-basic/reference/command-line-compiler/addmodule) přepínače kompilátoru vbc.exe.|  
|`BaseAddress`|Volitelné `String` parametr.<br /><br /> Určuje základní adresy knihovny DLL. Tento parametr odpovídá [/BaseAddress](/dotnet/visual-basic/reference/command-line-compiler/baseaddress) přepínače kompilátoru vbc.exe.|  
|`CodePage`|Volitelné `Int32` parametr.<br /><br /> Určuje znakovou stránku pro všechny soubory zdrojového kódu v kompilace. Tento parametr odpovídá [/CODEPAGE](/dotnet/visual-basic/reference/command-line-compiler/codepage) přepínače kompilátoru vbc.exe.|  
|`DebugType`|Volitelné `String[]` parametr.<br /><br /> Způsobí, že kompilátor generovat ladicí informace. Tento parametr může mít následující hodnoty:<br /><br /> -   `full`<br />-   `pdbonly`<br /><br /> Výchozí hodnota je `full`, která umožňuje připojení ladicího programu spuštěného programu. Hodnota `pdbonly` umožňuje ladění kódu zdroje, když program se spustil v ladicím programu, ale zobrazí kód jazyka sestavení jenom v případě, že se spuštěným programem je připojen k ladicího programu. Další informace najdete v tématu [/Debug (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/debug).|  
|`DefineConstants`|Volitelné `String[]` parametr.<br /><br /> Definuje podmíněného kompilátoru konstanty. Dvojice symbol/hodnota jsou odděleny středníky a zadávají s následující syntaxí:<br /><br /> *symbol1* `=` *value1* `;` *symbol2* `=` *hodnota2*<br /><br /> Tento parametr odpovídá [/ define](/dotnet/visual-basic/reference/command-line-compiler/define) přepínače kompilátoru vbc.exe.|  
|`DelaySign`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, úloha umístí veřejný klíč v sestavení. Pokud `false`, úloha plně podepisuje sestavení. Výchozí hodnota je `false`. Tento parametr nemá žádný vliv, pokud není použita s `KeyFile` parametr nebo `KeyContainer` parametr. Tento parametr odpovídá [/delaysign](/dotnet/visual-basic/reference/command-line-compiler/delaysign) přepínače kompilátoru vbc.exe.|  
|`DisabledWarnings`|Volitelné `String` parametr.<br /><br /> Potlačí zadaný upozornění. Pouze musíte zadat číselnou část identifikátor upozornění. Několik upozornění jsou odděleny středníky. Tento parametr odpovídá [/nowarn](/dotnet/visual-basic/reference/command-line-compiler/nowarn) přepínače kompilátoru vbc.exe.|  
|`DocumentationFile`|Volitelné `String` parametr.<br /><br /> Zpracuje dokumentační komentáře k zadanému souboru XML. Tento parametr přepíše `GenerateDocumentation` atribut. Další informace najdete v tématu [/doc](/dotnet/visual-basic/reference/command-line-compiler/doc).|  
|`EmitDebugInformation`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, úloha generuje informace o ladění a umístí jej do souboru pdb. Další informace najdete v tématu [/Debug (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/debug).|  
|`ErrorReport`|Volitelné `String` parametr.<br /><br /> Určuje, jak má úloha zprávy o chybách interní kompilátoru. Tento parametr může mít následující hodnoty:<br /><br /> -   `prompt`<br />-   `send`<br />-   `none`<br /><br /> Pokud `prompt` je zadán a dojde k chybě vnitřní kompilátoru, bude uživatel vyzván možností němuž k odesílání dat chyby společnosti Microsoft.<br /><br /> Pokud `send` je zadán a dojde k chybě vnitřní kompilátoru, úloha odešle data chyby společnosti Microsoft.<br /><br /> Výchozí hodnota je `none`, které sestavy chyb v textu pouze výstup.<br /><br /> Tento parametr odpovídá [/errorreport](/dotnet/visual-basic/reference/command-line-compiler/errorreport) přepínače kompilátoru vbc.exe.|  
|`FileAlignment`|Volitelné `Int32` parametr.<br /><br /> Určuje, v bajtech, kde chcete-li zarovnat na části výstupní soubor. Tento parametr může mít následující hodnoty:<br /><br /> -   `512`<br />-   `1024`<br />-   `2048`<br />-   `4096`<br />-   `8192`<br /><br /> Tento parametr odpovídá [/filealign](/dotnet/visual-basic/reference/command-line-compiler/filealign) přepínače kompilátoru vbc.exe.|  
|`GenerateDocumentation`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, generuje dokumentaci informace a umístí jej do souboru XML s názvem spustitelného souboru nebo knihovny, který vytváří úloha. Další informace najdete v tématu [/doc](/dotnet/visual-basic/reference/command-line-compiler/doc).|  
|`Imports`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Obory názvů importuje ze zadané položky kolekce. Tento parametr odpovídá [/importuje](/dotnet/visual-basic/reference/command-line-compiler/imports) přepínače kompilátoru vbc.exe.|  
|`KeyContainer`|Volitelné `String` parametr.<br /><br /> Určuje název kontejneru kryptografických klíčů. Tento parametr corresonds k [/keycontainer](/dotnet/visual-basic/reference/command-line-compiler/keycontainer) přepínače kompilátoru vbc.exe.|  
|`KeyFile`|Volitelné `String` parametr.<br /><br /> Určuje název souboru obsahujícího kryptografický klíč. Další informace najdete v tématu [/keyfile](/dotnet/visual-basic/reference/command-line-compiler/keyfile).|  
|`LangVersion`|Volitelné <xref:System.String?displayProperty=fullName> parametr.<br /><br /> Určuje jazykovou verzi, "9" nebo "10".|  
|`LinkResources`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Vytvoří odkaz na prostředek rozhraní .NET Framework ve výstupním souboru; soubor prostředků není umístěn ve výstupním souboru. Tento parametr odpovídá [/linkresource](/dotnet/visual-basic/reference/command-line-compiler/linkresource) přepínače kompilátoru vbc.exe.|  
|`MainEntryPoint`|Volitelné `String` parametr.<br /><br /> Určuje třídu nebo modul, který obsahuje `Sub Main` postupu. Tento parametr corresonds k [/main](/dotnet/visual-basic/reference/command-line-compiler/main) přepínače kompilátoru vbc.exe.|  
|`ModuleAssemblyName`|Volitelné `String` parametr.<br /><br /> Určuje sestavení, které tento modul je součástí.|  
|`NoConfig`|Volitelné `Boolean` parametr.<br /><br /> Určuje, že kompilátor by neměl používat soubor vbc.rsp. Tento parametr odpovídá [/noconfig](/dotnet/visual-basic/reference/command-line-compiler/noconfig) parametr vbc.exe kompilátoru.|  
|`NoLogo`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, potlačí zobrazení informace kompilátoru. Tento parametr odpovídá [/nologo](/dotnet/visual-basic/reference/command-line-compiler/nologo) přepínače kompilátoru vbc.exe.|  
|`NoStandardLib`|Volitelné `Boolean` parametr.<br /><br /> Způsobí, že kompilátor není tak, aby odkazovaly na standardní knihovny. Tento parametr odpovídá [/nostdlib](/dotnet/visual-basic/reference/command-line-compiler/nostdlib) přepínače kompilátoru vbc.exe.|  
|`NoVBRuntimeReference`|Volitelné `Boolean` parametr.<br /><br /> Pouze interní použití. V případě hodnoty true brání automatické odkaz na souboru Microsoft.VisualBasic.dll...|  
|`NoWarnings`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, potlačí úloh všech upozornění. Další informace najdete v tématu [/nowarn](/dotnet/visual-basic/reference/command-line-compiler/nowarn).|  
|`Optimize`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, umožňuje optimalizace kompilátoru. Tento parametr odpovídá [/ optimize](/dotnet/visual-basic/reference/command-line-compiler/optimize) přepínače kompilátoru vbc.exe.|  
|`OptionCompare`|Volitelné `String` parametr.<br /><br /> Určuje, jak jsou vytvářeny porovnání řetězců. Tento parametr může mít následující hodnoty:<br /><br /> -   `binary`<br />-   `text`<br /><br /> Hodnota `binary` Určuje, že úloha používá porovnání binárního řetězce. Hodnota `text` Určuje, že úloha používá porovnání řetězců textu. Výchozí hodnota tohoto parametru je `binary`. Tento parametr odpovídá [/optioncompare](/dotnet/visual-basic/reference/command-line-compiler/optioncompare) přepínače kompilátoru vbc.exe.|  
|`OptionExplicit`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, je nutná explicitní deklarace proměnné. Tento parametr odpovídá [/optionexplicit](/dotnet/visual-basic/reference/command-line-compiler/optionexplicit) přepínače kompilátoru vbc.exe.|  
|`OptionInfer`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, umožňuje odvození typu proměnné.|  
|`OptionStrict`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, úloha vynucuje přísné typ sémantiku jako omezení typu implicitní převody. Tento parametr odpovídá [/optionstrict](/dotnet/visual-basic/reference/command-line-compiler/optionstrict) přepínače kompilátoru vbc.exe.|  
|`OptionStrictType`|Volitelné `String` parametr.<br /><br /> Určuje, které sémantika striktní typu generovat upozornění. V současné době se podporuje jenom "vlastní". Tento parametr odpovídá [/optionstrict](/dotnet/visual-basic/reference/command-line-compiler/optionstrict) přepínače kompilátoru vbc.exe.|  
|`OutputAssembly`|Volitelné `String` výstupní parametr.<br /><br /> Určuje název výstupního souboru. Tento parametr odpovídá [/out](/dotnet/visual-basic/reference/command-line-compiler/out) přepínače kompilátoru vbc.exe.|  
|`Platform`|Volitelné `String` parametr.<br /><br /> Určuje platformu procesoru, které se zaměřují výstupní soubor. Tento parametr může mít hodnotu `x86`, `x64`, `Itanium`, nebo `anycpu`. Výchozí hodnota je `anycpu`. Tento parametr odpovídá [/Platform](/dotnet/visual-basic/reference/command-line-compiler/platform) přepínače kompilátoru vbc.exe.|  
|`References`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Způsobí, že úloha import informace veřejného typu ze zadaných položek do aktuálního projektu. Tento parametr odpovídá [/reference](/dotnet/visual-basic/reference/command-line-compiler/reference) přepínače kompilátoru vbc.exe.|  
|`RemoveIntegerChecks`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, zakáže Kontrola chyb přetečení celé číslo. Výchozí hodnota je `false`. Tento parametr odpovídá [/removeintchecks](/dotnet/visual-basic/reference/command-line-compiler/removeintchecks) přepínače kompilátoru vbc.exe.|  
|`Resources`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Vloží prostředek rozhraní .NET Framework do výstupního souboru. Tento parametr odpovídá [/Resource](/dotnet/visual-basic/reference/command-line-compiler/resource) přepínače kompilátoru vbc.exe.|  
|`ResponseFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje soubor odpovědí, který obsahuje příkazy pro tuto úlohu. Tento parametr odpovídá [@ (určení souboru odezvy)](/dotnet/visual-basic/reference/command-line-compiler/specify-response-file) – možnost kompilátoru vbc.exe.|  
|`RootNamespace`|Volitelné `String` parametr.<br /><br /> Určuje kořenový obor názvů pro všechny deklarace typu. Tento parametr odpovídá [/RootNamespace](/dotnet/visual-basic/reference/command-line-compiler/rootnamespace) přepínače kompilátoru vbc.exe.|  
|`SdkPath`|Volitelné `String` parametr.<br /><br /> Určuje umístění mscorlib.dll a souboru microsoft.visualbasic.dll. Tento parametr odpovídá [/sdkpath](/dotnet/visual-basic/reference/command-line-compiler/sdkpath) přepínače kompilátoru vbc.exe.|  
|`Sources`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje jeden nebo více [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] zdrojové soubory.|  
|`TargetCompactFramework`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, cíle úloh [!INCLUDE[Compact](../extensibility/includes/compact_md.md)]. Tento přepínač odpovídá [/netcf](/dotnet/visual-basic/reference/command-line-compiler/netcf) přepínače kompilátoru vbc.exe.|  
|`TargetType`|Volitelné `String` parametr.<br /><br /> Určuje formát souboru výstupního souboru. Tento parametr může mít hodnotu `library`, vytváří knihovny kódu `exe`, která vytvoří konzolovou aplikaci, `module`, která vytvoří modul, nebo `winexe`, vytváří programu systému Windows. Výchozí hodnota je `library`. Tento parametr odpovídá [/target](/dotnet/visual-basic/reference/command-line-compiler/target) přepínače kompilátoru vbc.exe.|  
|`Timeout`|Volitelné `Int32` parametr.<br /><br /> Určuje množství času, v milisekundách, po kterých je spustitelný soubor úlohy ukončen. Výchozí hodnota je `Int.MaxValue`, což označuje, že bez doby vypršení časového limitu.|  
|`ToolPath`|Volitelné `String` parametr.<br /><br /> Určuje umístění, ze kterých úloha načte základní spustitelný soubor (vbc.exe). Pokud není tento parametr zadán, použije úloha cesta instalace sady SDK odpovídající verzi rozhraní, které běží [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)].|  
|`TreatWarningsAsErrors`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, všech upozornění jsou považovány za chyby. Další informace najdete v tématu [/warnaserror (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/warnaserror).|  
|`UseHostCompilerIfAvailable`|Volitelné `Boolean` parametr.<br /><br /> Dá pokyn úlohy použít objekt kompilátor, pokud je k dispozici. Používání pouze systémem [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|  
|`Utf8Output`|Volitelné `Boolean` parametr.<br /><br /> Zaznamená výstup kompilátoru pomocí kódování UTF-8. Tento parametr odpovídá [/utf8output](/dotnet/visual-basic/reference/command-line-compiler/utf8output) přepínače kompilátoru vbc.exe.|  
|`Verbosity`|Volitelné `String` parametr.<br /><br /> Určuje podrobností výstupu kompilátoru. Může být podrobností `Quiet`, `Normal` (výchozí), nebo `Verbose`.|  
|`WarningsAsErrors`|Volitelné `String` parametr.<br /><br /> Určuje seznam upozornění na považovat za chyby. Další informace najdete v tématu [/warnaserror (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/warnaserror).<br /><br /> Tento parametr přepíše `TreatWarningsAsErrors` parametr.|  
|`WarningsNotAsErrors`|Volitelné `String` parametr.<br /><br /> Určuje seznam upozornění, která nejsou považovány za chyby. Další informace najdete v tématu [/warnaserror (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/warnaserror).<br /><br /> Tento parametr je užitečné, pouze pokud `TreatWarningsAsErrors` parametr je nastaven na `true`.|  
|`Win32Icon`|Volitelné `String` parametr.<br /><br /> Vloží soubor .ico, který v sestavení, která umožňuje výstupní soubor požadovaný vzhled v Průzkumníku souborů. Tento parametr odpovídá [/win32icon](/dotnet/visual-basic/reference/command-line-compiler/win32icon) přepínače kompilátoru vbc.exe.|  
|`Win32Resources`|Volitelné `String` parametr.<br /><br /> Vloží soubor prostředků (.res) Win32 ve výstupním souboru. Tento parametr odpovídá [/win32resource](/dotnet/visual-basic/reference/command-line-compiler/win32resource) přepínače kompilátoru vbc.exe.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.ToolTaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.ToolTask> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [tooltaskextension – základní třída](../msbuild/tooltaskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad kompiluje [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projektu.  
  
```xml  
<VBC  
   Sources="@(sources)"  
   Resources="strings.resources"  
   Optimize="true"  
   OutputAssembly="out.exe"/>  
```  
  
## <a name="see-also"></a>Viz také  
 [Visual Basic – kompilátor příkazového řádku](/dotnet/visual-basic/reference/command-line-compiler/index)   
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)