---
title: LocationType | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- LocationType enumeration
ms.assetid: d3e1eedc-bfd3-4c91-881b-d69565138d0f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fb46eb1c7477f93ed63dfc4424d881886c8d0c8f
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
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