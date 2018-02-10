---
title: "Formatversion – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 96e692f6-b581-46ca-8cc9-441a1861e371
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 468d5e60b2107118cdc2cf0e17b3e78b1133cc1c
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
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
|`FormatType`|Volitelné `String` parametr.<br /><br /> Určuje typ formátu.<br /><br /> -   "Version" = version.<br />-"Cesta"nahraďte ="." s "_";|  
|`OutputVersion`|Volitelné `String` výstupní parametr.<br /><br /> Určuje výstup verze, která obsahuje číslo revize.|  
|`Revision`|Volitelné `Int32` parametr.<br /><br /> Určuje revizi připojit k verzi.|  
|`Version`|Volitelné `String` parametr.<br /><br /> Určuje řetězec, číslo verze k formátování.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)