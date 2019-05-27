---
title: IDebugEvent2::GetAttributes | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEvent2::GetAttributes
helpviewer_keywords:
- IDebugEvent2::GetAttributes
ms.assetid: 2ac5b5fb-da17-43f7-811a-313f677e60d7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: d374086ebae3546346f442f782c02a145ca18972
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66199905"
---
# <a name="idebugevent2getattributes"></a>IDebugEvent2::GetAttributes
Získá atributy pro tuto událost ladění.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetAttribute( 
   DWORD* pdwAttrib
);
```

```csharp
int GetAttribute( 
   out uint pdwAttrib
);
```

## <a name="parameters"></a>Parametry
`pdwAttrib`\
[out] Kombinace příznaků z [EVENTATTRIBUTES](../../../extensibility/debugger/reference/eventattributes.md) výčtu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) rozhraní je společné pro všechny události. Tato metoda popisuje typ události. například je událost synchronní nebo asynchronní a je to událostí ukončení.

## <a name="see-also"></a>Viz také:
- [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)
- [EVENTATTRIBUTES](../../../extensibility/debugger/reference/eventattributes.md)