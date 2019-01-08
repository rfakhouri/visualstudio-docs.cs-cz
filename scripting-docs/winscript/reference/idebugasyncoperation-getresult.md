---
title: IDebugAsyncOperation::GetResult | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugAsyncOperation.GetResult
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugAsyncOperation::GetResult
ms.assetid: 56d43365-6b12-4213-a97c-953c40d7b7f6
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d86e9eb2b934bc6bd4027405d06960cd107f81c1
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54087474"
---
# <a name="idebugasyncoperationgetresult"></a>IDebugAsyncOperation::GetResult
Poskytuje návratovou hodnotu a parametr vrácený objekt z ladění synchronní operace.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetResult(  
   HRESULT*    phrResult,  
   IUnknown**  ppunkResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `phrResult`  
 [out] Pokud je operace dokončena, `phrResult` je návratová hodnota `IDebugSyncOperation::Execute`.  
  
 `ppunkResult`  
 [out] Pokud je operace dokončena, `ppunkResult` je parametr objektu vrácená operací.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`E_PENDING`|Operace se nedokončila.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud se operace dokončí, vrátí tato metoda `HRESULT` a parametru z objektu `IDebugSyncOperation::Execute`.  
  
## <a name="see-also"></a>Viz také  
 [Idebugasyncoperation – rozhraní](../../winscript/reference/idebugasyncoperation-interface.md)   
 [IDebugSyncOperation::Execute](../../winscript/reference/idebugsyncoperation-execute.md)