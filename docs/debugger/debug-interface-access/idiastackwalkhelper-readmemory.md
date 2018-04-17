---
title: IDiaStackWalkHelper::readMemory | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::readMemory method
ms.assetid: e1eb90aa-49b7-476c-9e70-7e8f08994cbe
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: af93d4d49167a6167d971140c3b668c95a34f799
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiastackwalkhelperreadmemory"></a>IDiaStackWalkHelper::readMemory
Čte blok dat z ke spustitelnému souboru bitové kopie v paměti.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT readMemory(   
   enum MemoryTypeEnum type,  
   ULONGLONG           va,  
   DWORD               cbData,  
   DWORD*              pcbData,  
   BYTE*               pbData  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `type`  
 [v] Hodnota z [MemoryTypeEnum – výčet](../../debugger/debug-interface-access/memorytypeenum.md) výčtu určení typu paměť pro čtení.  
  
 Va  
 [v] Virtuální adresa do bitové kopie, ve kterém má začínat čtení.  
  
 `cbData`  
 [v] Velikost vyrovnávací paměť dat v bajtech.  
  
 `pcbData`  
 [out] Vrátí počet bajtů ve skutečnosti číst. Pokud `pbData` je `NULL`, pak toto je celkový počet bajtů dat, které jsou k dispozici.  
  
 `pbData`  
 [ve out] Vyrovnávací paměť, která obsahuje paměť pro čtení.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [MemoryTypeEnum – výčet](../../debugger/debug-interface-access/memorytypeenum.md)