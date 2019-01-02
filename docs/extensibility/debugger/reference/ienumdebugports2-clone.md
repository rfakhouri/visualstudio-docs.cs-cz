---
title: IEnumDebugPorts2::Clone | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IEnumDebugPorts2::Clone
helpviewer_keywords:
- IEnumDebugPorts2::Clone
ms.assetid: d5ce77e8-bb99-409a-98fa-20fe5a0de25e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 489866d4c9830a611c02a416ff641357b8501ea2
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53934515"
---
# <a name="ienumdebugports2clone"></a>IEnumDebugPorts2::Clone
Vrátí kopii objektu do aktuálního výčtu jako samostatný objekt.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Clone(  
   IEnumDebugPorts2** ppEnum  
);  
```  
  
```csharp  
int Clone(  
   out IEnumDebugPorts2 ppEnum  
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
 [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)