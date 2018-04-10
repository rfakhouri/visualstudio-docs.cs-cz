---
title: CSC – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: msbuild
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Csc
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Csc task [MSBuild]
- MSBuild, Csc task
ms.assetid: d8c19b36-f5ca-484b-afa6-8ff3b90e103a
caps.latest.revision: 26
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: a74f8c43d35104957b62fb3da93d2acbf6a9a303
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/10/2018
---
# <a name="csc-task"></a>Csc – úloha
Zabalí CSC.exe a vytvoří spustitelné soubory (soubory .exe), dynamické knihovny (soubory .dll) nebo moduly kódu (.netmodule soubory). Další informace o CSC.exe najdete v tématu [možnosti kompilátoru C#](/dotnet/csharp/language-reference/compiler-options/index).  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `Csc` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`AdditionalLibPaths`|Volitelné `String[]` parametr.<br /><br /> Určuje další adresáře pro vyhledávání pro odkazy. Další informace najdete v tématu [/lib (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/lib-compiler-option).|  
|`AddModules`|Volitelné `String` parametr.<br /><br /> Určuje jeden nebo více modulů jako součást sestavení. Další informace najdete v tématu [/addmodule (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/addmodule-compiler-option).|  
|`AllowUnsafeBlocks`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, kompilovaný kód, který používá [unsafe](/dotnet/csharp/language-reference/keywords/unsafe) – klíčové slovo. Další informace najdete v tématu [/ unsafe (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/unsafe-compiler-option).|  
|`ApplicationConfiguration`|Volitelné `String` parametr.<br /><br /> Určuje konfigurační soubor aplikace obsahující nastavení vazby sestavení.|  
|`BaseAddress`|Volitelné `String` parametr.<br /><br /> Určuje upřednostňovaná základní adresa, na které se mají načíst knihovnu DLL. Výchozí základní adresy knihovny DLL se nastavuje pomocí [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] modul common language runtime. Další informace najdete v tématu [/BaseAddress (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/baseaddress-compiler-option).|  
|`CheckForOverflowUnderflow`|Volitelné `Boolean` parametr.<br /><br /> Určuje, zda celé číslo aritmetické, která přesahuje hranice typu dat, způsobí výjimku za běhu. Další informace najdete v tématu [/ checked (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/checked-compiler-option).|  
|`CodePage`|Volitelné `Int32` parametr.<br /><br /> Určuje znakovou stránku pro všechny soubory zdrojového kódu v kompilace. Další informace najdete v tématu [/codepage (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/codepage-compiler-option).|  
|`DebugType`|Volitelné `String` parametr.<br /><br /> Určuje typ ladění. `DebugType` může být `full` nebo `pdbonly`. Výchozí hodnota je `full`, což umožňuje ladicí program připojí se k spuštěným programem. Určení `pdbonly` umožňuje zdroje ladění kódu, když program se spustil v ladicím programu, ale pouze zobrazí assembleru, když se spuštěným programem je připojen k ladicího programu.<br /><br /> Tento parametr přepíše `EmitDebugInformation` parametr.<br /><br /> Další informace najdete v tématu [/Debug (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/debug-compiler-option).|  
|`DefineConstants`|Volitelné `String` parametr.<br /><br /> Definuje preprocesoru symboly. Další informace najdete v tématu [/ define (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/define-compiler-option).|  
|`DelaySign`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, určuje, že má plně podepsané sestavení. Pokud `false`, určuje, že chcete pouze umístit veřejný klíč v sestavení.<br /><br /> Tento parametr nemá žádný vliv, pokud není použita s buď `KeyFile` nebo `KeyContainer` parametr.<br /><br /> Další informace najdete v tématu [/delaysign (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/delaysign-compiler-option).|  
|`DisabledWarnings`|Volitelné `String` parametr.<br /><br /> Určuje seznam upozornění se zakáže. Další informace najdete v tématu [/nowarn (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/nowarn-compiler-option).|  
|`DocumentationFile`|Volitelné `String` parametr.<br /><br /> Zpracuje dokumentační komentáře do souboru XML. Další informace najdete v tématu [/DOC (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/doc-compiler-option).|  
|`EmitDebugInformation`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, úloha generuje informace o ladění a umístí jej do souboru databáze (.pdb) programu. Pokud `false`, úloha vysílá žádné informace o ladění. Výchozí hodnota je `false`. Další informace najdete v tématu [/Debug (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/debug-compiler-option).|  
|`ErrorReport`|Volitelné `String` parametr.<br /><br /> Nabízí pohodlný způsob, jak nahlásit společnosti Microsoft C# vnitřní chybě. Tento parametr může mít hodnotu `prompt`, `send`, nebo `none`. Pokud je nastaven na `prompt`, vám zobrazí výzva, když dojde k chybě vnitřní kompilátoru. Na řádku umožňuje elektronicky odesílat sestavy chyb společnosti Microsoft. Pokud je nastaven na `send`, je automaticky odeslán sestavy chyb. Pokud je nastaven na `none`, pouze v textového výstupu kompilátoru hlásí chybu. Výchozí hodnota je `none`. Další informace najdete v tématu [/errorreport (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/errorreport-compiler-option).|  
|`FileAlignment`|Volitelné `Int32` parametr.<br /><br /> Určuje velikost oddílů ve výstupním souboru. Další informace najdete v tématu [/filealign (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/filealign-compiler-option).|  
|`GenerateFullPaths`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, určuje absolutní cestu k souboru ve výstupu kompilátoru. Pokud `false`, určuje název souboru. Výchozí hodnota je `false`. Další informace najdete v tématu [/fullpaths (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/fullpaths-compiler-option).|  
|`KeyContainer`|Volitelné `String` parametr.<br /><br /> Určuje název kontejneru kryptografických klíčů. Další informace najdete v tématu [/keycontainer (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/keycontainer-compiler-option).|  
|`KeyFile`|Volitelné `String` parametr.<br /><br /> Určuje název souboru obsahujícího kryptografický klíč. Další informace najdete v tématu [/keyfile (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/keyfile-compiler-option).|  
|`LangVersion`|Volitelné `String` parametr.<br /><br /> Určuje verzi jazyka. Další informace najdete v tématu [/langversion (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/langversion-compiler-option).|  
|`LinkResources`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Vytvoří odkaz [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] prostředků ve výstupním souboru; souboru prostředků není umístěn ve výstupním souboru.<br /><br /> Položky předaný do tento parametr může mít volitelná metadata položky s názvem `LogicalName` a `Access`. `LogicalName` odpovídá `identifier` parametr `/linkresource` přepínače, a `Access` odpovídá `accessibility-modifier` parametr. Další informace najdete v tématu [/linkresource (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/linkresource-compiler-option).|  
|`MainEntryPoint`|Volitelné `String` parametr.<br /><br /> Určuje umístění `Main` metoda. Další informace najdete v tématu [/Main (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/main-compiler-option).|  
|`ModuleAssemblyName`|Volitelné `String` parametr.<br /><br /> Určuje název sestavení, které tento modul bude součástí.|  
|`NoConfig`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, určuje kompilátor není kompilovat bez souboru csc.rsp. Další informace najdete v tématu [/noconfig (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/noconfig-compiler-option).|  
|`NoLogo`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, potlačí zobrazení informace kompilátoru. Další informace najdete v tématu [/nologo (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/nologo-compiler-option).|  
|`NoStandardLib`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, zabraňuje importu mscorlib.dll, která definuje obor názvů, celý systém. Tento parametr použijte, pokud chcete definovat nebo vytvořit vlastní System – obor názvů a objekty. Další informace najdete v tématu [/nostdlib (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/nostdlib-compiler-option).|  
|`NoWin32Manifest`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, neobsahují v manifestu Win32 výchozí.|  
|`Optimize`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, umožňuje optimalizace. Pokud `false`, zakáže optimalizace. Další informace najdete v tématu [/ optimize (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/optimize-compiler-option).|  
|`OutputAssembly`|Volitelné `String` výstupní parametr.<br /><br /> Určuje název souboru výstupního souboru. Další informace najdete v tématu [/out (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/out-compiler-option).|  
|`OutputRefAssembly`|Volitelné `String` parametr.<br /><br /> Určuje název výstupního souboru, odkaz na sestavení. Další informace najdete v tématu [/refout (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/refout-compiler-option).|  
|`PdbFile`|Volitelné `String` parametr.<br /><br /> Určuje název souboru ladicích informací. Výchozí název je název výstupního souboru s příponou PDB.|  
|`Platform`|Volitelné `String` parametr.<br /><br /> Určuje platformu procesoru, které se zaměřují výstupní soubor. Tento parametr může mít hodnotu `x86`, `x64`, nebo `anycpu`. Výchozí hodnota je `anycpu`. Další informace najdete v tématu [/Platform (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/platform-compiler-option).|  
|`References`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Způsobí, že úloha import informace veřejného typu ze zadaných položek do aktuálního projektu. Další informace najdete v tématu [/Reference (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/reference-compiler-option).<br /><br /> Můžete zadat [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] alias v odkazu [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] souboru přidáním metadata `Aliases` k původní položce "Odkaz". Chcete-li například nastavit alias "LS1" v příkazovém řádku následující CSC:<br /><br /> `csc /r:LS1=MyCodeLibrary.dll /r:LS2=MyCodeLibrary2.dll *.cs`<br /><br /> měli byste použít:<br /><br /> `<Reference Include="MyCodeLibrary"> <Aliases>LS1</Aliases> </Reference>`|  
|`Resources`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Vloží [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] prostředků do výstupního souboru.<br /><br /> Položky předaný do tento parametr může mít volitelná metadata položky s názvem `LogicalName` a `Access`. `LogicalName` odpovídá `identifier` parametr `/resource` přepínače, a `Access` odpovídá `accessibility-modifier` parametr. Další informace najdete v tématu [/Resource (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/resource-compiler-option).|  
|`ResponseFiles`|Volitelné `String` parametr.<br /><br /> Určuje soubor odpovědí, který obsahuje příkazy pro tuto úlohu. Další informace najdete v tématu [@ (určení souboru odezvy)](/dotnet/csharp/language-reference/compiler-options/response-file-compiler-option).|  
|`Sources`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje jeden nebo více [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] zdrojové soubory.|  
|`TargetType`|Volitelné `String` parametr.<br /><br /> Určuje formát souboru výstupního souboru. Tento parametr může mít hodnotu `library`, vytváří knihovny kódu `exe`, která vytvoří konzolovou aplikaci, `module`, která vytvoří modul, nebo `winexe`, vytváří programu systému Windows. Výchozí hodnota je `library`. Další informace najdete v tématu [/Target (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/target-compiler-option).|  
|`TreatWarningsAsErrors`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, zpracovává všech upozornění jako chyby. Další informace najdete v tématu [/warnaserror (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/warnaserror-compiler-option).|  
|`UseHostCompilerIfAvailable`|Volitelné `Boolean` parametr.<br /><br /> Dá pokyn úlohy použít objekt kompilátor, pokud je k dispozici. Používání pouze systémem [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|  
|`Utf8Output`|Volitelné `Boolean` parametr.<br /><br /> Zaznamená výstup kompilátoru pomocí kódování UTF-8. Další informace najdete v tématu [/utf8output (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/utf8output-compiler-option).|  
|`WarningLevel`|Volitelné `Int32` parametr.<br /><br /> Určuje úroveň pro upozornění pro kompilátor zobrazovat. Další informace najdete v tématu [/ warn (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/warn-compiler-option).|  
|`WarningsAsErrors`|Volitelné `String` parametr.<br /><br /> Určuje seznam upozornění na považovat za chyby. Další informace najdete v tématu [/warnaserror (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/warnaserror-compiler-option).<br /><br /> Tento parametr přepíše `TreatWarningsAsErrors` parametr.|  
|`WarningsNotAsErrors`|Volitelné `String` parametr.<br /><br /> Určuje seznam upozornění, která nejsou považovány za chyby. Další informace najdete v tématu [/warnaserror (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/warnaserror-compiler-option).<br /><br /> Tento parametr je užitečné, pouze pokud `TreatWarningsAsErrors` parametr je nastaven na `true`.|  
|`Win32Icon`|Volitelné `String` parametr.<br /><br /> Vloží soubor .ico, který v sestavení, která umožňuje výstupní soubor požadovaný vzhled v Průzkumníku souborů. Další informace najdete v tématu [/win32icon (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/win32icon-compiler-option).|  
|`Win32Manifest`|Volitelné `String` parametr.<br /><br /> Určuje manifest Win32 mají být zahrnuty.|  
|`Win32Resource`|Volitelné `String` parametr.<br /><br /> Vloží soubor prostředků (.res) Win32 ve výstupním souboru. Další informace najdete v tématu [/win32res (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/win32res-compiler-option).|  
  
## <a name="remarks"></a>Poznámky  
 Kromě parametry uvedené výše, zdědí tento úkol parametry z `Microsoft.Build.Tasks.ManagedCompiler` třídy, která dědí z <xref:Microsoft.Build.Tasks.ToolTaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.ToolTask> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [tooltaskextension – základní třída](../msbuild/tooltaskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `Csc` úloh zkompilovat spustitelný soubor ze zdrojových souborů v `Compile` kolekce položek.  
  
```xml  
<CSC  
    Sources="@(Compile)"  
    OutputAssembly="$(AppName).exe"  
    EmitDebugInformation="true" />  
```  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Úlohy](../msbuild/msbuild-tasks.md)
