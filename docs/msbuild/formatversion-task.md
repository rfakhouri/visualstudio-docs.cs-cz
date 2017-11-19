---
title: "Formatversion – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 96e692f6-b581-46ca-8cc9-441a1861e371
caps.latest.revision: "5"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: c74b737febc0fd91286abd4e4c43c5f84b9e6452
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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