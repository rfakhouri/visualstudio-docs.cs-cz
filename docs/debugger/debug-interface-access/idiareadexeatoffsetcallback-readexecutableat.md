---
title: Idiareadexeatoffsetcallback::readexecutableat – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaReadExeAtOffsetCallback::ReadExecutableAt method
ms.assetid: 30b1cef0-b366-4712-8e89-d21f640964f8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e43bb15eb91e3ffdaa7306140206ca80c2547b0b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiareadexeatoffsetcallbackreadexecutableat"></a>IDiaReadExeAtOffsetCallback::ReadExecutableAt
Přečte zadaný počet bajtů, začínající na zadaném posunu ze spustitelného souboru.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT ReadExecutableAt (   
   DWORDLONG fileOffset,  
   DWORD     cbData,  
   DWORD*    pcbData,  
   BYTE      data[]  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 fileOffset  
 [v] Posun ve spustitelném souboru má začínat čtení.  
  
 cbData  
 [v] Počet bajtů ke čtení.  
  
 pcbData  
 [out] Vrátí počet bajtů přečtených.  
  
 data]  
 [ve out] Pole, které obsahuje bajtů přečtených ze souboru.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je volána DIA podporu kód pro načtení datových bajtů z spustitelný soubor využívající posun absolutní souboru. Tato metoda je volána v podporu systému [idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [Idiareadexeatoffsetcallback –](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)