---
title: IDiaStackWalkHelper::readMemory | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaStackWalkHelper2::readMemory method
ms.assetid: e1eb90aa-49b7-476c-9e70-7e8f08994cbe
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f528d377dc75f940a10f1a38ae04cc3eb71cdd22
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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