---
title: Úloha GetFileHash | Dokumentace Microsoftu
ms.date: 01/28/2019
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- GetFileHash task [MSBuild]
- MSBuild, GetFileHash task
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ab5da58b125f86627d54547bd9f6f7cddc16c4de
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62977500"
---
# <a name="getfilehash-task"></a>GetFileHash úkolu

Vypočítá kontrolních součtů obsah souboru nebo sady souborů.

Tato úloha byla přidána do 15.8, ale vyžaduje [řešení](https://github.com/Microsoft/msbuild/pull/3999#issuecomment-458193272) pro MSBuild starším než 16.0.

## <a name="task-parameters"></a>Parametry úlohy

 Následující tabulka popisuje parametry `GetFileHash` úloh.

|Parametr|Popis|
|---------------|-----------------|
|`Files`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br />Soubory, které chcete použít algoritmus hash.|
|`Items`|<xref:Microsoft.Build.Framework.ITaskItem>`[]` Výstupní parametr.<br /><br />`Files` Vstup dalšími metadaty nastavena na hodnotu hash souboru.|
|`Hash`|`String` Výstupní parametr.<br /><br />Hodnota hash souboru. Tímto výstupem je nastavte pouze v případě byl předaný přesně jednu položku.|
|`Algorithm`|Volitelné `String` parametru.<br /><br />Algoritmus. Povolené hodnoty: `SHA256`, `SHA384`, `SHA512`. Výchozí = `SHA256`.|
|`MetadataName`|Volitelné `String` parametru.<br /><br />Název metadat ukládat hodnoty hash v každé položce. Výchozí hodnota je `FileHash`.|
|`HashEncoding`|Volitelné `String` parametru.<br /><br />Kódování určené k použití pro generované hodnoty hash. Výchozí hodnota je `hex`. Povolené hodnoty = `hex`, `base64`.|

## <a name="example"></a>Příklad

V následujícím příkladu `GetFileHash` úloh na určení a vytisknout kontrolní součet `FilesToHash` položky.

```xml
<Project>
  <ItemGroup>
    <FilesToHash Include="$(MSBuildThisFileDirectory)\*" />
  </ItemGroup>
  <Target Name="GetHash">
    <GetFileHash Files="@(FilesToHash)">
      <Output
          TaskParameter="Items"
          ItemName="FilesWithHashes" />
    </GetFileHash>

    <Message Importance="High"
             Text="@(FilesWithHashes->'%(Identity): %(FileHash)')" />
  </Target>
</Project>
```

## <a name="see-also"></a>Viz také:

- [Úlohy](../msbuild/msbuild-tasks.md)

- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)