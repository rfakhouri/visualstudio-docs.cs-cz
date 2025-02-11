---
title: IDebugCoreServer3::EnableAutoAttach | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCoreServer3::EnableAutoAttach
helpviewer_keywords:
- IDebugCoreServer3::EnableAutoAttach
ms.assetid: 06aa633b-263b-4e08-8844-9a52d5120b94
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 9eb8beed7f32e9c6fb64212f73a41a35544259bb
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66326974"
---
# <a name="idebugcoreserver3enableautoattach"></a>IDebugCoreServer3::EnableAutoAttach
Umožňuje automatické připojení pro zadanou ladicí stroj.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT EnableAutoAttach(
   GUID*     rgguidSpecificEngines,
   DWORD     celtSpecificEngines,
   LPCOLESTR pszStartPageUrl,
   BSTR*     pbstrSessionId
);
```

```csharp
int EnableAutoAttach(
   Guid[]     rgguidSpecificEngines,
   uint       celtSpecificEngines,
   string     pszStartPageUrl,
   out string pbstrSessionId
);
```

## <a name="parameters"></a>Parametry
`rgguidSpecificEngines`\
[in] Pole identifikátorů GUID pro každý ladicí stroj označit jako automatické připojení.

`celtSpecificEngines`\
[in] Počet modulů, zadaný v `rgguidSpecificEngines`.

`pszStartPageUrl`\
[in] Počáteční adresa URL má použít při připojení automaticky.

`pbstrSessionID`\
[out] ID relace, která byla automaticky připojen.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Jeden kód chyby: `E_AUTO_ATTACH_NOT_REGISTERED`, což znamená, že objekt pro vytváření tříd auto-attach nebyl registrován.

## <a name="remarks"></a>Poznámky
 Když se spustí program přidružený k zadané adrese URL, zadaný ladicími stroji automaticky zahájení a připojené.

## <a name="see-also"></a>Viz také:
- [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)