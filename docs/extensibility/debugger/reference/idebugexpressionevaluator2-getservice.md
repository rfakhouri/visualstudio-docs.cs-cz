---
title: IDebugExpressionEvaluator2::GetService | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugExpressionEvaluator2::GetService
- GetService
ms.assetid: f8988a9e-9d18-42af-84a7-55f41e9adf63
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 42a4027b4153f262eb8164a915f229f04c7cbed4
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66325553"
---
# <a name="idebugexpressionevaluator2getservice"></a>IDebugExpressionEvaluator2::GetService
Načte službu objekt dle jejich jedinečného identifikátoru.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetService (
   GUID        uid,
   IUnknown ** ppService
);
```

```csharp
int GetService (
   Guid       uid,
   out object ppService
);
```

## <a name="parameters"></a>Parametry
`uid`\
[in] Jedinečný identifikátor služby k načtení.

`ppService`\
[out] Vrátí objekt, který představuje službu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 To mohou být spotřebovány vyhodnocení výrazu třetích stran získat services z jiného vyhodnocovací filtr výrazů. Například tato metoda může získat rozhraní pro služby visualizéru z výchozí vyhodnocovací filtr výrazů. Je nepravděpodobné, že je nutné implementovat toto rozhraní vyhodnocovače výrazů třetích stran.

## <a name="see-also"></a>Viz také:
- [IDebugExpressionEvaluator2](../../../extensibility/debugger/reference/idebugexpressionevaluator2.md)