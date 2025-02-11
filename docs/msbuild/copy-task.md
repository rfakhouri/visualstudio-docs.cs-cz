---
title: Copy – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d996aa0c16c67cfdda23a1ecb63adcbb32d02b15
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62827113"
---
# <a name="copy-task"></a>Copy – úloha
Zkopíruje soubory do nového umístění v systému souborů.

## <a name="parameters"></a>Parametry
Následující tabulka popisuje parametry `Copy` úloh.

|Parametr|Popis|
|---------------|-----------------|
|`CopiedFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje položky, které byly úspěšně zkopírovány.|
|`DestinationFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametru.<br /><br /> Určuje seznam souborů, do kterého se mají kopírovat zdrojové soubory. Tento seznam by měl být se seznamem uvedeným v parametru `SourceFiles` v relaci 1 : 1. To znamená, že první soubor zadaný v části `SourceFiles` bude zkopírován na první místo zadané v části `DestinationFiles` a tak dále.|
|`DestinationFolder`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Určuje adresář, do kterého se mají soubory kopírovat. Musí se jednat o adresář, nikoli o soubor. Pokud adresář neexistuje, je automaticky vytvořen.|
|`OverwriteReadOnlyFiles`|Volitelné `Boolean` parametru.<br /><br /> Přepsat soubory i v případě, že jsou označeny jako soubory určené pouze pro čtení|
|`Retries`|Volitelné `Int32` parametru.<br /><br /> Určuje počet pokusů o kopírování, pokud se všechny předchozí pokusy nezdařily. Výchozím nastavením je nula.<br /><br /> **Poznámka:** Použití opakování může zastínit problém se synchronizací v procesu sestavení.|
|`RetryDelayMilliseconds`|Volitelné `Int32` parametru.<br /><br /> Určuje zpoždění mezi nezbytnými pokusy o opakování. Výchozí hodnotou je argument RetryDelayMillisecondsDefault, který je předán konstruktoru CopyTask.|
|`SkipUnchangedFiles`|Volitelné `Boolean` parametru.<br /><br /> Je-li hodnota `true`, přeskočí se kopírování souborů, u kterých mezi zdrojem a cílem nedošlo ke změně. Úloha `Copy` považuje soubory za nezměněné, pokud mají stejnou velikost a je uveden stejný čas poslední aktualizace. <br /><br /> **Poznámka:**  Při nastavení tohoto parametru na hodnotu `true` by pro obsažený cíl neměla být použita analýza závislosti, protože spouští úlohu pouze v případě, že čas poslední aktualizace zdrojových souborů je novější než čas poslední aktualizace cílových souborů.|
|`SourceFiles`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Určuje soubory ke kopírování.|
|`UseHardlinksIfPossible`|Volitelné `Boolean` parametru.<br /><br /> Je-li hodnota `true`, pak namísto kopírování souborů vytvoří pevné odkazy na zkopírované soubory.|

## <a name="warnings"></a>Upozornění
Upozornění k přihlášení, včetně:

- `Copy.DestinationIsDirectory`

- `Copy.SourceIsDirectory`

- `Copy.SourceFileNotFound`

- `Copy.CreatesDirectory`

- `Copy.HardLinkComment`

- `Copy.RetryingAsFileCopy`

- `Copy.FileComment`

- `Copy.RemovingReadOnlyAttribute`

## <a name="remarks"></a>Poznámky
Je nutné zadat buď parametr `DestinationFolder`, nebo `DestinationFiles`, nikoli však oba. Jsou-li zadány oba parametry, úloha se nezdaří a je zaznamenána chyba.

Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).

## <a name="example"></a>Příklad
Následující příklad zkopíruje položky v `MySourceFiles` položky kolekce do složky *c:\MyProject\Destination*.

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
Následující příklad znázorňuje postup rekurzivního kopírování. Tento projekt zkopíruje všechny soubory rekurzivně z *c:\MySourceTree* do *c:\MyDestinationTree*, při zachování adresářovou strukturu.

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

## <a name="see-also"></a>Viz také:
- [Úlohy](../msbuild/msbuild-tasks.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
