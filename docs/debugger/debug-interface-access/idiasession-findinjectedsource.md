---
title: Idiasession::findinjectedsource – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findInjectedSource method
ms.assetid: 907531b6-1ef8-4153-986d-b72611a1632d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4bef903304e3892284fc38d9e2b2367ebfe650f4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62839339"
---
# <a name="idiasessionfindinjectedsource"></a>IDiaSession::findInjectedSource
Načte seznam zdrojů, který je umístěný do úložiště symbolů podle poskytovatele atributu ani jiné součásti procesu kompilace.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT findInjectedSource ( 
   LPCOLESTR                 srcFile,
   IDiaEnumInjectedSources** ppResult
);
```

#### <a name="parameters"></a>Parametry
 srcFile

[in] Název zdrojového souboru, který chcete vyhledat.

 ppResult

[out] Vrátí [idiaenuminjectedsources –](../../debugger/debug-interface-access/idiaenuminjectedsources.md) objekt, který obsahuje seznam všech vloženého zdroje.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)