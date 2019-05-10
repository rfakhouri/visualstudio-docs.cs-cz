---
title: IDebugReference2::SetValueAsString | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugReference2::SetValueAsString
helpviewer_keywords:
- IDebugReference2::SetValueAsString
ms.assetid: 9a508ced-fd54-44f5-bb42-ec15c80384d7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 022712c0be8dfb569ba097bc4a86f8b02de93633
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65457413"
---
# <a name="idebugreference2setvalueasstring"></a>IDebugReference2::SetValueAsString
Nastaví hodnotu odkazu z řetězce. Vyhrazeno pro budoucí použití.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT SetValueAsString ( 
   LPCOLESTR pszValue,
   DWORD     dwRadix,
   DWORD     dwTimeout
);
```

```csharp
int SetValueAsString ( 
   string pszValue,
   uint   dwRadix,
   uint   dwTimeout
);
```

## <a name="parameters"></a>Parametry
 `pszValue`\

 [in] Hodnota jako řetězec.

 `dwRadix`\

 [in] Základ, který se má použít v jakékoli číselné informace o formátování.

 `dwTimeout`\

 [in] Maximální doba v milisekundách pro čekání před návratem z této metody. Použití `INFINITE` čekat po neomezenou dobu.

## <a name="return-value"></a>Návratová hodnota
 Vždy vrátí `E_NOTIMPL`.

## <a name="see-also"></a>Viz také:
- [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)