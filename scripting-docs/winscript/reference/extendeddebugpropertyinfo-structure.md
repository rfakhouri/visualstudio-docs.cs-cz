---
title: "Extendeddebugpropertyinfo – struktura | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- ExtendedDebugPropertyInfo
apilocation:
- scrobj.dll
helpviewer_keywords:
- ExtendedDebugPropertyInfo structure
ms.assetid: f2cf6477-454b-4d13-95da-ae4c90daa175
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ee06b0ace93f068e0530a3aa62b8c28d11069f44
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="extendeddebugpropertyinfo-structure"></a>ExtendedDebugPropertyInfo – struktura
Rozšiřuje `DebugPropertyInfo` struktura s další členy, chcete-li charakterizovat rozšířené vlastnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct ExtendedDebugPropertyInfo{  
   DBGPROP_INFO_FLAGS  dwValidFields;  
   LPOLESTR  bstrName;  
   LPOLESTR  bstrType;  
   LPOLESTR  bstrValue;  
   LPOLESTR  bstrFullName;  
   DBGPROP_ATTRIB_FLAGS  dwAttrib;  
   IDebugProperty*  pDebugProp;  
   DWORD  nDISPID;  
   DWORD  nType;  
   VARIANT  varValue;  
   ILockBytes*  plbValue;  
   IDebugExtendedProperty*  pDebugExtProp;  
};  
```  
  
## <a name="members"></a>Členové  
 `dwValidFields`  
 Výčtový typ dat. slouží k zadání pole, která jsou inicializovány.  
  
 `bstrName`  
 Název vlastnosti v kontextu.  
  
 `bstrType`  
 Typ vlastnosti jako formátovaný řetězec.  
  
 `bstrValue`  
 Hodnota vlastnosti jako řetězec formátovaný.  
  
 `bstrFullName`  
 Úplný název vlastnosti.  
  
 `dwAttrib`  
 Výčet, který určuje příznaky pro atributy vlastnosti ladění.  
  
 `pDebugProp`  
 `IDebugProperty`objekt odpovídající tomuto `ExtendedDebugPropertyInfo`.  
  
 `nDISPID`  
 Id odesílání.  
  
 `nType`  
 Rozšířené vlastnosti typu.  
  
 `varValue`  
 Hodnota rozšířené vlastnosti, pokud lze zobrazit v typu VARIANT.  
  
 `plbValue`  
 Skutečná data bajtů hodnoty vlastnosti.  
  
 `pDebugExtProp`  
 `IDebugExtendedProperty`objekt odpovídající tomuto `ExtendedDebugPropertyInfo`.  
  
## <a name="see-also"></a>Viz také  
 [Debugpropertyinfo – struktura](../../winscript/reference/debugpropertyinfo-structure.md)   
 [Idebugproperty – rozhraní](../../winscript/reference/idebugproperty-interface.md)   
 [Idebugextendedproperty – rozhraní](../../winscript/reference/idebugextendedproperty-interface.md)   
 [DBGPROP_ATTRIB_FLAGS](../../winscript/reference/dbgprop-attrib-flags.md)   
 [DBGPROP_INFO_FLAGS](../../winscript/reference/dbgprop-info-flags.md)