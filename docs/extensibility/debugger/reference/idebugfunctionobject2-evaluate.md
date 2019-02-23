---
title: IDebugFunctionObject2::Evaluate | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugFunctionObject2::Evaluate
ms.assetid: bc54c652-904b-4297-a6db-faa329684881
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 441126724c78c2045e3e870fcdf7baa23f9149c3
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56708781"
---
# <a name="idebugfunctionobject2evaluate"></a>IDebugFunctionObject2::Evaluate
Volá funkci a vrátí výslednou hodnotu jako objekt.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Evaluate (
   IDebugObject** ppParams,
   DWORD          dwParams,
   DWORD          dwEvalFlags,
   DWORD          dwTimeout,
   IDebugObject** ppResult
);
```

```csharp
int Evaluate (
   IDebugObject     ppParams,
   uint             dwParams,
   uint             dwEvalFlags,
   uint             dwTimeout,
   out IDebugObject ppResult
);
```

#### <a name="parameters"></a>Parametry
 `ppParams`

 [in] Pole [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objekty, které představují vstupní parametry. Každý z těchto parametrů bylo vytvořeno s použitím jedné z metod vytvořit v tomto rozhraní.

 `dwParams`

 [in] Počet parametrů `ppParams` pole.

 `dwEvalFlags`

 [in] Kombinace příznaků z [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) výčet určující, jak se má provést vyhodnocení.

 `dwTimeout`

 [in] Určuje maximální dobu (v milisekundách) čekání před návratem z této metody. Použití **NEKONEČNÉ** čekat po neomezenou dobu.

 `ppResult`

 [out] Vrátí **IDebugObject** , který představuje hodnotu funkce jako objekt.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDebugFunctionObject2](../../../extensibility/debugger/reference/idebugfunctionobject2.md)