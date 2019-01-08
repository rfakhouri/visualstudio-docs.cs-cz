---
title: Výčet JS_PROPERTY_ATTRIBUTES | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- JS_PROPERTY_ATTRIBUTES
apilocation:
- jscript9diag.dll
ms.assetid: e83b9b6c-5b21-48d1-92b6-22bed926b18b
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4a3fac8b1be15d1b1d26c13fe1e17e311798a3a3
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54088267"
---
# <a name="jspropertyattributes-enumeration"></a>Výčet JS_PROPERTY_ATTRIBUTES
Označuje atributy vlastnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
enum JS_PROPERTY_ATTRIBUTES{   JS_PROPERTY_ATTRIBUTE_NONE = 0,   JS_PROPERTY_HAS_CHILDREN = 0x1,   JS_PROPERTY_FAKE = 0x2,   JS_PROPERTY_METHOD = 0x4,   JS_PROPERTY_READONLY = 0x8,   JS_PROPERTY_NATIVE_WINRT_POINTER = 0x10} JS_PROPERTY_ATTRIBUTES;  
```  
  
## <a name="members"></a>Členové  
  
|Název|Popis|  
|----------|-----------------|  
|`JS_PROPERTY_ATTRIBUTE_NONE`|Vlastnost nemá žádné atributy.|  
|`JS_PROPERTY_HAS_CHILDREN`|Vlastnost má podřízené položky.|  
|`JS_PROPERTY_FAKE`|Vlastnost představuje uzel s falešnou, jako je například "[metody]".|  
|`JS_PROPERTY_METHOD`|Vlastnost je metoda.|  
|`JS_PROPERTY_READONLY`|Vlastnost je jen pro čtení.|  
|`JS_PROPERTY_NATIVE_WINRT_POINTER`|Vlastnost je ukazatel na nativní objekt WinRT.|  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jscript9diag.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace skriptovacích rozhraní systému Windows](../../winscript/reference/windows-script-interfaces-reference.md)