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
ms.openlocfilehash: 58675b5f9e963ec416a2c8586375a94f9c06ae69
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62877520"
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

#### <a name="parameters"></a>Parametry
 `pcstrName`

 [in] Název alias se najít.

 `ppAlias`

 [out] Alias najít (pokud existuje) reprezentována [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md) rozhraní.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` (Pokud není nalezena alias) nebo kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda inicializuje cílového objektu na hodnotu null, před voláním; potom testy pro hodnotu null, následně k určení, zda byl nalezen alias.

## <a name="see-also"></a>Viz také
- [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)
- [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)