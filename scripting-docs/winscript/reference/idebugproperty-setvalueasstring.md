---
title: IDebugProperty::SetValueAsString | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugProperty.SetValueAsString
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugProperty::SetValueAsString
ms.assetid: cad8d7b2-19a5-4a29-9000-cafdecdc238b
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 75761c77281583336efd1f9b6466f7f2fd0cc291
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62979081"
---
# <a name="idebugpropertysetvalueasstring"></a>IDebugProperty::SetValueAsString
Nastaví hodnotu vlastnosti ze zadaného řetězce.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT SetValueAsString (  
   LPCOLESTR pszValue,  
   UINTnRadix,  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszValue`  
 [in] Nastavit hodnotu.  
  
 `nRadix`  
 [in] Základ, který se má použít při interpretaci jakékoli číselné informace.  
  
## <a name="return-value"></a>Návratová hodnota  
 Bude vracet platnou `HRESULT`, obvykle `S_OK`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProperty – rozhraní](../../winscript/reference/idebugproperty-interface.md)