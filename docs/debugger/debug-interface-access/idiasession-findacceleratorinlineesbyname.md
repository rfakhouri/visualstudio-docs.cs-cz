---
title: IDiaSession::findAcceleratorInlineesByName | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: e203e5c2-6563-43fa-be56-3063955043ab
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fb3caa5574605864a0dd16b59b6f451530b8e631
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62827784"
---
# <a name="idiasessionfindacceleratorinlineesbyname"></a>IDiaSession::findAcceleratorInlineesByName
Vrátí výčet symbolů pro vložené rámce odpovídající názvu funkce zadány jako vložené.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT findAcceleratorInlineeLinesByName ( 
   LPCOLESTR             name,
   DWORD                 option,
   IDiaEnumSymbols**     ppResult
);
```

#### <a name="parameters"></a>Parametry
 `name`

[in] Název funkce inlinee chcete prohledat.

 `option`

[in] Možnosti hledání název se použije při vyhledávání vložený snímků, které odpovídají `name`. Další informace najdete v tématu [namesearchoptions – výčet](../../debugger/debug-interface-access/namesearchoptions.md).

 `ppResult`

[out] Ukazatel `IDiaEnumSymbols` ukazatel rozhraní, který je inicializován s výsledkem.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Tato funkce hledá inlinees pouze v rámci akcelerátoru zástupné procedury funkcí. Nativní C++ postup záznamů je ignorován.

## <a name="see-also"></a>Viz také
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)