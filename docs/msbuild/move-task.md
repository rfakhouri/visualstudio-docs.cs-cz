---
title: Move – úloha | Microsoft Docs
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
- MSBuild, Move task
- Move task [MSBuild]
ms.assetid: d1405347-1309-4f18-b565-905408093d59
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2c5abd32476f5a1348c5120e2804a87656298f52
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31568110"
---
# <a name="move-task"></a>Move – úloha
Soubory přesune do nového umístění.  
  
## <a name="parameters"></a>Parametry  
 V následující tabulce jsou popsány parametry `Move` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`DestinationFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Určuje seznam souborů pro zdrojové soubory pro přesun. Tento seznam se očekává mapování 1: 1 do seznamu, který je uveden v `SourceFiles` parametr. To znamená, první soubor zadaný v `SourceFiles` přesunou do zadaného v první umístění `DestinationFiles`, a tak dále.|  
|`DestinationFolder`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje adresář, do které chcete přesunout soubory.|  
|`MovedFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje položky, které byly úspěšně přesunuty.|  
|`OverwriteReadOnlyFiles`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, přepíše soubory i v případě, že jsou označeny jako jen pro čtení souborů.|  
|`SourceFiles`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Určuje soubory, které chcete přesunout.|  
  
## <a name="remarks"></a>Poznámky  
 Buď `DestinationFolder` parametr nebo `DestinationFiles` parametr musí být zadaný, ale ne pomocí obou. Jsou-li zadány oba parametry, úloha se nezdaří a je zaznamenána chyba.  

 `Move` Úloh vytvoří podle potřeby pro soubory požadované cílové složky.

 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
