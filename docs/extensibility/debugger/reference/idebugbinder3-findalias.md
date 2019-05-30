---
title: IDebugBinder3::FindAlias | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBinder3::FindAlias
helpviewer_keywords:
- IDebugBinder3::FindAlias method
ms.assetid: b8333701-2718-4983-8513-0875fb7cb730
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 8387a3302395d6e25c2b00dd360286e533531168
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66344426"
---
# <a name="idebugbinder3findalias"></a>IDebugBinder3::FindAlias
Tato metoda vyhledá alias, název. Všechny aliasy to bude hledat v programu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT FindAlias(
   LPCOLESTR     pcstrName,
   IDebugAlias** ppAlias
);
```

```csharp
int FindAlias(
   string          pcstrName,
   out IDebugAlias ppAlias
);
```

## <a name="parameters"></a>Parametry
`pcstrName`\
[in] Název alias se najít.

`ppAlias`\
[out] Alias najít (pokud existuje) reprezentována [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md) rozhraní.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` (Pokud není nalezena alias) nebo kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda inicializuje cílového objektu na hodnotu null, před voláním; potom testy pro hodnotu null, následně k určení, zda byl nalezen alias.

## <a name="see-also"></a>Viz také:
- [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)
- [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)