---
title: "JsMemoryEventType – výčet | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsMemoryEventType
helpviewer_keywords: JsMemoryEventType enumeration
ms.assetid: b4b176b6-b536-472e-8999-95b681a1df55
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ef39008ba84337cebdc9613db17cc9fbdfc8aa79
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="jsmemoryeventtype-enumeration"></a>JsMemoryEventType – výčet
Typ události přidělení zpětného volání.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
enum JsMemoryEventType;  
```  
  
## <a name="members"></a>Členové  
  
### <a name="values"></a>Hodnoty  
  
|Název|Popis|  
|----------|-----------------|  
|`JsMemoryAllocate`|Označuje požadavek na přidělení paměti.|  
|`JsMemoryFailure`|Označuje neúspěšné přidělení událostí.|  
|`JsMemoryFree`|Určuje paměť, uvolnění událostí.|  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)