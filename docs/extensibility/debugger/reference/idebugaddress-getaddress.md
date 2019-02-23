---
title: IDebugAddress::GetAddress | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugAddress::GetAddress
helpviewer_keywords:
- IDebugAddress:GetAddress method
ms.assetid: 2590387b-5d36-4116-9a75-737957b8898e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1cff380759163a38129b92f07752e72904f6bbaf
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56684452"
---
# <a name="idebugaddressgetaddress"></a>IDebugAddress::GetAddress
Vrací strukturu popisující objekt a jeho umístění v rámci jeho rozsah nebo kontejneru.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetAddress (
   DEBUG_ADDRESS * pAddress
);
```

```csharp
int GetAddress(
   DEBUG_ADDRESS[] pAddress
);
```

#### <a name="parameters"></a>Parametry
 `pAddress`

 [out v] A [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) struktura, která je vyplněna touto metodou.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) struktura je předaný této metodě, která ji doplní pomocí příslušné informace. Způsob interpretace těchto informací závisí na typ vrácené informace a samotná obslužná rutina symbol. Zobrazit [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) další podrobnosti.

## <a name="see-also"></a>Viz také
- [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)