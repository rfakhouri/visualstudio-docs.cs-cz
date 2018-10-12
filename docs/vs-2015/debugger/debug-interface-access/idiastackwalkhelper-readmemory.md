---
title: IDiaStackWalkHelper::readMemory | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::readMemory method
ms.assetid: e1eb90aa-49b7-476c-9e70-7e8f08994cbe
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3e110a67f7db5359d9f840f8853307206b84e339
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49201523"
---
# <a name="idiastackwalkhelperreadmemory"></a>IDiaStackWalkHelper::readMemory
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Čte blok dat z ke spustitelnému souboru bitové kopie v paměti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
 [in] Hodnota z [memorytypeenum – výčet](../../debugger/debug-interface-access/memorytypeenum.md) výčet určující druh paměť pro čtení.  
  
 posouzení ohrožení zabezpečení  
 [in] Virtuální adresa obrázku, ve kterém má začínat čtení.  
  
 `cbData`  
 [in] Velikost vyrovnávací paměti dat v bajtech.  
  
 `pcbData`  
 [out] Vrátí počet bajtů ve skutečnosti číst. Pokud `pbData` je `NULL`, pak toto je celkový počet bajtů dat, které jsou k dispozici.  
  
 `pbData`  
 [out v] Vyrovnávací paměť je vyplní paměti čtení.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [MemoryTypeEnum – výčet](../../debugger/debug-interface-access/memorytypeenum.md)



