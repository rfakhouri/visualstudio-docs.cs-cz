---
title: Resolvenativereference – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ResolveNativeReference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, ResolveNativeReference task
- ResolveNativeReference task [MSBuild]
ms.assetid: 56acd101-de77-4eec-92c6-f5c6d2187579
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0f18549fece2db8a4a758dee17f6b4b1283d97e4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62996613"
---
# <a name="resolvenativereference-task"></a>ResolveNativeReference – úloha
Nativní odkazy řeší. Implementuje <xref:Microsoft.Build.Tasks.ResolveNativeReference> třídy. Tato třída podporuje infrastrukturu rozhraní .NET Framework, která není určena pro použití přímo v kódu.

## <a name="task-parameters"></a>Parametry úlohy
 Následující tabulka popisuje parametry `ResolveNativeReference` úloh.

|Parametr|Popis|
|---------------|-----------------|
|`AdditionalSearchPaths`|Požadovaný parametr <xref:System.String?displayProperty=fullName>`[]`.<br /><br /> Získá nebo nastaví cesty hledání pro řešení identit sestavení pro nativní odkazy.|
|`ContainedComComponents`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Získá nebo nastaví komponenty modelu COM nativní sestavení.|
|`ContainedLooseEtcFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Získá nebo nastaví, dojde ke ztrátě *atd* soubory uvedeny v nativní manifest.|
|`ContainedLooseTlbFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Získá nebo nastaví, dojde ke ztrátě *.tlb* soubory nativní sestavení.|
|`ContainedPrerequisiteAssemblies`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Získá nebo nastaví sestavení, která se musí nacházet před použitím v manifestu.|
|`ContainedTypeLibraries`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Získá nebo nastaví typ knihovny nativní sestavení.|
|`ContainingReferenceFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Získá nebo nastaví odkaz na soubory.|
|`NativeReferences`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Získá nebo nastaví odkazy na sestavení nativního Win32.|

## <a name="remarks"></a>Poznámky
 Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>Viz také:
- [Úlohy](../msbuild/msbuild-tasks.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)