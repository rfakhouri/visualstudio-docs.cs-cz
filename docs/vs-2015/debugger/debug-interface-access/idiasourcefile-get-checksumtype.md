---
title: Idiasourcefile::get_checksumtype – | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSourceFile::get_checksumType method
ms.assetid: 4c363e61-a6a9-409a-9cc0-d06eb2bee645
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: f859bce63e2976b23ab613e249dad41b2bc63486
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68190700"
---
# <a name="idiasourcefilegetchecksumtype"></a>IDiaSourceFile::get_checksumType
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Načte typ kontrolního součtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT get_checksumType (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí typ kontrolního součtu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Typ kontrolního součtu je hodnota, která je možné mapovat na algoritmus kontrolního součtu. Například standardní formát souborů PDB může obvykle mít jednu z následujících hodnot:  
  
|Typ kontrolního součtu|Popisek rozhraní CryptoAPI|Popis|  
|-------------------|---------------------|-----------------|  
|0|\<žádné >|Žádné kontrolní součet k dispozici.|  
|1|`CALG_MD5`|kontrolní součet generuje s použitím algoritmu hash MD5.|  
|2|`CALG_SHA1`|kontrolní součet generuje s použitím algoritmu hash SHA1.|  
  
 `CryptoAPI` Popisky jsou z `ALG_ID` výčtu. Další informace o algoritmy hash, najdete `CryptoAPI` části Microsoft [!INCLUDE[winsdkshort](../../includes/winsdkshort-md.md)].  
  
 Chcete-li získat skutečný kontrolní součet bajtů pro zdrojový soubor, zavolejte [idiasourcefile::get_checksum –](../../debugger/debug-interface-access/idiasourcefile-get-checksum.md) metody.  
  
## <a name="see-also"></a>Viz také  
 [Idiasourcefile –](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSourceFile::get_checksum](../../debugger/debug-interface-access/idiasourcefile-get-checksum.md)
