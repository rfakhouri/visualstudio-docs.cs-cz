---
title: IDebugFunctionObject::CreateObject | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugFunctionObject::CreateObject
helpviewer_keywords: IDebugFunctionObject::CreateObject method
ms.assetid: c4c99dd5-609a-4e7c-8f29-eb728f57e995
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9ba06089624a585688f481719b2ce51397653cd1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
 [v] [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) objekt reprezentující konstruktoru objektu, který se má vytvořit.  
  
 `dwArgs`  
 [v] Počet parametrů `pArg` pole. Představuje počet parametrů předaný konstruktoru.  
  
 `pArg`  
 [v] Pole [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objekty představující parametry předaný konstruktoru.  
  
 `ppObject`  
 [out] Vrátí `IDebugObject` představující nově vytvořený objekt.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Volat tuto metodu pro vytvoření objektu, který představuje instanci třídy (nebo jiné komplexní typ, který vyžaduje konstruktor) tedy parametr pro funkci, která je reprezentována [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) rozhraní.  
  
 Pokud parametr objektu nevyžaduje konstruktor, zavolejte [CreateObjectNoConstructor](../../../extensibility/debugger/reference/idebugfunctionobject-createobjectnoconstructor.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)   
 [CreateObjectNoConstructor](../../../extensibility/debugger/reference/idebugfunctionobject-createobjectnoconstructor.md)