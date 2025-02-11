---
title: IDebugExpression::Start | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugExpression.Start
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugExpression::Start
ms.assetid: a7af3470-62b5-40f0-987d-63b6b22538b3
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e80f3fb8087d39c76f59cf5c6bc8719c1cbaf5e4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62978520"
---
# <a name="idebugexpressionstart"></a>IDebugExpression::Start
Zahájí vyhodnocení výrazu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT Start(  
   IDebugExpressionCallBack*  pdecb  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pdecb`  
 [in] Zpětné volání pro ukazování po dokončení vyhodnocení výrazu. Pokud je tento parametr `NULL`, jsou vyvolávány žádné události a klient se musí dotazovat stav výrazu pomocí `QueryIsComplete`.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda začíná vyhodnocení výrazu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugExpression::Abort](../../winscript/reference/idebugexpression-abort.md)   
 [IDebugExpression – rozhraní](../../winscript/reference/idebugexpression-interface.md)