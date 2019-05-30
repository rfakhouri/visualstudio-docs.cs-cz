---
title: IDebugObject2::IsEncOutdated | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject2::IsEncOutdated
helpviewer_keywords:
- IDebugObject2::IsEncOutdated method
ms.assetid: d3a8c02d-895b-478c-9957-d663130f308e
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 9b2d26b49f3d2597e12e11a323a9281bd5c676fa
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66317417"
---
# <a name="idebugobject2isencoutdated"></a>IDebugObject2::IsEncOutdated
Tato metoda určuje, zda funkce upravit a pokračovat stav tohoto objektu nebo jeho nadřazeného kontejneru je zastaralá. Vyhodnocovací filtr vlastních výrazů neimplementuje tuto metodu a vždy vrátí `E_NOTIMPL`.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT IsEncOutdated(
   BOOL* pfEncOutdated
);
```

```csharp
int IsEncOutdated(
   out int pfEncOutdated
);
```

## <a name="parameters"></a>Parametry
`pfEncOutdated`\
[out] Nenulová (`TRUE`) Pokud státu upravit a pokračovat není aktuální, nula (`FALSE`) Pokud není.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

> [!NOTE]
> Vyhodnocovací filtr vlastních výrazů by měla vždy vrátit `E_NOTIMPL`.

## <a name="see-also"></a>Viz také:
- [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)