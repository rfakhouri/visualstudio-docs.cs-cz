---
title: "T4 cleanupbehavior – direktiva | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f773f04799ec1ec975626699f37089c3c5b59b2d
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/13/2018
---
# <a name="t4-cleanupbehavior-directive"></a>T4 CleanUpBehavior – direktiva
Pro odstranění domény appDomain po zpracování textové šablony vložte následující řádek:  
  
```  
<#@ CleanupBehavior processor="T4VSHost" CleanupAfterProcessingtemplate="true" #>  
```  
  
 Textové šablony jsou zpracovávány v doméně appDomain, která je oddělena od hostitelského procesu. Ve většině případů se po zpracování jedné textové šablony použije doména appdomain znovu ke zpracování další šablony. Pokud ale zadáte CleanupBehavior, doména appDomain se odstraní a další šablona se zpracuje pomocí nové domény appDomain.  
  
 Sice se zpomalí zpracování textu, ale může to být užitečné, protože tím zajistíte likvidaci prostředků.  
  
 Tato direktiva funguje pouze u hostitele sady Visual Studio.