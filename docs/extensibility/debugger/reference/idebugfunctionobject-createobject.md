---
title: IDebugFunctionObject::CreateObject | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugFunctionObject::CreateObject
helpviewer_keywords:
- IDebugFunctionObject::CreateObject method
ms.assetid: c4c99dd5-609a-4e7c-8f29-eb728f57e995
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 94ee856f3f1b514fb4d6cb11c448edd102038953
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55031692"
---
# <a name="idebugfunctionobjectcreateobject"></a>IDebugFunctionObject::CreateObject
Vytvoří objekt pomocí konstruktoru.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT CreateObject(   
   IDebugFunctionObject* pConstructor,  
   DWORD                 dwArgs,  
   IDebugObject*         pArgs[],  
   IDebugObject**        ppObject  
);  
```  
  
```csharp  
int CreateObject(  
   IDebugFunctionObject pConstructor,   
   uint                 dwArgs,   
   IDebugObject[]       pArgs,   
   out IDebugObject     ppObject  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pConstructor`  
 [in] [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) objekt představující konstruktor objektu, který se má vytvořit.  
  
 `dwArgs`  
 [in] Počet parametrů `pArg` pole. Představuje počet parametry předané do konstruktoru.  
  
 `pArg`  
 [in] Pole [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objekty představující parametry předané do konstruktoru.  
  
 `ppObject`  
 [out] Vrátí `IDebugObject` představující nově vytvořený objekt.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Volejte tuto metodu za účelem vytvoření objektu, který představuje instance třídy (nebo jiné komplexní typ, který vyžaduje konstruktor), který je parametr pro funkci, která je reprezentována [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) rozhraní.  
  
 Pokud parametr objektu nevyžaduje konstruktor, zavolejte [CreateObjectNoConstructor](../../../extensibility/debugger/reference/idebugfunctionobject-createobjectnoconstructor.md) metody.  
  
## <a name="see-also"></a>Viz také  
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)   
 [CreateObjectNoConstructor](../../../extensibility/debugger/reference/idebugfunctionobject-createobjectnoconstructor.md)