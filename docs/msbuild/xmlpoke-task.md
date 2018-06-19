---
title: Xmlpoke – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- XmlPoke task [MSBuild]
- MSBuild, XmlPoke task
ms.assetid: 6ba1953c-be3b-4df8-8561-e133408f8270
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3295a5aee03badc52b980183e88f484e0d4bcc3a
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106944"
---
# <a name="xmlpoke-task"></a>XmlPoke – úloha

Nastaví hodnoty podle specifikace dotaz XPath do souboru XML.

## <a name="parameters"></a>Parametry

 Následující tabulka popisuje parametry `XmlPoke` úloh.
  
|Parametr|Popis|
|---------------|-----------------|
|`Namespaces`|Volitelné `String` parametr.<br /><br /> Určuje obor názvů pro předpony dotaz XPath.|
|`Query`|Volitelné `String` parametr.<br /><br /> Určuje dotaz XPath.|
|`Value`|Požadované <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje hodnotu, která má být vložen do zadané cesty.|
|`XmlInputPath`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje vstup XML jako cestu k souboru.|

## <a name="remarks"></a>Poznámky

 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>Viz také

 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)