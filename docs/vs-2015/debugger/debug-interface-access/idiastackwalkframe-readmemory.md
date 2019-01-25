---
title: Idiastackwalkframe::readmemory – | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkFrame::readMemory method
ms.assetid: 7ab0b525-a5a7-4692-acad-e8c00fa9ab9a
caps.latest.revision: 15
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 97a868973d2a514150b8d728e685523e918f88f4
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54760675"
---
# <a name="idiastackwalkframereadmemory"></a>IDiaStackWalkFrame::readMemory
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Přečte paměti z image.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT readMemory (   
   MemoryTypeEnum type,  
   ULONGLONG va,  
   DWORD     cbData,  
   DWORD*    pcbData,  
   BYTE      data[]  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `type`  
 [in] Jeden z [memorytypeenum – výčet](../../debugger/debug-interface-access/memorytypeenum.md) hodnot výčtu, která určuje typ pro přístup k paměti.  
  
 `va`  
 [in] Virtuální adresa umístění obrázku má začínat čtení.  
  
 `cbData`  
 [in] Velikost vyrovnávací paměti dat v bajtech.  
  
 `pcbData`  
 [out] Vrátí počet bajtů vrácených. Pokud `data` je `NULL`, pak `pcbData` obsahuje celkový počet bajtů dat, které jsou k dispozici.  
  
 `data`  
 [out] Vyrovnávací paměť, která se vyplní data ze zadaného umístění.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)
