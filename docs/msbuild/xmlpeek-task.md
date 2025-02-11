---
title: Xmlpeek – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- XmlPeek task [MSBuild]
- MSBuild, XmlPeek task
ms.assetid: 19196031-a3bc-41b5-9c4a-f2572630e179
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 19b8273617955092519bf16f0aa5b3fbea86218a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62777818"
---
# <a name="xmlpeek-task"></a>XmlPeek – úloha
Vrací hodnoty podle specifikace dotazu XPath ze souboru XML.

## <a name="parameters"></a>Parametry
 Následující tabulka popisuje parametry `XmlPeek` úloh.

|Parametr|Popis|
|---------------|-----------------|
|`Namespaces`|Volitelné `String` parametru.<br /><br /> Určuje obor názvů u předpony dotazu XPath.|
|`Query`|Volitelné `String` parametru.<br /><br /> Určuje dotaz XPath.|
|`Result`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje výsledky, které jsou vráceny pomocí této úlohy.|
|`XmlContent`|Volitelné `String` parametru.<br /><br /> Určuje vstup XML jako řetězec.|
|`XmlInputPath`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Určuje vstup XML jako cestu k souboru.|

## <a name="remarks"></a>Poznámky
 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>Viz také:
- [Úlohy](../msbuild/msbuild-tasks.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)