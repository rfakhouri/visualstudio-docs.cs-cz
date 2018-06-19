---
title: Copy – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Copy
- MSBuild.Copy.SourceFileNotFound
- MSBuild.Copy.Retrying
- MSBuild.Copy.ExceededRetries
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, Copy task
- Copy task [MSBuild]
ms.assetid: a46ba9da-3e4e-4890-b4ea-09a099b6bc40
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1cd3f7e6c5075ad024e227c847ff05f186f7b016
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31570161"
---
# <a name="copy-task"></a>Copy – úloha
Zkopíruje soubory do nového umístění v systému souborů.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `Copy` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`CopiedFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje položky, které byly úspěšně zkopírovány.|  
|`DestinationFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje seznam souborů, do kterého se mají kopírovat zdrojové soubory. Tento seznam by měl být se seznamem uvedeným v parametru `SourceFiles` v relaci 1 : 1. To znamená, že první soubor zadaný v části `SourceFiles` bude zkopírován na první místo zadané v části `DestinationFiles` a tak dále.|  
|`DestinationFolder`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje adresář, do kterého se mají soubory kopírovat. Musí se jednat o adresář, nikoli o soubor. Pokud adresář neexistuje, je automaticky vytvořen.|  
|`OverwriteReadOnlyFiles`|Volitelné `Boolean` parametr.<br /><br /> Přepsat soubory i v případě, že jsou označeny jako soubory určené pouze pro čtení|  
|`Retries`|Volitelné `Int32` parametr.<br /><br /> Určuje počet pokusů o kopírování, pokud se všechny předchozí pokusy nezdařily. Výchozím nastavením je nula.<br /><br /> **Poznámka:** použití opakování maskovat synchronizace problém v procesu sestavení.|  
|`RetryDelayMilliseconds`|Volitelné `Int32` parametr.<br /><br /> Určuje zpoždění mezi nezbytnými pokusy o opakování. Výchozí hodnotou je argument RetryDelayMillisecondsDefault, který je předán konstruktoru CopyTask.|  
|`SkipUnchangedFiles`|Volitelné `Boolean` parametr.<br /><br /> Je-li hodnota `true`, přeskočí se kopírování souborů, u kterých mezi zdrojem a cílem nedošlo ke změně. Úloha `Copy` považuje soubory za nezměněné, pokud mají stejnou velikost a je uveden stejný čas poslední aktualizace. **Poznámka:** Pokud nastavíte tento parametr na `true`, byste neměli používat analysis závislost na obsahující cíl, protože úlohy používající pouze pokud poslední úpravy časy zdrojové soubory jsou novější než poslední úpravy dobu cílové soubory.|  
|`SourceFiles`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Určuje soubory ke kopírování.|  
|`UseHardlinksIfPossible`|Volitelné `Boolean` parametr.<br /><br /> Je-li hodnota `true`, pak namísto kopírování souborů vytvoří pevné odkazy na zkopírované soubory.|  
  
## <a name="warnings"></a>Upozornění  
 Přihlášení se upozornění, včetně:  
  
-   `Copy.DestinationIsDirectory`  
  
-   `Copy.SourceIsDirectory`  
  
-   `Copy.SourceFileNotFound`  
  
-   `Copy.CreatesDirectory`  
  
-   `Copy.HardLinkComment`  
  
-   `Copy.RetryingAsFileCopy`  
  
-   `Copy.FileComment`  
  
-   `Copy.RemovingReadOnlyAttribute`  
  
## <a name="remarks"></a>Poznámky  
 Je nutné zadat buď parametr `DestinationFolder`, nebo `DestinationFiles`, nikoli však oba. Jsou-li zadány oba parametry, úloha se nezdaří a je zaznamenána chyba.  
  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad zkopíruje položky v kolekci položek `MySourceFiles` do složky c:\MyProject\Destination.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <MySourceFiles Include="a.cs;b.cs;c.cs"/>  
    </ItemGroup>  
  
    <Target Name="CopyFiles">  
        <Copy  
            SourceFiles="@(MySourceFiles)"  
            DestinationFolder="c:\MyProject\Destination"  
        />  
    </Target>  
  
</Project>  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad znázorňuje postup rekurzivního kopírování. Tento projekt rekurzivně zkopíruje všechny soubory z umístění c:\MySourceTree do umístění c:\MyDestinationTree a zachová strukturu adresářů.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <MySourceFiles Include="c:\MySourceTree\**\*.*"/>  
    </ItemGroup>  
  
    <Target Name="CopyFiles">  
        <Copy  
            SourceFiles="@(MySourceFiles)"  
            DestinationFiles="@(MySourceFiles->'c:\MyDestinationTree\%(RecursiveDir)%(Filename)%(Extension)')"  
        />  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)