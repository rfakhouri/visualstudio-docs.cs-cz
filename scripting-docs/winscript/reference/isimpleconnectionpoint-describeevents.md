---
title: ISimpleConnectionPoint::DescribeEvents | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
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
ms.openlocfilehash: 43a20a2d9580c80bc6aea5d22c6a0713f4843634
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54088501"
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