---
title: Debugpropertyinfo – struktura | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- DebugPropertyInfo
apilocation:
- scrobj.dll
helpviewer_keywords:
- DebugPropertyInfo structure
ms.assetid: 3246efbc-c212-4024-8f07-6414c2f85e75
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 47c0f6a359341d19b99c1ce8c099ebf1c6d6a1ff
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54088982"
---
# <a name="debugpropertyinfo-structure"></a>DebugPropertyInfo – struktura
Popisuje objekt hierarchickou povahu, který má název, typ a hodnotu. Slouží k popisu vlastnosti ladění lokální proměnné, parametry, sledovat proměnné a výrazy a zaregistruje.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
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
 Výčtový datový typ, používá k určení, která pole jsou inicializovány.  
  
 bstrName  
 Název vlastnosti v rámci kontextu.  
  
 bstrType  
 Typ vlastnosti, jako formátovaný řetězec.  
  
 bstrValue  
 Hodnota vlastnosti jako formátovaný řetězec.  
  
 bstrFullName  
 Celý název vlastnosti.  
  
 dwAttrib  
 Výčet, který určuje příznaky pro atributy vlastnosti ladění.  
  
 pDebugProp  
 `IDebugProperty` Popsal informace v tomto `DebugPropertyInfo` struktury.  
  
## <a name="see-also"></a>Viz také  
 [Idebugproperty – rozhraní](../../winscript/reference/idebugproperty-interface.md)   
 [DBGPROP_ATTRIB_FLAGS](../../winscript/reference/dbgprop-attrib-flags.md)   
 [DBGPROP_INFO_FLAGS](../../winscript/reference/dbgprop-info-flags.md)