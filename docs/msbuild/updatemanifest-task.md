---
title: Updatemanifest – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, UpdateManifest task
- UpdateManifest task [MSBuild]
ms.assetid: 1291fd33-b89e-4e15-8fb1-69f9625cf2d2
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 58976744fddb59cfc9c6ef80de759a03196904e4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="updatemanifest-task"></a>UpdateManifest – úloha
Aktualizace vybraných vlastností v manifestu a odstoupí.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `UpdateManifest` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`ApplicationManifest`|Požadované <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje manifest aplikace.|  
|`ApplicationPath`|Požadované `String` parametr.<br /><br /> Určuje cestu k manifestu aplikace.|  
|`InputManifest`|Požadované <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje manifest aktualizovat.|  
|`OutputManifest`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> výstupní parametr.<br /><br /> Určuje manifestu, který obsahuje aktualizované vlastnosti.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [Třída Base úlohy](../msbuild/task-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)