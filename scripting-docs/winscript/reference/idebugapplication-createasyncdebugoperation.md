---
title: IDebugApplication::CreateAsyncDebugOperation | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplication.CreateAsyncDebugOperation
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::CreateAsyncDebugOperation
ms.assetid: bc32b101-6364-4498-8458-bd5f3ab5ad94
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c60c84dbd3be9248e2bd075e65d53f7f9361d0b5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62991019"
---
# <a name="idebugapplicationcreateasyncdebugoperation"></a>IDebugApplication::CreateAsyncDebugOperation
Poskytuje asynchronní přístup k dané ladění synchronní operace.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT CreateAsyncDebugOperation(  
   IDebugSyncOperation*    psdo,  
   IDebugAsyncOperation**  ppado  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `psdo`  
 [in] Objekt ladění synchronní operace.  
  
 `ppado`  
 [out] Operace objektu asynchronní ladění.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda umožňuje jazyk modulů k vyhodnocení výrazů asynchronně, ale explicitně nebyl synchronizován se vlákno ladicího programu. Další informace najdete v tématu [idebugsyncoperation – rozhraní](../../winscript/reference/idebugsyncoperation-interface.md) a [idebugasyncoperation – rozhraní](../../winscript/reference/idebugasyncoperation-interface.md).  
  
## <a name="see-also"></a>Viz také  
 [Idebugapplication – rozhraní](../../winscript/reference/idebugapplication-interface.md)   
 [Idebugsyncoperation – rozhraní](../../winscript/reference/idebugsyncoperation-interface.md)   
 [IDebugAsyncOperation – rozhraní](../../winscript/reference/idebugasyncoperation-interface.md)