---
title: T4 – direktiva CleanUpBehavior | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e5a211f-a3bf-4229-bff0-7d2e45b71c64
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 9b9138ab564c7597715537216333f1efd0f3fc5a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667877"
---
# <a name="t4-cleanupbehavior-directive"></a>T4 CleanUpBehavior – direktiva
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [T4 CleanUpBehavior – direktiva](https://docs.microsoft.com/visualstudio/modeling/t4-cleanupbehavior-directive).  
  
Pro odstranění domény appDomain po zpracování textové šablony vložte následující řádek:  
  
```  
<#@ CleanupBehavior processor="T4VSHost" CleanupAfterProcessingtemplate="true" #>  
```  
  
 Textové šablony jsou zpracovávány v doméně appDomain, která je oddělena od hostitelského procesu. Ve většině případů se po zpracování jedné textové šablony použije doména appdomain znovu ke zpracování další šablony. Pokud ale zadáte CleanupBehavior, doména appDomain se odstraní a další šablona se zpracuje pomocí nové domény appDomain.  
  
 Sice se zpomalí zpracování textu, ale může to být užitečné, protože tím zajistíte likvidaci prostředků.  
  
 Tato direktiva funguje pouze u hostitele sady Visual Studio.



