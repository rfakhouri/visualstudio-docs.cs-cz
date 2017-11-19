---
title: "Debugpropertyinfo – struktura | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: DebugPropertyInfo
apilocation: scrobj.dll
helpviewer_keywords: DebugPropertyInfo structure
ms.assetid: 3246efbc-c212-4024-8f07-6414c2f85e75
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c9baade1a742a06c952906c05c574e752806bc9c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="debugpropertyinfo-structure"></a>DebugPropertyInfo – struktura
Popisuje objekt hierarchické povahy, který má název, typ a hodnotu. Slouží k popisu vlastnosti ladění lokální proměnné, parametry, sledovat proměnné a výrazy a zaregistruje.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct DebugPropertyInfo{  
   DBGPROP_INFO_FLAGS  dwValidFields;  
   BSTR  bstrName;  
   BSTR  bstrType;  
   BSTR  bstrValue;  
   BSTR  bstrFullName;  
   DBGPROP_ATTRIB_FLAGS  dwAttrib;  
   IDebugProperty*  pDebugProp;  
};  
```  
  
## <a name="members"></a>Členové  
 dwValidFields  
 Výčtový typ dat. slouží k zadání pole, která jsou inicializovány.  
  
 bstrName  
 Název vlastnosti v kontextu.  
  
 bstrType  
 Typ vlastnosti jako formátovaný řetězec.  
  
 bstrValue  
 Hodnota vlastnosti, jako formátovaný řetězec.  
  
 bstrFullName  
 Úplný název vlastnosti.  
  
 dwAttrib  
 Výčet, který určuje příznaky pro atributy vlastnosti ladění.  
  
 pDebugProp  
 `IDebugProperty` Popsaného informace v tomto `DebugPropertyInfo` struktura.  
  
## <a name="see-also"></a>Viz také  
 [Idebugproperty – rozhraní](../../winscript/reference/idebugproperty-interface.md)   
 [DBGPROP_ATTRIB_FLAGS](../../winscript/reference/dbgprop-attrib-flags.md)   
 [DBGPROP_INFO_FLAGS](../../winscript/reference/dbgprop-info-flags.md)