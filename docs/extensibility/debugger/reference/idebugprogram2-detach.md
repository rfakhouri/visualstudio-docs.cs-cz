---
title: IDebugProgram2::Detach | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2::Detach
helpviewer_keywords:
- IDebugProgram2::Detach
ms.assetid: 5e8d88b0-a8d4-4746-88c0-ad332ee73f33
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e15f617978f0e3ffb6e09f0a55cdf20d040c13d2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62870509"
---
# <a name="idebugprogram2detach"></a>IDebugProgram2::Detach
Odpojí ladicí stroj z programu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Detach( 
   void 
);
```

```csharp
int Detach();
```

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Odpojit program bude nadále spuštěn, ale je již součástí relace ladění. Žádné další události ladicí program se posílají až odpojit ladicí stroj.

## <a name="see-also"></a>Viz také
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)