---
title: IEnumDebugPropertyInfo::Skip | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumDebugPropertyInfo.Skip
apilocation:
- scrobj.dll
helpviewer_keywords:
- IEnumDebugPropertyInfo::Skip
ms.assetid: 2f6361fb-d66d-4fc0-8fe0-c859593a183f
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3e7544b8ea54fabc53e6c8476648e339c53da94d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62963387"
---
# <a name="ienumdebugpropertyinfoskip"></a>IEnumDebugPropertyInfo::Skip
Vynechá zadaný počet `DebugPropertyInfo` struktury v sekvenci výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT Skip(  
   ULONGcelt  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `celt`  
 [in] Počet `DebugPropertyInfo` struktury v pořadí výčtu pro přeskočení.  
  
## <a name="return-value"></a>Návratová hodnota  
 Bude vracet platnou `HRESULT`, obvykle `S_OK`. Vrátí `S_FALSE` a nastaví aktuální ukazatel na prvek na konci výčtu, pokud `celt` je větší než počet elementů vlevo v enumerátor.  
  
## <a name="see-also"></a>Viz také  
 [IEnumDebugPropertyInfo Interface](../../winscript/reference/ienumdebugpropertyinfo-interface.md)   
 [DebugPropertyInfo – struktura](../../winscript/reference/debugpropertyinfo-structure.md)