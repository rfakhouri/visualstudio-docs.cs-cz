---
title: Idiareadexeatrvacallback::readexecutableatrva – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
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
ms.openlocfilehash: f71db30a3e4cba957e6aba0981587276af714e3e
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
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