---
title: Idiareadexeatrvacallback::readexecutableatrva – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaReadExeAtRVACallback::ReadExecutableAtRVA method
ms.assetid: 3c1e965f-8f05-41a8-86d8-01830b2377c9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d622397984e6c1b43d1e62852652680b6a6711fb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiareadexeatrvacallbackreadexecutableatrva"></a>IDiaReadExeAtRVACallback::ReadExecutableAtRVA
Přečte zadaný počet bajtů, počínaje zadaný relativní virtuální adresa (RVA) ze spustitelného souboru.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT ReadExecutableAtRVA (   
   DWORD  relativeVirtualAddress,  
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[]  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `relativeVirtualAddress`  
 [v] RVA ve spustitelném souboru má začínat čtení.  
  
 `cbData`  
 [v] Počet bajtů ke čtení.  
  
 `pcbData`  
 [out] Vrátí počet bajtů přečtených.  
  
 `data[]`  
 [ve out] Pole, které obsahuje bajtů přečtených ze souboru.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je volána DIA podporu kód pro načtení datových bajtů z spustitelný soubor pomocí relativní virtuální adresy. Tato metoda je volána v podporu systému [idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [Idiareadexeatrvacallback –](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)