---
title: IDebugModule2::ReloadSymbols_Deprecated | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugModule2::ReloadSymbols
helpviewer_keywords:
- IDebugModule2::ReloadSymbols method
ms.assetid: 0f9f0133-7d58-4cd9-a6ca-1141e095749d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: cc5651a85ccc89a8a084c608e3fc698aa326e07c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62918831"
---
# <a name="idebugmodule2reloadsymbolsdeprecated"></a>IDebugModule2::ReloadSymbols_Deprecated
ZASTARALÉ. NEPOUŽÍVEJTE. Znovu načte symboly pro tento modul.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT ReloadSymbols( 
   LPCOLESTR pszUrlToSymbols,
   BSTR*     pbstrDebugMessage
);
```

```csharp
int ReloadSymbols( 
   string     pszUrlToSymbols,
   out string pbstrDebugMessage
);
```

#### <a name="parameters"></a>Parametry
 `pszUrlToSymbols`

 [in] Cesta k úložišti symbolů.

 `pbstrDebugMessage`

 [out] Vrátí informačních zpráv, jako je například stav nebo chybové zprávy, který se zobrazí napravo od názvu modulu v okně moduly.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Ladicí stroj by měla vždy vrátit `E_FAIL`.

## <a name="remarks"></a>Poznámky
 Tato metoda se už nepodporuje. Implementace [LoadSymbols](../../../extensibility/debugger/reference/idebugmodule3-loadsymbols.md) metoda místo.

## <a name="see-also"></a>Viz také
- [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)
- [LoadSymbols](../../../extensibility/debugger/reference/idebugmodule3-loadsymbols.md)