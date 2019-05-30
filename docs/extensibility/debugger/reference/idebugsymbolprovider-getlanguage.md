---
title: IDebugSymbolProvider::GetLanguage | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugSymbolProvider::GetLanguage
helpviewer_keywords:
- IDebugSymbolProvider::GetLanguage method
ms.assetid: e4142183-3d8b-418f-907f-4ee4c753d8ce
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: dfa11a1df6460c08431d7b23fabe5d94674baad2
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66347604"
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