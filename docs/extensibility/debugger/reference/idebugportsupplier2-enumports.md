---
title: IDebugPortSupplier2::EnumPorts | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugPortSupplier2::EnumPorts
helpviewer_keywords:
- IDebugPortSupplier2::EnumPorts
ms.assetid: 88b57fd2-eba1-44fa-bd34-cf2ad2b1ff87
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e317c3047b370b0ba5eb491f803b50b0496651ef
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53964254"
---
# <a name="idebugportsupplier2enumports"></a>IDebugPortSupplier2::EnumPorts
Načte seznam všechny porty, získáte ho od dodavatele portu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT EnumPorts(   
   IEnumDebugPorts2** ppEnum  
);  
```  
  
```csharp  
int EnumPorts(   
   out IEnumDebugPorts2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppEnum`  
 [out] Vrátí [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md) objekt, který obsahuje seznam portů zadaný.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)