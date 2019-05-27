---
title: IDebugModOpt::GetModOpts | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugModOpt::GetModOpts
- GetModOpts
ms.assetid: cb513fa9-d521-4a65-b968-f55f53a368df
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 1c27c8a2a0e755fda5afa806657e918c7e7c0109
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66203120"
---
# <a name="idebugmodoptgetmodopts"></a>IDebugModOpt::GetModOpts
Načte seznam volitelné modifikátory.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetModOpts(
   ULONG  celt,
   BSTR*  rgelt,
   ULONG* pceltFetched
);
```

```csharp
int GetModOpts(
   uint         celt,
   out string[] rgelt,
   ref uint     pceltFetched
);
```

## <a name="parameters"></a>Parametry
`celt`\
[in] Počet prvků který se má vrátit.

`rgelt`\
[out] Vrátí pole obsahující parametry.

`pceltFetched`\
[out v] Počet prvků vrácených v `rgelt` pole.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také:
- [IDebugModOpt](../../../extensibility/debugger/reference/idebugmodopt.md)