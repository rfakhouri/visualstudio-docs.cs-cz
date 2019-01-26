---
title: Updatemanifest – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, UpdateManifest task
- UpdateManifest task [MSBuild]
ms.assetid: 1291fd33-b89e-4e15-8fb1-69f9625cf2d2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 79d4eb1d9ea90f2ee10a5b285e8fd841b5405203
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54961294"
---
# <a name="updatemanifest-task"></a>UpdateManifest – úloha
Aktualizace vybraných vlastností v manifestu a vzdává.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `UpdateManifest` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`ApplicationManifest`|Vyžaduje <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Určuje manifest aplikace.|  
|`ApplicationPath`|Vyžaduje `String` parametru.<br /><br /> Určuje cestu k manifestu aplikace.|  
|`InputManifest`|Vyžaduje <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Určuje manifest aktualizovat.|  
|`OutputManifest`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> výstupní parametr.<br /><br /> Určuje manifest, který obsahuje aktualizované vlastnosti.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry ze <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [Task – základní třída](../msbuild/task-base-class.md).  
  
## <a name="see-also"></a>Viz také:  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)