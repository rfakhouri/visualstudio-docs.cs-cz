---
title: IDebugClassField::GetEnclosingClass | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
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
ms.openlocfilehash: 6cd73955835f8aff0047995a690da03e5ab0305d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugclassfieldgetenclosingclass"></a>IDebugClassField::GetEnclosingClass
Získá třídu, která obklopuje tuto třídu.  
  
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
 [out] Vrátí [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) třídu objektu, který představuje uzavření. Vrátí hodnotu null, pokud neexistuje žádná třída nadřazených.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pokud třída reprezentována to [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) objekt je vnořená třída, pak se `ppClassField` vrátí parametr `IDebugClassField` třídu objektu, který představuje uzavření. Například uděleno definici této třídy:  
  
```  
class RootClass {  
   class NestedClass { }  
};  
```  
  
 Volání `GetEnclosingClass` metodu `IDebugClassField` objekt reprezentující `NestedClass` vrací `IDebugClassField` objekt představující třídu `RootClass`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)