---
title: LocationType | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: LocationType enumeration
ms.assetid: d3e1eedc-bfd3-4c91-881b-d69565138d0f
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d5a6a14b3e5e1731c7b9f1fd58181be7adb870d9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="locationtype"></a>LocationType
Určuje druh informace o umístění, které jsou obsaženy v symbolu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
enum LocationType {   
   LocIsNull,  
   LocIsStatic,  
   LocIsTLS,  
   LocIsRegRel,  
   LocIsThisRel,  
   LocIsEnregistered,  
   LocIsBitField,  
   LocIsSlot,  
   LocIsIlRel,  
   LocInMetaData,  
   LocIsConstant,  
   LocTypeMax  
};  
```  
  
## <a name="elements"></a>Elementy  
 `LocIsNull`  
 Informace o umístění není k dispozici.  
  
 `LocIsStatic`  
 Umístění je statický.  
  
 `LocIsTLS`  
 Umístění je v místní úložiště vláken.  
  
 `LocIsRegRel`  
 Umístění je relativní vzhledem k registraci.  
  
 `LocIsThisRel`  
 Umístění je `this`– relativní.  
  
 `LocIsEnregistered`  
 Umístění je do registru.  
  
 `LocIsBitField`  
 Umístění je v poli verze.  
  
 `LocIsSlot`  
 Umístění je slot Microsoft Intermediate Language (MSIL).  
  
 `LocIsIlRel`  
 Umístění je relativní vůči MSIL.  
  
 `LocInMetaData`  
 Umístění je v metadatech.  
  
 `LocIsConstant`  
 Umístění je v konstantní hodnotu.  
  
 `LocTypeMax`  
 Počet typů umístění v tento výčet.  
  
## <a name="remarks"></a>Poznámky  
 Vlastnosti, které jsou k dispozici [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) rozhraní závisí na umístění symbolu v souboru bitové kopie. Další informace najdete v tématu [umístění symbolu](../../debugger/debug-interface-access/symbol-locations.md).  
  
 Hodnoty v tento výčet jsou vráceny prostřednictvím volání [idiasymbol::get_locationtype –](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md) metoda.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: cvconst.h  
  
## <a name="see-also"></a>Viz také  
 [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [Idiasymbol::get_locationtype –](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)   
 [Umístění symbolů](../../debugger/debug-interface-access/symbol-locations.md)