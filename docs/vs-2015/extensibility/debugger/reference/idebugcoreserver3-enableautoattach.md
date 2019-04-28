---
title: IDebugCoreServer3::EnableAutoAttach | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCoreServer3::EnableAutoAttach
helpviewer_keywords:
- IDebugCoreServer3::EnableAutoAttach
ms.assetid: 06aa633b-263b-4e08-8844-9a52d5120b94
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 45362c9456b99d6cec0af01dcb29844d02363a27
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62569774"
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

#### <a name="parameters"></a>Parametry
 `rgguidSpecificEngines`

 [in] Pole identifikátorů GUID pro každý ladicí stroj označit jako automatické připojení.

 `celtSpecificEngines`

 [in] Počet modulů, zadaný v `rgguidSpecificEngines`.

 `pszStartPageUrl`

 [in] Počáteční adresa URL má použít při připojení automaticky.

 `pbstrSessionID`

 [out] ID relace, která byla automaticky připojen.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Jeden kód chyby: `E_AUTO_ATTACH_NOT_REGISTERED`, což znamená, že objekt pro vytváření tříd auto-attach nebyl registrován.

## <a name="remarks"></a>Poznámky
 Když se spustí program přidružený k zadané adrese URL, zadaný ladicími stroji automaticky zahájení a připojené.

## <a name="see-also"></a>Viz také
- [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)