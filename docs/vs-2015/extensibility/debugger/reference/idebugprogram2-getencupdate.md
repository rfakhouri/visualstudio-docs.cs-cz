---
title: IDebugProgram2::GetENCUpdate | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2::GetENCUpdate
helpviewer_keywords:
- IDebugProgram2::GetENCUpdate
ms.assetid: 9832aac8-6320-4fd8-91dd-2a0852febb00
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ac976232f2e92a7af1c8e0fabb7907e7164ba08a
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63386098"
---
# <a name="idebugprogram2getencupdate"></a>IDebugProgram2::GetENCUpdate
Tato metoda načte upravit a pokračovat (ENC) aktualizace pro tento program. Vždy vrátí hodnotu vlastního ladicího stroje `E_NOTIMPL`.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetENCUpdate( 
   IUnknown** ppUpdate
);
```

```csharp
int GetENCUpdate(
   out object ppUpdate
);
```

#### <a name="parameters"></a>Parametry
 `ppUpdate`

 [out] Vrátí interní rozhraní, který slouží k aktualizaci této aplikace.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

> [!NOTE]
> Vždy by měl vrátit vlastního ladicího stroje `E_NOTIMPL`.

## <a name="see-also"></a>Viz také
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)