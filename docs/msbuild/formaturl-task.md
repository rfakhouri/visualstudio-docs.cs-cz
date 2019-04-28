---
title: Formaturl – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, FormatUrl task
- FormatUrl task [MSBuild]
ms.assetid: 81114b67-520f-43b5-8891-224f68a78516
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e6c8bc23a843112a234dad0dfc718937bebfe5aa
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62931463"
---
# <a name="formaturl-task"></a>FormatUrl – úloha
Převede adresu URL na správném formátu adresy URL.

## <a name="parameters"></a>Parametry
 Následující tabulka popisuje parametry `FormatUrl` úloh.

|Parametr|Popis|
|---------------|-----------------|
|`InputUrl`|Volitelné `String` parametru.<br /><br /> Určuje adresu URL pro formátování.|
|`OutputUrl`|Volitelné `String` výstupní parametr.<br /><br /> Určuje formátovanou adresu URL.|

## <a name="remarks"></a>Poznámky
 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>Viz také:
- [Úlohy](../msbuild/msbuild-tasks.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)