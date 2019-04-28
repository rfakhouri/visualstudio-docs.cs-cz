---
title: IEnumDebugExpressionContexts::Next | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumDebugExpressionContexts.Next
apilocation:
- jscript.dll
helpviewer_keywords:
- IEnumDebugExpressionContexts::Next
ms.assetid: aa223b0b-f7c1-4368-a59e-677e60133baf
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5128ba9ac90fc99cfec81b2c81711547947bfa49
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62807348"
---
# <a name="ienumdebugexpressioncontextsnext"></a>IEnumDebugExpressionContexts::Next
Načte zadaný počet segmentů v pořadí výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT Next(  
   ULONG                      celt,  
   IDebugExpressionContext**  ppdec,  
   ULONG*                     pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `celt`  
 [in] Počet segmentů, pro načtení.  
  
 `ppdec`  
 [out] Vrátí pole `IDebugExpressionContext` rozhraní, která představuje segmenty načítají.  
  
 `pceltFetched`  
 [out] Skutečný počet segmentů získaný enumerátor.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda načte zadaný počet segmentů v pořadí výčtu.  
  
## <a name="see-also"></a>Viz také  
 [IEnumDebugExpressionContexts – rozhraní](../../winscript/reference/ienumdebugexpressioncontexts-interface.md)