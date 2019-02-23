---
title: IDebugCoreServer3::DiagnoseWebDebuggingError | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCoreServer3::DiagnoseWebDebuggingError
helpviewer_keywords:
- IDebugCoreServer3::DiagnoseWebDebuggingError
ms.assetid: 8c4570ca-ae55-42f2-bbaa-8d8e75d2fa19
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8173283adadd1290bdd83bf5f6810622efbff959
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56722938"
---
# <a name="idebugcoreserver3diagnosewebdebuggingerror"></a>IDebugCoreServer3::DiagnoseWebDebuggingError
Nepovedlo se pokusí zjistit, proč auto-attach.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT DiagnoseWebDebuggingError(
   LPCWSTR pszUrl
);
```

```csharp
int DiagnoseWebDebuggingError(
   string pszUrl
);
```

#### <a name="parameters"></a>Parametry
 `pszUrl`

 [in] Není v současné době nepoužívá; musí být vždy nastavená na hodnotu null.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Tady jsou další typické návratové kódy:

|Kód|Popis|
|----------|-----------------|
|`S_WEBDBG_UNABLE_TO_DIAGNOSE`|Nelze určit, proč se nepodařilo spustit ladění vzdáleném serveru.|
|`S_WEBDBG_DEBUG_VERB_BLOCKED`|Nelze ladit na vzdáleném serveru, pravděpodobně z důvodu nedostatečných oprávnění nebo proto, že není povolen příkaz DEBUG.|
|`E_WEBDBG_DEBUG_VERB_BLOCKED`|Webový server byl uzamčen a blokuje slovo DEBUG, která jsou nutná pro povolení ladění.|

## <a name="see-also"></a>Viz také
- [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)