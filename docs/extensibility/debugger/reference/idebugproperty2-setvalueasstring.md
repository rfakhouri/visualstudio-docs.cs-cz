---
title: IDebugProperty2::SetValueAsString | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProperty2::SetValueAsString
helpviewer_keywords:
- IDebugProperty2::SetValueAsString
ms.assetid: 9e6a5054-41b7-4223-b509-b93689d366a5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6acc3c0c0ec271793832783b2fb7eb9f2ff2309a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56686480"
---
# <a name="idebugproperty2setvalueasstring"></a>IDebugProperty2::SetValueAsString
Nastaví hodnotu vlastnosti ze zadaného řetězce.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT SetValueAsString ( 
   LPCOLESTR pszValue,
   UINT      nRadix,
   DWORD     dwTimeout
);
```

```csharp
int SetValueAsString ( 
   string pszValue,
   uint   nRadix,
   uint   dwTimeout
);
```

#### <a name="parameters"></a>Parametry
 `pszValue`

 [in] Řetězec obsahující hodnotu, která se má nastavit.

 `nRadix`

 [in] Základ, který se má použít při interpretaci jakékoli číselné informace. To může být 0 pokusí automaticky zjistit základ číselné soustavy.

 `dwTimeout`

 [in] Určuje maximální dobu (v milisekundách) čekání před návratem z této metody. Použití `INFINITE` čekat po neomezenou dobu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. V následující tabulce jsou uvedeny další možné hodnoty.

|Hodnota|Popis|
|-----------|-----------------|
|`E_SETVALUE_VALUE_CANNOT_BE_SET`|Řetězec se nedá převést na hodnotu vlastnosti nebo nelze nastavit hodnotu vlastnosti.|
|`E_SETVALUE_VALUE_IS_READONLY`|Vlastnost je jen pro čtení.|

## <a name="see-also"></a>Viz také
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)