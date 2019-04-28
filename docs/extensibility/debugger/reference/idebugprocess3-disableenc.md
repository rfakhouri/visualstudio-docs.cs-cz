---
title: IDebugProcess3::DisableENC | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess3::DisableENC
helpviewer_keywords:
- IDebugProcess3::DisableENC
ms.assetid: cffdbdac-4d76-4aeb-aa55-5d0410db99f1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2cc26c9d2dae65d8bab0126be5a62b144ebf42b7
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63413287"
---
# <a name="idebugprocess3disableenc"></a>IDebugProcess3::DisableENC
Tato metoda explicitně zakáže upravit a pokračovat na tento proces (a všechny programy obsahuje). Dodavatel port. Tento vlastní port byste vždy vrátí `E_NOTIMPL`.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT DisableENC(
   EncUnavailableReason reason
);
```

```csharp
   EncUnavailableReason reason
);
```

#### <a name="parameters"></a>Parametry
 `reason`

 [in] Hodnota z [EncUnavailableReason](../../../extensibility/debugger/reference/encunavailablereason.md) výčtu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

> [!NOTE]
> Dodavatel port. Tento vlastní port byste vždy vrátí `E_NOTIMPL`.

## <a name="remarks"></a>Poznámky
 Jednou upravit a pokračovat je zakázaná pro proces, ho můžete znovu povolit pouze restartování procesu.

## <a name="see-also"></a>Viz také
- [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)
- [EncUnavailableReason](../../../extensibility/debugger/reference/encunavailablereason.md)