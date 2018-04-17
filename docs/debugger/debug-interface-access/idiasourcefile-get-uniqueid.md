---
title: Idiasourcefile::get_uniqueid – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
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
ms.openlocfilehash: 0d7f28f2bec0ce4123014c6c64f4d611b2a7d436
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiasourcefilegetuniqueid"></a>IDiaSourceFile::get_uniqueId
Načte jednoduché celočíselnou hodnotu klíče, které jsou jedinečné pro tuto bitovou kopii.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_uniqueId (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrací jednoduchý celočíselnou hodnotu klíče, které jsou jedinečné pro tuto bitovou kopii.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Porovnání klíčů místo řetězce můžou urychlit zpracování číslo řádku.  
  
## <a name="see-also"></a>Viz také  
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)