---
title: Idiaenumsymbolsbyaddr::symbolbyva – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSymbolsByAddr::symbolByVA method
ms.assetid: ac84339f-70c6-48ed-85d0-6d7d1b5194e8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2077c00069968c17da047270f6fdf98e66d5350f
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53868979"
---
# <a name="idiaenumsymbolsbyaddrsymbolbyva"></a>IDiaEnumSymbolsByAddr::symbolByVA
Pozice výčtu pomocí provádí vyhledávání podle virtuální adresy (VA).  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT symbolByVA (   
   DWORD**      virtualAddress,  
   IDiaSymbol** ppsymbol  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 virtualAddress  
 [in] Virtuální adresa.  
  
 ppsymbol  
 [out] Vrátí [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objekt představující symbol nalezen.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` Pokud symbol se nenašel. V opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiaenumsymbolsbyaddr –](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)