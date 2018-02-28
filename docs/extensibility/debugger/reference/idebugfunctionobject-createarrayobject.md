---
title: IDebugFunctionObject::CreateArrayObject | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugFunctionObject::CreateArrayObject
helpviewer_keywords:
- IDebugFunctionObject::CreateArrayObject method
ms.assetid: a380e53c-15f1-401f-927f-f366eea789e6
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 5dfe24252ce2ce51ff86fa680d94964b86d09365
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugfunctionobjectcreatearrayobject"></a>IDebugFunctionObject::CreateArrayObject
Vytvoří objekt array. Toto pole může obsahovat buď primitivní nebo hodnot instance objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT CreateArrayObject(   
   OBJECT_TYPE    ot,  
   IDebugField*   pClassField,  
   DWORD          dwRank,  
   DWORD          dwDims[],  
   DWORD          dwLowBounds[],  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int CreateArrayObject(  
   enum_OBJECT_TYPE ot,   
   IDebugField      pClassField,   
   uint             dwRank,   
   uint[]           dwDims,   
   uint[]           dwLowBounds,   
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ot`  
 [v] Určuje hodnotu z [OBJECT_TYPE](../../../extensibility/debugger/reference/object-type.md) výčtu označující typ nového objektu pole.  
  
 `pClassField`  
 [v] [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objekt představující třídu objektu, pokud se vytváří instance hodnoty pole objektu. Pokud vytváříte pole primitivní objektů, je tento parametr hodnotu null.  
  
 `dwRank`  
 [v] Pořadí nebo počet rozměrů pole.  
  
 `dwDims`  
 [v] Velikosti Každá dimenze pole.  
  
 `dwLowBounds`  
 [v] Původ Každá dimenze (obvykle 0 nebo 1).  
  
 `ppObject`  
 [out] Vrátí [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objekt reprezentující nově vytvořený pole. Toto je ve skutečnosti [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md) objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Voláním této metody lze vytvořit objekt, který představuje parametr pole na funkci, která je reprezentována [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)