---
title: Idiaenumsourcefiles::Item – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSourceFiles::Item method
ms.assetid: 3c19d7ed-0232-4b0e-9b10-f33ed9e0c93b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b21e77db31cbfbbf02aba2371b8211ffdd0c4a14
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53859130"
---
# <a name="idiaenumsourcefilesitem"></a>IDiaEnumSourceFiles::Item
Zkopíruje zdrojový soubor pomocí indexu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT Item (   
   DWORD            index,  
   IDiaSourceFile** sourceFile  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 index  
 [in] Index o [idiasourcefile –](../../debugger/debug-interface-access/idiasourcefile.md) objekt, který se má načíst. Index je v rozsahu 0 až `count`-1, kde `count` je vrácený [idiaenumsourcefiles::get_count –](../../debugger/debug-interface-access/idiaenumsourcefiles-get-count.md) metody.  
  
 zdrojový soubor  
 [out] Vrátí [idiasourcefile –](../../debugger/debug-interface-access/idiasourcefile.md) objekt představující požadovaný zdrojový soubor.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiaenumsourcefiles –](../../debugger/debug-interface-access/idiaenumsourcefiles.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)