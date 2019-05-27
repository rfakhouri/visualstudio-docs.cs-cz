---
title: IDebugFunctionObject::CreateObjectNoConstructor | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugFunctionObject::CreateObjectNoConstructor
helpviewer_keywords:
- IDebugFunctionObject::CreateObjectNoConstructor method
ms.assetid: 4e2bd6d5-f4bd-4c10-a998-3db451c9a0c8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 9e6225099b3b88cbbbb73884cbd93be4f7976e50
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66200841"
---
# <a name="idebugfunctionobjectcreateobjectnoconstructor"></a>IDebugFunctionObject::CreateObjectNoConstructor
Vytvoří objekt se žádný konstruktor.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT CreateObjectNoConstructor( 
   IDebugField*   pClassObject,
   IDebugObject** ppObject
);
```

```csharp
int CreateObjectNoConstructor(
   IDebugField      pClassField,
   out IDebugObject ppObject
);
```

## <a name="parameters"></a>Parametry
`pClassObject`\
[in] [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objekt reprezentující typ objektu, který se má vytvořit.

`ppObject`\
[out] Vrátí [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) představující nově vytvořený objekt.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Volejte tuto metodu za účelem vytvoření objektu, který představuje instanci struktury nebo komplexní typ (která nevyžaduje konstruktor), který je parametr funkce, která je reprezentována [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) rozhraní.

 Pokud parametr objektu vyžaduje konstruktor, zavolejte [CreateObject](../../../extensibility/debugger/reference/idebugfunctionobject-createobject.md) metody.

## <a name="see-also"></a>Viz také:
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)
- [CreateObject](../../../extensibility/debugger/reference/idebugfunctionobject-createobject.md)