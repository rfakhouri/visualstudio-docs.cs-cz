---
title: Locationtype – | Dokumentace Microsoftu
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
- LocationType enumeration
ms.assetid: d3e1eedc-bfd3-4c91-881b-d69565138d0f
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a6d2400706a88dfcc40dec6e0e410c2e675bcf6d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675877"
---
# <a name="locationtype"></a>LocationType
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [locationtype –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/locationtype).  
  
Označuje druh informace o poloze, které jsou obsaženy v symbolu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
 Umístění je statická.  
  
 `LocIsTLS`  
 Umístění je v místním úložišti vláken.  
  
 `LocIsRegRel`  
 Umístění je relativní k registru.  
  
 `LocIsThisRel`  
 Umístění je `this`– relativní.  
  
 `LocIsEnregistered`  
 Umístění je v registru.  
  
 `LocIsBitField`  
 Umístění je ve bitového pole.  
  
 `LocIsSlot`  
 Umístění je slot Microsoft Intermediate Language (MSIL).  
  
 `LocIsIlRel`  
 Umístění je relativní vůči jazyka MSIL.  
  
 `LocInMetaData`  
 Umístění je v metadatech.  
  
 `LocIsConstant`  
 Umístění je konstantní hodnotu.  
  
 `LocTypeMax`  
 Počet typů umístění tohoto výčtu.  
  
## <a name="remarks"></a>Poznámky  
 Vlastnosti, které jsou k dispozici [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) rozhraní závisí na umístění symbolu v souboru bitové kopie. Další informace najdete v tématu [umístění symbolů](../../debugger/debug-interface-access/symbol-locations.md).  
  
 Hodnoty v tomto výčtu jsou vráceny prostřednictvím volání [idiasymbol::get_locationtype –](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md) metody.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: cvconst.h  
  
## <a name="see-also"></a>Viz také  
 [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [Idiasymbol::get_locationtype –](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)   
 [Umístění symbolů](../../debugger/debug-interface-access/symbol-locations.md)



