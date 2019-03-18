---
title: Debugpropertyinfo – struktura | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
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
ms.openlocfilehash: 99208626b41f2463178bccecf73c21a1d15fa765
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58155742"
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