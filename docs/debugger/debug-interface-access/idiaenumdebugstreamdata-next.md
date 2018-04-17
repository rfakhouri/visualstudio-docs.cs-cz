---
title: Idiaenumdebugstreamdata::Next – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumDebugStreamData::Next method
ms.assetid: 114171dd-38fd-4bd7-a702-8ff887ffc99b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b66a339d8925fc78c08eff2ac77086b04e6d07d4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiaenumdebugstreamdatanext"></a>IDiaEnumDebugStreamData::Next
Načte zadaný počet záznamů v výčtové pořadí.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT Next (   
   ULONG  celt,  
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[],  
   ULONG* pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 celt  
 [v] Počet záznamů, které mají být načteny.  
  
 cbData  
 [v] Velikost vyrovnávací paměť dat v bajtech.  
  
 pcbData  
 [out] Vrátí počet bajtů vrácených. Pokud `data` má hodnotu NULL, pak `pcbData` obsahuje celkový počet bajtů dat, které jsou k dispozici pro všechny požadované záznamy.  
  
 data]  
 [out] Vyrovnávací paměť, která má být vyplněny data záznam datový proud ladění.  
  
 pceltFetched  
 [ve out] Vrátí počet záznamů v `data`.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` Pokud neexistují žádné další záznamy. Jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiaenumdebugstreamdata –](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)   
 [IDiaEnumDebugStreams::Next](../../debugger/debug-interface-access/idiaenumdebugstreams-next.md)