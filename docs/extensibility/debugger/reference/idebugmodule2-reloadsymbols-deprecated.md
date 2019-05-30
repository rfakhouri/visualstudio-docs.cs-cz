---
title: IDebugModule2::ReloadSymbols_Deprecated | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugModule2::ReloadSymbols
helpviewer_keywords:
- IDebugModule2::ReloadSymbols method
ms.assetid: 0f9f0133-7d58-4cd9-a6ca-1141e095749d
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 635e305c0dd88d72017048da6353f813fcc46406
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66323961"
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

## <a name="parameters"></a>Parametry
`pszUrlToSymbols`\
[in] Cesta k úložišti symbolů.

`pbstrDebugMessage`\
[out] Vrátí informačních zpráv, jako je například stav nebo chybové zprávy, který se zobrazí napravo od názvu modulu v okně moduly.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Ladicí stroj by měla vždy vrátit `E_FAIL`.

## <a name="remarks"></a>Poznámky
 Tato metoda se už nepodporuje. Implementace [LoadSymbols](../../../extensibility/debugger/reference/idebugmodule3-loadsymbols.md) metoda místo.

## <a name="see-also"></a>Viz také:
- [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)
- [LoadSymbols](../../../extensibility/debugger/reference/idebugmodule3-loadsymbols.md)