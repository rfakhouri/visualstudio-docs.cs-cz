---
title: "Idiaenumdebugstreamdata::Item – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumDebugStreamData::Item method
ms.assetid: 761e61a5-44a6-4d5d-a98e-c2e9b89d2343
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 28cc2177d82c71f257812fd2b7106001ce4ea066
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiaenumdebugstreamdataitem"></a>IDiaEnumDebugStreamData::Item
Načte zadaný záznam.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT Item (   
   DWORD  index,  
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[]  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 index  
 [v] Index záznamu mají být načteny. Index je v rozsahu od 0 do `count`-1, kde `count` vrátí [idiaenumdebugstreamdata::get_count –](../../debugger/debug-interface-access/idiaenumdebugstreamdata-get-count.md).  
  
 cbData  
 [v] Velikost vyrovnávací paměť dat v bajtech.  
  
 pcbData  
 [out] Vrátí počet bajtů vrácených. Pokud `data` je `NULL`, pak `pcbData` obsahuje celkový počet bajtů dat, které jsou k dispozici v zadaný záznam.  
  
 data]  
 [out] Vyrovnávací paměť, která obsahuje data záznam datový proud ladění.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby. Vrátí `E_INVALIDARG` pro neplatné parametry a pokud `index` parametr je mimo rozsah.  
  
## <a name="see-also"></a>Viz také  
 [Idiaenumdebugstreamdata –](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)   
 [Idiaenumdebugstreamdata::Next –](../../debugger/debug-interface-access/idiaenumdebugstreamdata-next.md)   
 [Idiaenumdebugstreams::Item –](../../debugger/debug-interface-access/idiaenumdebugstreams-item.md)   
 [Idiaenumdebugstreamdata::get_count –](../../debugger/debug-interface-access/idiaenumdebugstreamdata-get-count.md)   
 [Idiaenumdebugstreamdata::Skip –](../../debugger/debug-interface-access/idiaenumdebugstreamdata-skip.md)