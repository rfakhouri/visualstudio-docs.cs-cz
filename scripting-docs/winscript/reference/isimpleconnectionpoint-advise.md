---
title: ISimpleConnectionPoint::Advise | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- ISimpleConnectionPoint.Advise
apilocation:
- pdm.dll
helpviewer_keywords:
- ISimpleConnectionPoint::Advise
ms.assetid: 59ded60d-b938-4110-aca3-e69ba234ca9a
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b3c0ea37e6fabb051458a11c4838061126bd98bf
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54091738"
---
# <a name="isimpleconnectionpointadvise"></a>ISimpleConnectionPoint::Advise
Naváže připojení mezi objektu bodu jednoduchých připojení a jímkou klienta.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT Advise(  
   IDispatch*  pdisp,  
   DWORD*      pdwCookie  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pdisp`  
 [in] Ukazatel `IDispatch` rozhraní na straně klienta je dokáží jímky. Jímka klienta obdrží odchozích volání z jednoduchého spojovací bod.  
  
 `pdwCookie`  
 [out] Ukazatel na vrácený token, který jednoznačně identifikuje toto připojení. Tento token volající později použije odstranit připojení tak, že předáte `ISimpleConnectionPoint::Unadvise` metoda. Pokud připojení nebylo úspěšně navázán, bude tato hodnota je nula.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vytvoří připojení mezi objektu bodu jednoduchých připojení a jímkou klienta.  
  
## <a name="see-also"></a>Viz také  
 [Isimpleconnectionpoint – rozhraní](../../winscript/reference/isimpleconnectionpoint-interface.md)   
 [ISimpleConnectionPoint::Unadvise](../../winscript/reference/isimpleconnectionpoint-unadvise.md)