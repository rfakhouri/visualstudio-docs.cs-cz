---
title: ISimpleConnectionPoint::Advise | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
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
ms.openlocfilehash: 98db9c92f682808ce8ecc9f6aa382a2eb2bd8495
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62786259"
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
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vytvoří připojení mezi objektu bodu jednoduchých připojení a jímkou klienta.  
  
## <a name="see-also"></a>Viz také  
 [Isimpleconnectionpoint – rozhraní](../../winscript/reference/isimpleconnectionpoint-interface.md)   
 [ISimpleConnectionPoint::Unadvise](../../winscript/reference/isimpleconnectionpoint-unadvise.md)