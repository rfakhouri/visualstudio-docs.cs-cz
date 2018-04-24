---
title: AL (Linker sestavení) – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#AL
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- AL task [MSBuild]
- MSBuild, AL task
ms.assetid: 2ddefbf2-5662-4d55-99a6-ac383bf44560
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 022e7f47f17292c62b851868b85773e8295a6991
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="al-assembly-linker-task"></a>AL (linker sestavení) – úloha
AL úloha zabalí AL.exe, nástroj, který je distribuován s [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]. Tento nástroj Linker sestavení slouží k vytvoření sestavení s manifestu z jeden nebo více souborů, které jsou buď moduly nebo soubory prostředků. Kompilátory a vývojových prostředích může již poskytují tyto funkce, je často není potřeba přímo pomocí této úlohy. Linker sestavení je velmi užitečné pro vývojáře, která potřebuje k vytvoření jednoho sestavení z více souborů součásti, jako jsou ty, které může být vytvářeny z vývojového smíšený jazyk. Tato úloha není moduly zkombinovat do jednoho sestavení souboru; jednotlivé moduly musí být stále distribuované a k dispozici v pořadí pro výsledný sestavení správně načíst. Další informace o AL.exe najdete v tématu [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `AL` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`AlgorithmID`|Volitelné `String` parametr.<br /><br /> Určuje algoritmus, který vytvoří hodnotu hash pro všechny soubory ve vícesouborovém sestavení s výjimkou souboru, který obsahuje manifest sestavení. Další informace najdete v dokumentaci pro `/algid` možnost [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`BaseAddress`|Volitelné `String` parametr.<br /><br /> Určuje adresu, na kterou budou v počítači uživatele za běhu načteny knihovny DLL. Aplikace načtou rychleji, pokud zadáte základní adresy knihovny DLL, než když necháte přemístit knihovny DLL v procesu operačního systému. Tento parametr odpovídá /base[adresu](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`CompanyName`|Volitelné `String` parametr.<br /><br /> Určuje řetězec pro `Company` pole v sestavení. Další informace najdete v dokumentaci pro `/comp[any]` možnost [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`Configuration`|Volitelné `String` parametr.<br /><br /> Určuje řetězec pro `Configuration` pole v sestavení. Další informace najdete v dokumentaci pro `/config[uration]` možnost [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`Copyright`|Volitelné `String` parametr.<br /><br /> Určuje řetězec pro `Copyright` pole v sestavení. Další informace najdete v dokumentaci pro `/copy[right]` možnost [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`Culture`|Volitelné `String` parametr.<br /><br /> Určuje řetězec jazykové verze přidružený k sestavení. Další informace najdete v dokumentaci pro `/c[ulture]` možnost [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`DelaySign`|Volitelné `Boolean` parametr.<br /><br /> `true` umístit pouze veřejný klíč v sestavení; `false` k plně podepsání sestavení. Další informace najdete v dokumentaci pro `/delay[sign]` možnost [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`Description`|Volitelné `String` parametr.<br /><br /> Určuje řetězec pro `Description` pole v sestavení. Další informace najdete v dokumentaci pro `/descr[iption]` možnost [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`EmbedResources`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Vloží zadané prostředky v bitové kopii, která obsahuje manifest sestavení. Tato úloha zkopíruje obsah souboru prostředků do bitové kopie. Volitelná metadata připojené k je volána, mohou mít položky předané do tohoto parametru `LogicalName` a `Access`. `LogicalName` Metadata slouží k určení interní identifikátor pro prostředek.  `Access` Metadata může být nastaven na `private` aby prostředku nejsou viditelné v rámci jiné sestavení. Další informace najdete v dokumentaci pro `/embed[resource]` možnost [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`EvidenceFile`|Volitelné `String` parametr.<br /><br /> Vloží zadaný soubor v sestavení s názvem prostředku `Security.Evidence`.<br /><br /> Nemůžete použít `Security.Evidence` běžných prostředků. Tento parametr odpovídá `/e[vidence]` možnost [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`ExitCode`|Volitelné `Int32` výstupní parametr jen pro čtení.<br /><br /> Určuje kód ukončení poskytované provedeného příkazu.|  
|`FileVersion`|Volitelné `String` parametr.<br /><br /> Určuje řetězec pro `File Version` pole v sestavení. Další informace najdete v dokumentaci pro `/fileversion` možnost [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`Flags`|Volitelné `String` parametr.<br /><br /> Určuje hodnotu `Flags` pole v sestavení. Další informace najdete v dokumentaci pro `/flags` možnost [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`GenerateFullPaths`|Volitelné `Boolean` parametr.<br /><br /> Způsobí, že úloha používat absolutní cestu pro všechny soubory, které jsou hlášeny v chybovou zprávu. Tento parametr odpovídá `/fullpaths` možnost [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`KeyContainer`|Volitelné `String` parametr.<br /><br /> Určuje kontejner obsahující pár klíčů. Toto podepíše sestavení (dá sestavení silný název) tak, že vloží veřejný klíč do manifestu sestavení. Úloha se pak se přihlaste konečné sestavení s privátním klíčem. Další informace najdete v dokumentaci pro `/keyn[ame]` možnost [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`KeyFile`|Volitelné `String` parametr.<br /><br /> Určuje soubor, který obsahuje pár klíčů nebo jenom veřejný klíč pro podepsání sestavení. Kompilátor vloží veřejný klíč do manifestu sestavení a poté podepíše konečné sestavení soukromým klíčem. Další informace najdete v dokumentaci pro `/keyf[ile]` možnost [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`LinkResources`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Odkazuje na sestavení souborů zadaný prostředek. Prostředek stane součástí sestavení, ale nebude soubor zkopírován. Volitelná metadata připojené k je volána, mohou mít položky předané do tohoto parametru `LogicalName`, `Target`, a `Access`. `LogicalName` Metadata slouží k určení interní identifikátor pro prostředek. `Target` Metadata můžete zadat cestu a název souboru, do které úlohu zkopíruje soubor, po který se zkompiluje tohoto nového souboru do sestavení. `Access` Metadata může být nastaven na `private` aby prostředku nejsou viditelné v rámci jiné sestavení. Další informace najdete v dokumentaci pro `/link[resource]` možnost [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`MainEntryPoint`|Volitelné `String` parametr.<br /><br /> Určuje plně kvalifikovaný název (*class.method*) metody, které chcete použít jako vstupní bod při převodu modulu na spustitelný soubor. Tento parametr odpovídá `/main` možnost [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`OutputAssembly`|Požadované <xref:Microsoft.Build.Framework.ITaskItem> výstupní parametr.<br /><br /> Určuje název souboru vygenerovaného této úlohy. Tento parametr odpovídá `/out` možnost [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`Platform`|Volitelné `String` parametr.<br /><br /> Omezení platformy, které tento kód můžete spustit na; musí mít jednu z `x86`, `Itanium`, `x64`, nebo `anycpu`. Výchozí hodnota je `anycpu`. Tento parametr odpovídá `/platform` možnost [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`ProductName`|Volitelné `String` parametr.<br /><br /> Určuje řetězec pro `Product` pole v sestavení. Další informace najdete v dokumentaci pro `/prod[uct]` možnost [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`ProductVersion`|Volitelné `String` parametr.<br /><br /> Určuje řetězec pro `ProductVersion` pole v sestavení. Další informace najdete v dokumentaci pro `/productv[ersion]` možnost [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`ResponseFiles`|Volitelné `String[]` parametr.<br /><br /> Určuje odpověď soubory, které obsahují další možnosti pro převedení Linker sestavení.|  
|`SdkToolsPath`|Volitelné `String` parametr.<br /><br /> Určuje cestu k SDK nástroje, jako je například resgen.exe.|  
|`SourceModules`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Jeden nebo více modulů ke kompilaci do sestavení. Moduly budou uvedené v manifestu výsledné sestavení a budete muset dál distribuované a k dispozici v pořadí pro sestavení načíst. Položky předaný do tento parametr může mít další metadata názvem `Target`, která určuje cestu a název souboru, do které úlohu zkopíruje soubor, po který se zkompiluje tohoto nového souboru do sestavení. Další informace najdete v dokumentaci pro [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker). Tento parametr odpovídá seznamu modulů předaný do Al.exe bez konkrétním přepínačem.|  
|`TargetType`|Volitelné `String` parametr.<br /><br /> Určuje formát souboru výstupního souboru: `library` (knihovny kódu), `exe` (Konzolová aplikace), nebo `win` (aplikace pro systém Windows). Výchozí hodnota je `library`. Tento parametr odpovídá `/t[arget]` možnost [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`TemplateFile`|Volitelné `String` parametr.<br /><br /> Určuje sestavení, ze kterého dědí všechny metadata sestavení, s výjimkou pole jazykovou verzi. Zadané sestavení musí mít silný název.<br /><br /> Sestavení, které vytvoříte pomocí `TemplateFile` parametr bude satelitní sestavení. Tento parametr odpovídá `/template` možnost [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`Timeout`|Volitelné `Int32` parametr.<br /><br /> Určuje množství času, v milisekundách, po kterých je spustitelný soubor úlohy ukončen. Výchozí hodnota je `Int.MaxValue`, což označuje, že bez doby vypršení časového limitu.|  
|`Title`|Volitelné `String` parametr.<br /><br /> Určuje řetězec pro `Title` pole v sestavení. Další informace najdete v dokumentaci pro `/title` možnost [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`ToolPath`|Volitelné `String` parametr.<br /><br /> Určuje umístění, ze kterých úloha načte základní spustitelný soubor (Al.exe). Pokud není tento parametr zadán, použije úloha cesta instalace sady SDK odpovídající verzi rozhraní, které běží [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)].|  
|`Trademark`|Volitelné `String` parametr.<br /><br /> Určuje řetězec pro `Trademark` pole v sestavení. Další informace najdete v dokumentaci pro `/trade[mark]` možnost [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`Version`|Volitelné `String` parametr.<br /><br /> Určuje informace o verzi pro toto sestavení. Formát řetězce je *major.minor.build.revision*. Výchozí hodnota je 0. Další informace najdete v dokumentaci pro `/v[ersion]` možnost [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`Win32Icon`|Volitelné `String` parametr.<br /><br /> Vloží soubor .ico do sestavení. Soubor .ico dává výstupnímu souboru požadovaný vzhled v Průzkumníku souborů. Tento parametr odpovídá `/win32icon` možnost [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`Win32Resource`|Volitelné `String` parametr.<br /><br /> Vloží prostředek systému Win32 (soubor .res) do výstupního souboru. Další informace najdete v dokumentaci pro `/win32res` možnost [Al.exe (Linker sestavení)](/dotnet/framework/tools/al-exe-assembly-linker).|  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.ToolTaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.ToolTask> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [tooltaskextension – základní třída](../msbuild/tooltaskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad vytvoří sestavení s konkrétní možnosti.  
  
```xml  
<AL  
    EmbedResources="@(EmbeddedResource)"  
    Culture="%(EmbeddedResource.Culture)"  
    TemplateFile="@(IntermediateAssembly)"  
    KeyContainer="$(KeyContainerName)"  
    KeyFile="$(KeyOriginatorFile)"  
    DelaySign="$(DelaySign)"  
  
    OutputAssembly=  
       "%(EmbeddedResource.Culture)\$(TargetName).resources.dll">  
  
    <Output TaskParameter="OutputAssembly"  
        ItemName="SatelliteAssemblies"/>  
</AL>  
```  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Úlohy](../msbuild/msbuild-tasks.md)