---
title: IDiaStackWalkHelper::readMemory | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
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
ms.openlocfilehash: f8ef913a94dc184339d6c20c97ca8c3f0f3054a4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42671790"
---
# <a name="idiastackwalkhelperreadmemory"></a>IDiaStackWalkHelper::readMemory
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDiaStackWalkHelper::readMemory](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiastackwalkhelper-readmemory).  
  
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
 [Memorytypeenum – výčet](../../debugger/debug-interface-access/memorytypeenum.md)



