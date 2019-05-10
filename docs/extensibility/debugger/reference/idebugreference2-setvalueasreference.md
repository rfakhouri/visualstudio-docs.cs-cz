---
title: IDebugReference2::SetValueAsReference | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugReference2::SetValueAsReference
helpviewer_keywords:
- IDebugReference2::SetValueAsReference
ms.assetid: 94a545d2-16b9-45e9-b2e7-4e49ff90aad0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 0fc6e2fee354d6dcc76676bf02d4ed88e1799f26
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65458649"
---
# <a name="idebugreference2setvalueasreference"></a>IDebugReference2::SetValueAsReference
Nastaví hodnotu odkazu z jiného odkazu. Vyhrazeno pro budoucí použití.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT SetValueAsReference ( 
   IDebugReference2** rgpArgs,
   DWORD              dwArgCount,
   IDebugReference2*  pValue,
   DWORD              dwTimeout
);
```

```cpp
int SetValueAsReference ( 
   IDebugReference2[] rgpArgs,
   uint               dwArgCount,
   IDebugReference2   pValue,
   uint               dwTimeout
);
```

## <a name="parameters"></a>Parametry
 `rgpArgs`\

 [in] Pole [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) objekty sloužící k určení, jak nastavit hodnotu odkazu.

 `dwArgCount`\

 [in] Počet odkazů v poli.

 `pValue`\

 [in] [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) objekt, ze kterého chcete nastavit hodnotu vlastnosti.

 `dwTimeout`\

 [in] Maximální doba v milisekundách pro čekání před návratem z této metody. Použití `INFINITE` čekat po neomezenou dobu.

## <a name="return-value"></a>Návratová hodnota
 Vždy vrátí `E_NOTIMPL`.

## <a name="see-also"></a>Viz také:
- [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)