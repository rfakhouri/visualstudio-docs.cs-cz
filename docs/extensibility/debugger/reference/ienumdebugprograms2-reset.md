---
title: IEnumDebugPrograms2::Reset | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IEnumDebugPrograms2::Reset
helpviewer_keywords:
- IEnumDebugPrograms2::Reset
ms.assetid: b289242b-24ea-4df3-a811-20b0c8a903d6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 88d95b58f429c8a6012769166bf740f06675a994
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53905384"
---
# <a name="ienumdebugprograms2reset"></a>IEnumDebugPrograms2::Reset
Obnoví výčtu na první prvek.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Reset(  
   void  
);  
```  
  
```csharp  
int Reset();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Až tato metoda je volána, další volání [Další](../../../extensibility/debugger/reference/ienumdebugprograms2-next.md) metoda vrátí první prvek výčtu.  
  
## <a name="see-also"></a>Viz také  
 [IEnumDebugPrograms2](../../../extensibility/debugger/reference/ienumdebugprograms2.md)