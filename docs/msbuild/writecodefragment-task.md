---
title: "Writecodefragment – úloha | Microsoft Docs"
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
helpviewer_keywords:
- MSBuild, WriteCodeFragment task
- WriteCodeFragment task [MSBuild]
ms.assetid: 1d2514b4-5bef-43bb-bebe-496da8ef063c
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 6d08d4499ba0fcdc044b7189abeb9de1716b7ba4
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="writecodefragment-task"></a>WriteCodeFragment – úloha
Generuje soubor dočasné kód z fragment generovaného kódu. Nedojde k odstranění souboru.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `WriteCodeFragment` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`AssemblyAttributes`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Popis atributů pro zápis. Položka `Include` hodnota je název úplný typ atributu, například "System.AssemblyVersionAttribute".<br /><br /> Každý metadata jsou dvojice název hodnota parametru, který musí být typu `String`. Některé atributy Povolit jenom argumenty poziční konstruktoru. Takové argumenty však můžete všechny atributy. Pokud chcete nastavit atributy poziční konstruktor, použijte názvy metadat, které se podobají "_Parameter1", "_Parameter2" a tak dále.<br /><br /> Parametr index nelze přeskočit.|  
|`Language`|Požadované `String` parametr.<br /><br /> Určuje jazyk kódu pro generování.<br /><br /> `Language`může být jakýkoli jazyk pro který je k dispozici, zprostředkovatele CodeDom, například "C" nebo "VisualBasic". Emitovaného soubor bude mít výchozí přípona názvu souboru pro daný jazyk.|  
|`OutputDirectory`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje cílovou složku pro generovaný kód, obvykle zprostředkující složky.|  
|`OutputFile`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> výstupní parametr.<br /><br /> Určuje cestu k souboru, který byl vygenerován. Pokud tento parametr je nastaven pomocí názvu souboru, cílovou složku před název souboru. Pokud je nastavena pomocí kořenové, cílová složka je ignorována.<br /><br /> Pokud tento parametr není nastaven, je název výstupního souboru cílovou složku, název libovolný soubor a výchozí přípona názvu souboru pro určený jazyk.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)