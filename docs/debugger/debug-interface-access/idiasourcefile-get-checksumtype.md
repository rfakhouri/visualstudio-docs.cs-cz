---
title: Idiasourcefile::get_checksumtype – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSourceFile::get_checksumType method
ms.assetid: 4c363e61-a6a9-409a-9cc0-d06eb2bee645
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d372ad37419d95647a1492503a0b6cabe70ba649
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiasourcefilegetchecksumtype"></a>IDiaSourceFile::get_checksumType
Načte typ kontrolního součtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_checksumType (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí typ kontrolního součtu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Typ kontrolního součtu je hodnota, která lze mapovat na algoritmus kontrolního součtu. Například standardní formát souboru PDB může obvykle mít jednu z následujících hodnot:  
  
|Typ kontrolního součtu|Rozhraní CryptoAPI popisek|Popis|  
|-------------------|---------------------|-----------------|  
|0|\<žádné >|Žádné kontrolní součet přítomen.|  
|1|`CALG_MD5`|kontrolní součet vygenerovat pomocí algoritmu hash MD5.|  
|2|`CALG_SHA1`|kontrolní součet vygenerovat pomocí algoritmu hash SHA1.|  
  
 `CryptoAPI` Popisky jsou z `ALG_ID` výčtu. Další informace o algoritmy hash, najdete `CryptoAPI` části Microsoft [!INCLUDE[winsdkshort](../../debugger/debug-interface-access/includes/winsdkshort_md.md)].  
  
 Chcete-li získat skutečný kontrolní součet bajtů pro zdrojový soubor, zavolejte [idiasourcefile::get_checksum –](../../debugger/debug-interface-access/idiasourcefile-get-checksum.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [Idiasourcefile –](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSourceFile::get_checksum](../../debugger/debug-interface-access/idiasourcefile-get-checksum.md)