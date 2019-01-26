---
title: IEnumDebugThreads2::Clone | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IEnumDebugThreads2::Clone
helpviewer_keywords:
- IEnumDebugThreads2::Clone
ms.assetid: d774322c-e72d-4df3-b317-928da39dadc5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 25d8874b853b3d8930d99fa8f3099f22f2da9f4d
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54957725"
---
# <a name="ienumdebugthreads2clone"></a>IEnumDebugThreads2::Clone
Vrátí kopii objektu do aktuálního výčtu jako samostatný objekt.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Clone(  
   IEnumDebugThreads2** ppEnum  
);  
```  
  
```csharp  
int Clone(  
   out IEnumDebugThreads2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppEnum`  
 [out] Vrátí kopii objektu tento výčet jako samostatný objekt.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Kopírování výčet má stejného stavu jako původní v době, kdy tato metoda je volána. Ale tuto kopii a původní stavy jsou oddělené a je možné změnit individuálně.  
  
## <a name="see-also"></a>Viz také  
 [IEnumDebugThreads2](../../../extensibility/debugger/reference/ienumdebugthreads2.md)