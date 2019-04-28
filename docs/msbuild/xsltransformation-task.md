---
title: Xsltransformation – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, XslTransformation task
- XslTransformation task [MSBuild]
ms.assetid: 6f3a7d81-3ae3-4703-9a06-870b32b69d80
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8330cb006143244458c9da0f3e76060275607fa5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62777600"
---
# <a name="xsltransformation-task"></a>XslTransformation – úloha
Transformace na XML vstup pomocí XSLT nebo kompilované XSLT a výstupů na zařízení s výstupní soubor nebo soubor.

## <a name="parameters"></a>Parametry
 Následující tabulka popisuje parametry `XslTransformation` úloh.

|Parametr|Popis|
|---------------|-----------------|
|`OutputPaths`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Určuje výstupní soubory transformace XML.|
|`Parameters`|Volitelné `String` parametru.<br /><br /> Určuje parametry XSLT vstupní dokument.|
|`XmlContent`|Volitelné `String` parametru.<br /><br /> Určuje vstup XML jako řetězec.|
|`XmlInputPaths`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametru.<br /><br /> Určuje vstupní soubor XML.|
|`XslCompiledDllPath`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Určuje kompilované XSLT.|
|`XslContent`|Volitelné `String` parametru.<br /><br /> Určuje vstup XSLT jako řetězec.|
|`XslInputPath`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Určuje vstupní soubor XSLT.|

## <a name="remarks"></a>Poznámky
 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>Viz také:
- [Úlohy](../msbuild/msbuild-tasks.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)