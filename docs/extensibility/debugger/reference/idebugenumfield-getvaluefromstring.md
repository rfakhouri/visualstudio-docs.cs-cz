---
title: IDebugEnumField::GetValueFromString | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEnumField::GetValueFromString
helpviewer_keywords:
- IDebugEnumField::GetValueFromString method
ms.assetid: 1ef8ac5e-a3e0-4078-b876-7f5615aedcbb
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e714e6b2028605eb9c820f904cedf9ed4c23eab8
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56716022"
---
# <a name="idebugenumfieldgetvaluefromstring"></a>IDebugEnumField::GetValueFromString
Tato metoda vrátí hodnotu přidruženou k názvu konstanta výčtu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetValueFromString(
   LPCOLESTR  pszValue,
   ULONGLONG* pvalue
);
```

```csharp
int GetValueFromString(
   string    pszValue,
   out ulong pValue
);
```

#### <a name="parameters"></a>Parametry
 `pszValue`

 [in] Řetězec určující název, který má být získána hodnota. Všimněte si, že pro C++, toto je řetězec širokých znaků.

 `pValue`

 [out] Vrátí související číselnou hodnotu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE`, pokud název není součástí výčtu nebo kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda je velká a malá písmena. Hledat bez tohoto rozlišování potřeby (například v jazyce jako například Visual Basic, kde názvy nejsou malá a velká písmena) a použít [GetValueFromStringCaseInsensitive](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstringcaseinsensitive.md).

## <a name="see-also"></a>Viz také
- [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)
- [GetValueFromStringCaseInsensitive](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstringcaseinsensitive.md)