---
title: Touch – úloha | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Touch
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, Touch task
- Touch task [MSBuild]
ms.assetid: 8a978645-1393-4904-ae69-42afabd8c109
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 89116c56f3d3c24128b1b90d2130b98d04b071d0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668130"
---
# <a name="touch-task"></a>Touch – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Touch úloh](https://docs.microsoft.com/visualstudio/msbuild/touch-task).  
  
  
Nastaví dobu přístup a úpravy souborů.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `Touch` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`AlwaysCreate`|Volitelné `Boolean` parametru.<br /><br /> Pokud `true`, vytvoří všechny soubory, které už neexistují.|  
|`Files`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Určuje kolekci souborů, které mají dotykového ovládání.|  
|`ForceTouch`|Volitelné `Boolean` parametru.<br /><br /> Pokud `true`, vynutí touch soubor i v případě, že jsou soubory jen pro čtení.|  
|`Time`|Volitelné `String` parametru.<br /><br /> Určuje dobu, než aktuální čas. Musí být ve formátu formátu, který je akceptovatelná podle <xref:System.DateTime.Parse%2A> metody.|  
|`TouchedFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje kolekci položek, které byly úspěšně změněny.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu `Touch` úkolu, chcete-li změnit časy přístup a úpravy souborů zadaných v `Files` položky kolekce a vloží seznam úspěšně dokázal souborů v `FilesTouched` kolekci položek.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
<ItemGroup>  
    <Files Include="File1.cs;File2.cs;File3.cs" />  
</ItemGroup>  
  
    <Target Name="TouchFiles">  
        <Touch  
            Files="@(Files)">  
            <Output  
                TaskParameter="TouchedFiles"  
                ItemName="FilesTouched"/>  
    </Touch>  
</Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)



