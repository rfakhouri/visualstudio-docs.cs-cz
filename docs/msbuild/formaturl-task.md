---
title: Formaturl – úloha | Microsoft Docs
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
- MSBuild, FormatUrl task
- FormatUrl task [MSBuild]
ms.assetid: 81114b67-520f-43b5-8891-224f68a78516
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 353dd60697d1e77adced612dee79cea97e4c7ba8
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31576336"
---
# <a name="formaturl-task"></a>FormatUrl – úloha
Převede adresu URL ve správném formátu adresy URL.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `FormatUrl` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`InputUrl`|Volitelné `String` parametr.<br /><br /> Určuje adresu URL k formátování.|  
|`OutputUrl`|Volitelné `String` výstupní parametr.<br /><br /> Určuje formátovaný adresu URL.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě nutnosti parametry, které jsou uvedené v tabulce tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)