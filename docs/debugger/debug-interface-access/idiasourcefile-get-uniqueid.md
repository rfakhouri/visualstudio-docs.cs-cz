---
title: Idiasourcefile::get_uniqueid – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSourceFile::get_uniqueId method
ms.assetid: e0b8dbc0-6061-4f31-bead-2cd72be44e41
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3eef4e6f435b60f024067e13c884c7742df0ffa2
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53879472"
---
# <a name="idiasourcefilegetuniqueid"></a>IDiaSourceFile::get_uniqueId
Načte hodnotu klíče jednoduché celé číslo, které jsou jedinečné pro tuto bitovou kopii.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_uniqueId (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí hodnotu klíče jednoduché celé číslo, které jsou jedinečné pro tuto bitovou kopii.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Porovnání klíčů, nikoli řetězce může zrychlit zpracování čísla řádku.  
  
## <a name="see-also"></a>Viz také  
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)