---
title: ISimpleConnectionPoint::DescribeEvents | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- ISimpleConnectionPoint.DescribeEvents
apilocation:
- pdm.dll
helpviewer_keywords:
- ISimpleConnectionPoint::DescribeEvents
ms.assetid: 659ea05f-d41e-424a-bb38-df7672b2d135
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1b5824f945ad25f177fc169b58157377bf53bcce
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58145236"
---
# <a name="isimpleconnectionpointdescribeevents"></a>ISimpleConnectionPoint::DescribeEvents
Vrátí identifikátor DISPID a název pro každou jednotlivou událost v zadaném rozsahu událostí.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT DescribeEvents(  
   ULONG    iEvent,  
   ULONG    cEvents,  
   DISPID*  prgid,  
   BSTR*    prgbstr,  
   ULONG*   pcEventsFetched  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `iEvent`  
 [in] Index první událost pro načtení.  
  
 `cEvents`  
 [in] Počet událostí k načtení.  
  
 `prgid`  
 [out] Pole hodnoty DISPID události.  
  
 `prgbstr`  
 [out] Pole názvy událostí.  
  
 `pcEventsFetched`  
 [out] Skutečný počet načtených událostí.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`S_FALSE`|Další akce bylo vyžádáno, než byly k dispozici. Není k dispozici událostí jsou reprezentovány s DISPID_NULL a null BSTR.|  
|`E_INVALIDARG`|Může se načíst žádné elementy.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vrací identifikátor DISPID a název pro každou jednotlivou událost v zadaném rozsahu událostí.  
  
## <a name="see-also"></a>Viz také  
 [ISimpleConnectionPoint – rozhraní](../../winscript/reference/isimpleconnectionpoint-interface.md)