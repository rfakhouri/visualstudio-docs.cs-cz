---
title: IDebugEnumField::GetValueFromStringCaseInsensitive | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugEnumField::GetValueFromStringCaseInsensitive
helpviewer_keywords:
- IDebugEnumField::GetValueFromStringCaseInsensitive method
ms.assetid: ef95b38e-d9b2-4fb5-a166-7c2e14641dc7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4d9dd38fb36a1b48dda5f47ec716964bf1a576da
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53839979"
---
# <a name="idebugenumfieldgetvaluefromstringcaseinsensitive"></a>IDebugEnumField::GetValueFromStringCaseInsensitive
Tato metoda používá k vrácení hodnoty přidružené k názvu konstanta výčtu hledat bez tohoto rozlišování.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetValueFromStringCaseInsensitive(  
   LPCOLESTR  pszValue,  
   ULONGLONG* pvalue  
);  
```  
  
```csharp  
int GetValueFromStringCaseInsensitive(  
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
 Tato metoda je velká a malá písmena. Pokud malá a velká písmena vyhledávání je potřeba (například v jazyce například C++, kde názvy jsou malá a velká písmena), použijte [GetValueFromString](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstring.md).  
  
## <a name="see-also"></a>Viz také  
 [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)   
 [GetValueFromString](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstring.md)