---
title: IDebugBinder3::FindAlias | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBinder3::FindAlias
helpviewer_keywords:
- IDebugBinder3::FindAlias method
ms.assetid: b8333701-2718-4983-8513-0875fb7cb730
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 2b0185b0c3f7f26cfe9ffa8806c5049af323c517
ms.sourcegitcommit: 77b4ca625674658d5c5766e684fa0e2a07cad4da
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/14/2019
ms.locfileid: "65614944"
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