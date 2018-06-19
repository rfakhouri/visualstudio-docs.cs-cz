---
title: Formatversion – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 96e692f6-b581-46ca-8cc9-441a1861e371
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f5215f054f8da0e1118d4c7e66bc9c3c99d84c7b
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31568199"
---
# <a name="formatversion-task"></a>FormatVersion – úloha
Číslo revize se připojí k číslo verze.  
  
-   Případ #1: Vstupní: verze =\<nedefinované >;  Revize =\<nezajímá >;   Výstup: OutputVersion = "1.0.0.0"  
  
-   Případ #2: Vstupní: verze = "1.0.0.*" revize = "5" výstup: OutputVersion = "1.0.0.5"  
  
-   Případ #3: Vstupní: verze = "1.0.0.0" Revize =\<nezajímá >;  Výstup: OutputVersion = "1.0.0.0"  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `FormatVersion` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`FormatType`|Volitelné `String` parametr.<br /><br /> Určuje typ formátu.<br /><br /> -"Verze" = verze.<br />-"Cesta"nahraďte ="." s "_";|  
|`OutputVersion`|Volitelné `String` výstupní parametr.<br /><br /> Určuje výstup verze, která obsahuje číslo revize.|  
|`Revision`|Volitelné `Int32` parametr.<br /><br /> Určuje revizi připojit k verzi.|  
|`Version`|Volitelné `String` parametr.<br /><br /> Určuje řetězec, číslo verze k formátování.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)