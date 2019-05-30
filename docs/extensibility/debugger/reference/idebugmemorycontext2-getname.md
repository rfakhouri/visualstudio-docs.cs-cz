---
title: IDebugMemoryContext2::GetName | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMemoryContext2::GetName
helpviewer_keywords:
- IDebugMemoryContext2::GetName method
- GetName method
ms.assetid: 8c212556-7d9e-4d68-b2a9-8212f50d0287
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: ee8dd65a3bcaef7fd5a23da6c2a5f9c21a4838af
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66346997"
---
# <a name="idebugmemorycontext2getname"></a>IDebugMemoryContext2::GetName
Načte uživatele zobrazitelné název pro tento kontext.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetName( 
   BSTR* pbstrName
);
```

```csharp
int GetName(
   out string pbstrName
);
```

## <a name="parameters"></a>Parametry
`pbstrName`\
[out] Vrátí název kontextu paměti.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Název místní paměti se obvykle nepoužívá.

## <a name="see-also"></a>Viz také:
- [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)