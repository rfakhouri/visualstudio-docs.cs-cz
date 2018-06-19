---
title: JsValueType – výčet | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsValueType
helpviewer_keywords:
- JsValueType enumeration
ms.assetid: 6645e723-e554-41fc-b622-ab54ee044b3d
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: df4f61cf9118c19a0fc35e7505af422b812d0b43
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788625"
---
# <a name="jsvaluetype-enumeration"></a>JsValueType – výčet
Typ JavaScript jsvalueref –.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
enum JsValueType {  
    JsUndefined      = 0,  
    JsNull           = 1,  
    JsNumber         = 2,  
    JsString         = 3,  
    JsBoolean        = 4,  
    JsObject         = 5,  
    JsFunction       = 6,  
    JsError          = 7,  
    JsArray          = 8,  
    JsSymbol         = 9,  
    JsArrayBuffer    = 10,  
    JsTypedArray     = 11,  
    JsDataView       = 12,  
};  
```  
  
## <a name="members"></a>Členové  
  
### <a name="values"></a>Hodnoty  
  
|Název|Popis|  
|----------|-----------------|  
|`JsUndefined`|Hodnota je `undefined` hodnotu.|  
|`JsNull`|Hodnota je `null` hodnotu.|  
|`JsNumber`|Hodnota je hodnota číslo JavaScript.|  
|`JsString`|Hodnota je řetězcová hodnota JavaScript.|  
|`JsBoolean`|Hodnota je hodnota logická hodnota JavaScript.|  
|`JsObject`|Hodnota je hodnota objekt jazyka JavaScript.|  
|`JsFunction`|Hodnota je hodnota objektu funkce jazyka JavaScript.|  
|`JsError`|Hodnota je hodnota Chyba objekt jazyka JavaScript.|  
|`JsArray`|Hodnota je hodnota pole objekt jazyka JavaScript.|  
|`JsSymbol`|Hodnota je hodnota symbol jazyka JavaScript.<br /><br /> Tato hodnota výčtu je podporována pouze v režimu okraj.|  
|`JsArrayBuffer`|Hodnota je JavaScriptu `ArrayBuffer` hodnoty objektu.<br /><br /> Tato hodnota výčtu je podporována pouze v režimu okraj.|  
|`JsTypedArray`|Hodnota je JavaScriptu zadané hodnoty objektu pole.<br /><br /> Tato hodnota výčtu je podporována pouze v režimu okraj.|  
|`JsDataView`|Hodnota je JavaScriptu `DataView` hodnoty objektu.<br /><br /> Tato hodnota výčtu je podporována pouze v režimu okraj.|  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)