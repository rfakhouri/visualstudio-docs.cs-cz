---
title: IDebugFunctionObject2::CreateObject | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugFunctionObject2::CreateObject
- CreateObject
ms.assetid: 148de615-941e-4b64-ab11-75b692aae465
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 87d1c2cd71b57136e26a2bc30004547dc4b8dee5
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66313414"
---
# <a name="idebugfunctionobject2createobject"></a>IDebugFunctionObject2::CreateObject
Vytvoří objekt, který používá konstruktor daným nastavením příznaků hodnocení a hodnotu časového limitu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT CreateObject (
   IDebugFunctionObject* pConstructor,
   DWORD                 dwArgs,
   IDebugObject*         pArgs[],
   DWORD                 dwEvalFlags,
   DWORD                 dwTimeout,
   IDebugObject**        ppObject
);
```

```csharp
int CreateObject (
   IDebugFunctionObject pConstructor,
   uint                 dwArgs,
   IDebugObject[]       pArgs,
   uint                 dwEvalFlags,
   uint                 dwTimeout,
   out IDebugObject**   ppObject
);
```

## <a name="parameters"></a>Parametry
`pConstructor`\
[in] [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) objekt, který reprezentuje konstruktor objektu, který se má vytvořit.

`dwArgs`\
[in] Počet parametrů `pArg` pole. Představuje počet parametry předané do konstruktoru.

`pArgs`\
[in] Pole [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objekty, které představují parametry předané do konstruktoru.

`dwEvalFlags`\
[in] Kombinace příznaků z [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) výčet určující, jak se má provést vyhodnocení.

`dwTimeout`\
[in] Maximální doba v milisekundách pro čekání před návratem z této metody. Použití **NEKONEČNÉ** čekat po neomezenou dobu.

`ppObject`\
[out] Vrátí **IDebugObject** představující nově vytvořený objekt.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Volejte tuto metodu za účelem vytvoření objektu, který představuje instance třídy nebo jiné komplexní typ, který vyžaduje konstruktor, který je parametr.

## <a name="see-also"></a>Viz také:
- [IDebugFunctionObject2](../../../extensibility/debugger/reference/idebugfunctionobject2.md)