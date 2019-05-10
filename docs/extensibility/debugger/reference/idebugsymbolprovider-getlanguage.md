---
title: IDebugSymbolProvider::GetLanguage | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugSymbolProvider::GetLanguage
helpviewer_keywords:
- IDebugSymbolProvider::GetLanguage method
ms.assetid: e4142183-3d8b-418f-907f-4ee4c753d8ce
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 071dac72e39a3cce5b0b17dc9e401b9072efda6a
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2019
ms.locfileid: "65224054"
---
# <a name="idebugsymbolprovidergetlanguage"></a>IDebugSymbolProvider::GetLanguage
Tato metoda načte jazyk, ve kterém byla použita pro kompilaci kódu na adrese ladění.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetLanguage( 
   IDebugAddress* pAddress,
   GUID*          pguidLanguage,
   GUID*          pguidLanguageVendor
);
```

```csharp
int GetLanguage(
   IDebugAddress pAddress,
   out Guid      pguidLanguage,
   out Guid      pguidLanguageVendor
);
```

## <a name="parameters"></a>Parametry
 `pAddress`\

 [in] Adresa objektu reprezentována [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) rozhraní.

 `pguidLanguage`\

 [out] Vrátí `GUID` , který určuje jazyk.

 `pguidLanguageVendor`\

 [out] Vrátí `GUID` , který určuje jazyk dodavatele.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Ladicí stroj volá tuto metodu za účelem získání informací, že je potřeba vybrat vyhodnocovací filtr výrazů správné.

## <a name="see-also"></a>Viz také:
- [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)
- [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)