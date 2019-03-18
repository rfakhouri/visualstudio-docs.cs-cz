---
title: Extendeddebugpropertyinfo – struktura | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- ExtendedDebugPropertyInfo
apilocation:
- scrobj.dll
helpviewer_keywords:
- ExtendedDebugPropertyInfo structure
ms.assetid: f2cf6477-454b-4d13-95da-ae4c90daa175
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1fe0eef00d2bf064a8a002925f4ba5607d36f31c
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58160469"
---
# <a name="extendeddebugpropertyinfo-structure"></a>ExtendedDebugPropertyInfo – struktura
Rozšiřuje `DebugPropertyInfo` strukturu s další členy, chcete-li charakterizovat rozšířené vlastnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
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
 Výčtový datový typ, používá k určení, která pole jsou inicializovány.  
  
 `bstrName`  
 Název vlastnosti v rámci kontextu.  
  
 `bstrType`  
 Typ vlastnosti jako formátovaný řetězec.  
  
 `bstrValue`  
 Hodnota vlastnosti jako formátovaný řetězec.  
  
 `bstrFullName`  
 Celý název vlastnosti.  
  
 `dwAttrib`  
 Výčet, který určuje příznaky pro atributy vlastnosti ladění.  
  
 `pDebugProp`  
 `IDebugProperty` objekt odpovídající této `ExtendedDebugPropertyInfo`.  
  
 `nDISPID`  
 Identifikátor odeslání.  
  
 `nType`  
 Rozšířené vlastnosti typu.  
  
 `varValue`  
 Rozšířené vlastnosti hodnotu, pokud lze zobrazit v typu VARIANT.  
  
 `plbValue`  
 Počet bajtů skutečná data hodnoty vlastnosti.  
  
 `pDebugExtProp`  
 `IDebugExtendedProperty` objekt odpovídající této `ExtendedDebugPropertyInfo`.  
  
## <a name="see-also"></a>Viz také  
 [Debugpropertyinfo – struktura](../../winscript/reference/debugpropertyinfo-structure.md)   
 [Idebugproperty – rozhraní](../../winscript/reference/idebugproperty-interface.md)   
 [Idebugextendedproperty – rozhraní](../../winscript/reference/idebugextendedproperty-interface.md)   
 [DBGPROP_ATTRIB_FLAGS](../../winscript/reference/dbgprop-attrib-flags.md)   
 [DBGPROP_INFO_FLAGS](../../winscript/reference/dbgprop-info-flags.md)