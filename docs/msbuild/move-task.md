---
title: Move – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, Move task
- Move task [MSBuild]
ms.assetid: d1405347-1309-4f18-b565-905408093d59
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: dc2e11a1466f359cebb60505f498c0df3ae6c45b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62817519"
---
# <a name="move-task"></a>Move – úloha
Soubory přesunou do nového umístění.

## <a name="parameters"></a>Parametry
 Následující tabulka popisuje parametry `Move` úloh.

|Parametr|Popis|
|---------------|-----------------|
|`DestinationFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Určuje seznam souborů pro zdrojové soubory pro přesun. Tento seznam by měl být mapování 1: 1 v seznamu, který je zadán v `SourceFiles` parametru. To znamená, že první soubor zadaný v `SourceFiles` se přesune na první místo zadané v `DestinationFiles`a tak dále.|
|`DestinationFolder`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Určuje adresář, do kterého chcete přesunout soubory.|
|`MovedFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje položky, které byly úspěšně přesunuty.|
|`OverwriteReadOnlyFiles`|Volitelné `Boolean` parametru.<br /><br /> Pokud `true`, přepíše soubory i v případě, že jsou označeny jako soubory jen pro čtení.|
|`SourceFiles`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Určuje soubory, které chcete přesunout.|

## <a name="remarks"></a>Poznámky
 Buď `DestinationFolder` parametr nebo `DestinationFiles` parametr musí být zadaný, ale ne obojí. Jsou-li zadány oba parametry, úloha se nezdaří a je zaznamenána chyba.

 `Move` Úloh vytvoří složky podle potřeby pro požadované cílové soubory.

 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>Viz také:
- [Úlohy](../msbuild/msbuild-tasks.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
