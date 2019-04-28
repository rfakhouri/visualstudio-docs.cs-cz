---
title: Úloha VerifyFileHash | Dokumentace Microsoftu
ms.date: 01/28/2019
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- VerifyFileHash task [MSBuild]
- MSBuild, VerifyFileHash task
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: faf7738019680085020b9650094931d5860bc29b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62577359"
---
# <a name="verifyfilehash-task"></a>VerifyFileHash úkolu

Ověřuje, že soubor odpovídající hodnotě hash očekávaného souboru.

Tato úloha byla přidána do 15.8, ale vyžaduje [řešení](https://github.com/Microsoft/msbuild/pull/3999#issuecomment-458193272) pro MSBuild starším než 16.0.

## <a name="task-parameters"></a>Parametry úlohy

 Následující tabulka popisuje parametry `VerifyFileHash` úloh.

|Parametr|Popis|
|---------------|-----------------|
|`File`|Vyžaduje <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br />Soubory, které mají hodnotu hash a ověřit.|
|`Hash`|Vyžaduje `String` parametru.<br /><br />Očekávaná hodnota hash souboru.|
|`Items`|<xref:Microsoft.Build.Framework.ITaskItem>`[]` Výstupní parametr.<br /><br />`Files` Vstup dalšími metadaty nastavena na hodnotu hash souboru.|
|`Algorithm`|Volitelné `String` parametru.<br /><br />Algoritmus. Povolené hodnoty: `SHA256`, `SHA384`, `SHA512`. Výchozí = `SHA256`.|
|`HashEncoding`|Volitelné `String` parametru.<br /><br />Kódování určené k použití pro generované hodnoty hash. Výchozí hodnota je `hex`. Povolené hodnoty = `hex`, `base64`.|

## <a name="example"></a>Příklad

V následujícím příkladu `VerifyFileHash` úkolů, ověřit svůj vlastní kontrolní součet.

```xml
<Project>
  <Target Name="VerifyHash">
    <GetFileHash Files="$(MSBuildProjectFullPath)">
      <Output
          TaskParameter="Items"
          ItemName="FilesWithHashes" />
    </GetFileHash>

    <Message Importance="High"
             Text="@(FilesWithHashes->'%(Identity): %(FileHash)')" />

    <VerifyFileHash File="$(MSBuildThisFileFullPath)"
                    Hash="$(ExpectedHash)" />
  </Target>
</Project>
```

## <a name="see-also"></a>Viz také:

- [Úlohy](../msbuild/msbuild-tasks.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)