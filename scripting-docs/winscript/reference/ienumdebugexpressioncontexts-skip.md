---
title: IEnumDebugExpressionContexts::Skip | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumDebugExpressionContexts.Skip
apilocation:
- jscript.dll
helpviewer_keywords:
- IEnumDebugExpressionContexts::Skip
ms.assetid: 3498cbb5-8581-4dcd-b016-e86b049c7831
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5176eb83c4c5bfe517066d8ea7f52b76e121fb26
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62963517"
---
# <a name="ienumdebugexpressioncontextsskip"></a>IEnumDebugExpressionContexts::Skip
Vynechá zadaný počet segmentů v sekvenci výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT Skip(  
   ULONG  celt  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `celt`  
 [in] Počet segmentů v pořadí výčtu pro přeskočení.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vynechá zadaný počet segmentů v sekvenci výčtu.  
  
## <a name="see-also"></a>Viz také  
 [IEnumDebugExpressionContexts – rozhraní](../../winscript/reference/ienumdebugexpressioncontexts-interface.md)