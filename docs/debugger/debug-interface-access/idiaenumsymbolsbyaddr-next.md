---
title: Idiaenumsymbolsbyaddr::Next – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSymbolsByAddr::Next method
ms.assetid: a1320587-7ce7-401f-9548-2f8bcece5cc3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ffede509bdeb45ad1ca19b368d10928568f4fff8
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31462510"
---
# <a name="idiaenumsymbolsbyaddrnext"></a>IDiaEnumSymbolsByAddr::Next
Načte další symboly v pořadí podle adresy.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT Next (   
   ULONG        celt,   
   IDiaSymbol** rgelt,  
   ULONG*       pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 celt  
 [v] Počet symboly v enumerátor mají být načteny.  
  
 rgelt  
 [out] Pole, které se v pomocí [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objekt, který představuje požadované symboly.  
  
 pceltFetched  
 [out] Vrátí číslo symbolů v načtených enumerátor.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` Pokud neexistují žádné další symboly. Jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda aktualizuje tak počet elementů načtených pozice enumerátor.  
  
## <a name="see-also"></a>Viz také  
 [Idiaenumsymbolsbyaddr –](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)