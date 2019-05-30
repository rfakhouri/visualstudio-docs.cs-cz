---
title: IDebugPointerObject::GetBytes | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPointerObject::GetBytes
helpviewer_keywords:
- IDebugPointerObject::GetBytes method
ms.assetid: e986c188-87fb-4b51-86e9-ee6a0035bdab
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 247e1ff4c934ae581c7a0224c8f8cba8d4e9d946
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66308871"
---
# <a name="idebugpointerobjectgetbytes"></a>IDebugPointerObject::GetBytes
Získá hodnotu, na který je odkazováno jako řadu bajtů po sobě jdoucích.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetBytes( 
   DWORD  dwStart,
   DWORD  dwCount,
   BYTE*  pBytes,
   DWORD* pdwBytes
);
```

```csharp
int GetBytes(
   uint       dwStart,
   uint       dwCount,
   out byte[] pBytes,
   out uint   pdwBytes
);
```

## <a name="parameters"></a>Parametry
`dwStart`\
[in] Posun v bajtech od začátku objekt odkazoval.

`dwCount`\
[in] Počet bajtů k načtení.

`pBytes`\
[out v] Pole, které se vyplní hodnotou jako řadu bajtů po sobě jdoucích, spuštění na dané pozici z objektu odkazoval.

`pdwBytes`\
[out] Vrátí počet bajtů ve skutečnosti načíst.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda se používá, pokud ukazatel reprezentovaný tímto objektem [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md) odkazuje na primitivní typ nebo jednoduchý pole primitivní typy (to znamená, pole, které může být reprezentován jednoduché pořadí bajtů).

## <a name="see-also"></a>Viz také:
- [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)
- [SetBytes](../../../extensibility/debugger/reference/idebugpointerobject-setbytes.md)