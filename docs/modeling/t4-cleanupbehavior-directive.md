---
title: "T4 cleanupbehavior – direktiva | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 7df9fb0c4d567e6af4a0ac1ea3d8ab4832ffe5a7
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="t4-cleanupbehavior-directive"></a>T4 CleanUpBehavior – direktiva
Pro odstranění domény appDomain po zpracování textové šablony vložte následující řádek:  
  
```  
<#@ CleanupBehavior processor="T4VSHost" CleanupAfterProcessingtemplate="true" #>  
```  
  
 Textové šablony jsou zpracovávány v doméně appDomain, která je oddělena od hostitelského procesu. Ve většině případů se po zpracování jedné textové šablony použije doména appdomain znovu ke zpracování další šablony. Pokud ale zadáte CleanupBehavior, doména appDomain se odstraní a další šablona se zpracuje pomocí nové domény appDomain.  
  
 Sice se zpomalí zpracování textu, ale může to být užitečné, protože tím zajistíte likvidaci prostředků.  
  
 Tato direktiva funguje pouze u hostitele sady Visual Studio.