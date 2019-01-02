---
title: IDebugClassField::GetEnclosingClass | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugClassField::GetEnclosingClass
helpviewer_keywords:
- IDebugClassField::GetEnclosingClass method
ms.assetid: a0c12e3c-9ea0-4dfb-9e45-8cea18725022
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4cf74c5fd53d3ad75c9fc95e8217c849e3ce550c
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53851479"
---
# <a name="idebugclassfieldgetenclosingclass"></a>IDebugClassField::GetEnclosingClass
Získá třídu, která obklopuje této třídy.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetEnclosingClass(   
   IDebugClassField** ppClassField  
);  
```  
  
```csharp  
int GetEnclosingClass(  
   out IDebugClassField ppClassField  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppClassField`  
 [out] Vrátí [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) třídy představující nadřazený objekt. Vrátí hodnotu null, pokud neexistuje žádné nadřazené třídy.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pokud třída představovaného tímto rozhraním [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) objektu je vnořená třída, pak bude `ppClassField` vrátí parametr `IDebugClassField` třídy představující nadřazený objekt. Například při této definici třídy:  
  
```  
class RootClass {  
   class NestedClass { }  
};  
```  
  
 Volání `GetEnclosingClass` metodu `IDebugClassField` objekt představující `NestedClass` třídy vrátí `IDebugClassField` objekt představující třídu `RootClass`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)