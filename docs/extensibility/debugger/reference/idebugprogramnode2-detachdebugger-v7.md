---
title: IDebugProgramNode2::DetachDebugger_V7 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProgramNode2::DetachDebugger
helpviewer_keywords:
- IDebugProgramNode2::DetachDebugger
- IDebugProgramNode2::DetachDebugger_V7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8393eb7bc712de28e2378a9ad09081efe76eca6b
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54933942"
---
# <a name="idebugprogramnode2detachdebuggerv7"></a>IDebugProgramNode2::DetachDebugger_V7

> [!Note]
> ZASTARALÉ. NEPOUŽÍVEJTE.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT DetachDebugger_V7 (
   void 
);
```

```csharp
int DetachDebugger_V7 ();
```

## <a name="return-value"></a>Návratová hodnota

Implementace by měla vždy vrátit `E_NOTIMPL`.

## <a name="remarks"></a>Poznámky

> [!WARNING]
> Od verze Visual Studio 2005, tato metoda se už nepoužívá a by měl vždy vrátit `E_NOTIMPL`.

Tato metoda je volána, když ladicí program se neočekávaně ukončí. Když tato metoda je volána, DE měla pokračovat program, jakoby z něj odpojit uživatele. Poslat žádné další události ladění. Program by měl být ve stavu, ve kterém je připojitelná z jiné instance ladicího programu.

## <a name="see-also"></a>Viz také

[IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)