---
title: IDebugExpressionEvaluator2::GetService | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugExpressionEvaluator2::GetService
- GetService
ms.assetid: f8988a9e-9d18-42af-84a7-55f41e9adf63
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ac6f73e31e7e15a2ffd86e2d969f98a686fbd004
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56677692"
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

#### <a name="parameters"></a>Parametry
 `uid`

 [in] Jedinečný identifikátor služby k načtení.

 `ppService`

 [out] Vrátí objekt, který představuje službu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 To mohou být spotřebovány vyhodnocení výrazu třetích stran získat services z jiného vyhodnocovací filtr výrazů. Například tato metoda může získat rozhraní pro služby visualizéru z výchozí vyhodnocovací filtr výrazů. Je nepravděpodobné, že je nutné implementovat toto rozhraní vyhodnocovače výrazů třetích stran.

## <a name="see-also"></a>Viz také
- [IDebugExpressionEvaluator2](../../../extensibility/debugger/reference/idebugexpressionevaluator2.md)