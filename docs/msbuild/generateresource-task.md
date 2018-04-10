---
title: Generateresource – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: msbuild
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#GenerateResource
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, GenerateResource task
- GenerateResource task [MSBuild]
ms.assetid: c0aff32f-f2cc-46f6-9c3e-a5c9f8f912b1
caps.latest.revision: 15
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 37aacbfd2095cf4edae78393569702fe4fea6c7e
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/10/2018
---
# <a name="generateresource-task"></a>GenerateResource – úloha
Převede mezi .txt a soubory RESX (formát založený na jazyce XML prostředku) a společné jazykové runtime .resources binární soubory, které můžete vložených do binární spustitelného nebo zkompilovat do satelitní sestavení. Tato úloha se obvykle používá převést soubory s příponou TXT nebo RESX soubory Resource. `GenerateResource` Úloh je funkčně podobná [resgen.exe](/dotnet/framework/tools/resgen-exe-resource-file-generator).  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `GenerateResource` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`AdditionalInputs`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Obsahuje další vstupy Kontrola závislosti, které se provádí tuto úlohu. Například soubory projektu a cíle měl by být obvykle vstupy, takže pokud jsou aktualizováni, všechny prostředky jsou vygenerovány znovu.|  
|`EnvironmentVariables`|Volitelné `String[]` parametr.<br /><br /> Určuje pole dvojic název hodnota prostředí proměnné, které by měla být vytvořená resgen.exe předána kromě (nebo selektivně přepsání) bloku regulární prostředí.|  
|`ExcludedInputPaths`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje pole položek, která ke specifikaci cest, ze kterých budou během aktuální kontrola ignorovány sledovaných vstupy.|  
|`ExecuteAsTool`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, spouští tlbimp.exe a aximp.exe z příslušná cílová framework out-of-proc ke generování sestavení nezbytné obálku. Tento parametr umožňuje cílení na více verzí z `ResolveComReferences`.|  
|`FilesWritten`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje názvy všech souborů zapsat na disk. To zahrnuje soubor mezipaměti, pokud existuje. Tento parametr je užitečné pro implementace vyčistit.|  
|`MinimalRebuildFromTracking`|Volitelné `Boolean` parametr.<br /><br /> Získá nebo nastaví přepínač, který určuje, zda bude použit sledovaných přírůstkové sestavení. Pokud `true`, je zapnutá přírůstkové sestavení; jinak bude vynutit opětovném sestavení.|  
|`NeverLockTypeAssemblies`|Volitelné `Boolean` parametr.<br /><br /> Získá nebo nastaví logickou hodnotu, která určuje, zda chcete vytvořit nový [AppDomain](/dotnet/api/system.appdomain) k vyhodnocení, soubory prostředků (RESX) (true) nebo vytvořit nový [AppDomain](/dotnet/api/system.appdomain) pouze když soubory prostředků odkazují na uživatele sestavení (false).|  
|`OutputResources`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Určuje název generovaného souborů, jako jsou například soubory .resources. Pokud název nezadáte, bude použit název odpovídající vstupní soubor a souboru .resources, který se vytvoří je umístěn v adresáři, který obsahuje vstupní soubor.|  
|`PublicClass`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, vytvoří třídu jako veřejná Třída prostředků se silnými typy.|  
|`References`|Volitelné `String[]` parametr.<br /><br /> Odkazy na načíst typy v soubory RESX z. Elementy datového souboru RESX může mít typ formátu .NET. Pokud je pro čtení souboru RESX, to je třeba vyřešit. Obvykle se nevyřeší úspěšně pomocí standardní typ načítání pravidla. Pokud zadáte sestavení v `References`, že mají přednost před.<br /><br /> Tento parametr není potřeba prostředky se silnými typy.|  
|`SdkToolsPath`|Volitelné `String` parametr.<br /><br /> Určuje cestu k SDK nástroje, jako je například resgen.exe.|  
|`Sources`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Určuje položky, které chcete převést. Položek předaných tento parametr musí mít jednu z následujících přípon:<br /><br /> -   `.txt`: Určuje rozšíření pro textový soubor převést. Řetězce prostředků může obsahovat pouze textové soubory.<br />-   `.resx`: Určuje rozšíření pro soubor prostředků na základě XML, který chcete převést.<br />-   `.restext`: Určuje stejný formát jako .txt. Tato jiné rozšíření je užitečné, pokud budete chtít jasně odlišit zdrojové soubory, které obsahují prostředky z jiné zdrojové soubory v procesu sestavení.<br />-   `.resources`: Určuje příponu soubor prostředků pro převod.|  
|`StateFile`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje cestu k souboru volitelné mezipaměti, který se používá k urychlení kontrolu odkazů na vstupní soubory RESX závislosti.|  
|`StronglyTypedClassName`|Volitelné `String` parametr.<br /><br /> Určuje název třídy pro třídy prostředků se silnými typy. Pokud není tento parametr zadán, je použít základní název souboru prostředků.|  
|`StronglyTypedFilename`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje název souboru pro zdrojový soubor. Pokud není tento parametr zadán, název třídy se používá jako základní název souboru s příponou závislých na jazyku. Příklad: `MyClass.cs`.|  
|`StronglyTypedLanguage`|Volitelné `String` parametr.<br /><br /> Určuje jazyk, který chcete použít při generování zdroj Třída prostředků se silnými typy. Tento parametr musí odpovídat přesně jednomu z jazyků používaných CodeDomProvider. Příklad: `VB` nebo `C#`.<br /><br /> Předáním hodnoty pro tento parametr má úloha sloužící ke generování silného typu prostředků.|  
|`StronglyTypedManifestPrefix`|Volitelné `String` parametr.<br /><br /> Určuje předponu oboru názvů nebo manifest prostředků pro použití v zdroji generovaná třída silného typu prostředku.|  
|`StronglyTypedNamespace`|Volitelné `String` parametr.<br /><br /> Určuje obor názvů, který chcete použít pro zdroj generovaná třída prostředků se silnými typy. Pokud není tento parametr zadán, jsou všechny prostředky, silného typu v globálním oboru názvů.|  
|`TLogReadFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr jen pro čtení.<br /><br /> Získá pole položek, které představují čtení sledování protokolů.|  
|`TLogWriteFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr jen pro čtení.<br /><br /> Získá pole položek, které představují zápisu sledování protokolů.|  
|`ToolArchitecture`|Volitelné <xref:System.String?displayProperty=fullName> parametr.<br /><br /> Použít k určení, zda se musí použít vytváření ResGen.exe Tracker.exe.<br /><br /> Musí být parsable k členem <xref:Microsoft.Build.Utilities.ExecutableType> výčtu. Pokud `String.Empty`, používá k určení výchozí architektura heuristika. Musí být parsable na člena výčtu Microsoft.Build.Utilities.ExecutableType.|  
|`TrackerFrameworkPath`|Volitelné `String` parametr.<br /><br /> Určuje cestu, do příslušného umístění rozhraní .NET Framework, který obsahuje FileTracker.dll.<br /><br /> Pokud sada, uživatel má odpovědnost za a ověřte, zda počtu bitů FileTracker.dll, který předávají odpovídá počtu bitů ResGen.exe, mají v úmyslu použít. Pokud není sada, úloha rozhodne na požadované místo na základě aktuální verze rozhraní .NET Framework.|  
|`TrackerLogDirectory`|Volitelné `String` parametr.<br /><br /> Určuje zprostředkující adresář, do kterého se umístí protokoly sledování na spuštění úlohy.|  
|`TrackerSdkPath`|Volitelné `String` parametr.<br /><br /> Určuje cestu, do příslušného umístění sady Windows SDK, který obsahuje Tracker.exe.<br /><br /> Pokud sada, uživatel má odpovědnost za a ověřte, zda počtu bitů Tracker.exe který předávají odpovídá počtu bitů ResGen.exe, mají v úmyslu použít. Pokud není sada, úloha rozhodne na požadované místo podle aktuální sady Windows SDK.|  
|`TrackFileAccess`|Volitelné <xref:System.Boolean> parametr.<br /><br /> V případě hodnoty true adresáři souboru vstupního souboru se používá k vyřešení relativní cesty k souboru.|  
|`UseSourcePath`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, určuje, zda má být použit k vyřešení relativní cesty k souboru je vstupní soubor directory.|  
  
## <a name="remarks"></a>Poznámky  
 Protože soubory RESX mohou obsahovat odkazy na jiné soubory prostředků, není dostatečná k jednoduše porovnání resx a Resource časová razítka souboru zda výstupy nejsou aktuální. Místo toho `GenerateResource` úlohy odpovídá na odkazy v soubory RESX a kontroluje časová razítka propojených souborů. To znamená, že byste neměli používat obecně `Inputs` a `Outputs` atributů na cíl obsahující `GenerateResource` úloh, protože to může způsobit při by měl běžet ve skutečnosti přeskočen.  
  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
 Při použití nástroje MSBuild 4.0 do projektů cílených rozhraní .NET 3.5, mohou být neúspěšné x86 sestavení prostředků. Chcete-li tento problém obejít, můžete vytvořit cíl jako AnyCPU sestavení.  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `GenerateResource` úloh Generovat soubory .resources z souborů určených `Resx` kolekce položek.  
  
```xml  
<GenerateResource  
    Sources="@(Resx)"  
    OutputResources="@(Resx->'$(IntermediateOutputPath)%(Identity).resources')">  
    <Output  
        TaskParameter="OutputResources"  
        ItemName="Resources"/>  
</GenerateResource>  
```  
  
 `GenerateResource` Úloh používá \<LogicalName > metadata \<EmbeddedResource > položky se název prostředku, který je součástí sestavení.  
  
 Za předpokladu, že sestavení s názvem myAssembly, generuje následující kód vložený prostředek s názvem someQualifier.someResource.resources:  
  
```xml  
<ItemGroup>   <EmbeddedResource Include="myResource.resx">       <LogicalName>someQualifier.someResource.resources</LogicalName>   </EmbeddedResource></ItemGroup>  
```  
  
 Bez \<LogicalName > metadata, prostředku by se jmenovala myAssembly.myResource.resources.  Tento příklad se týká pouze procesu sestavení jazyka Visual Basic a Visual C#.  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
