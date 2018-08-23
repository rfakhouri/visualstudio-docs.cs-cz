---
title: Xmlpoke – úloha | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- XmlPoke task [MSBuild]
- MSBuild, XmlPoke task
ms.assetid: 6ba1953c-be3b-4df8-8561-e133408f8270
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ad3950c3aecb1144a588b0d232216a8a316b3b26
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668425"
---
# <a name="xmlpoke-task"></a>XmlPoke – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [xmlpoke – úloha](https://docs.microsoft.com/visualstudio/msbuild/xmlpoke-task).  
  
  
Nastaví hodnoty podle specifikace dotazu XPath do souboru XML.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `XmlPoke` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`Namespaces`|Volitelné `String` parametru.<br /><br /> Určuje obor názvů u předpony dotazu XPath.|  
|`Query`|Volitelné `String` parametru.<br /><br /> Určuje dotaz XPath.|  
|`Value`|Vyžaduje <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Určuje výstupní soubor.|  
|`XmlInputPath`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Určuje vstup XML jako cestu k souboru.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)



