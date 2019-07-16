---
title: Memorytypeenum – | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- MemoryTypeEnum enumeration
ms.assetid: 8778c047-edeb-4495-8f9f-3f8bbb297099
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ded136da4d601fd7c11a10c21aac0c90864bc0bc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68158133"
---
# <a name="memorytypeenum"></a>MemoryTypeEnum
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Určuje typ pro přístup k paměti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
enum MemoryTypeEnum {  
   MemTypeCode,  
   MemTypeData,  
   MemTypeStack,  
   MemTypeAny = -1  
};  
```  
  
#### <a name="parameters"></a>Parametry  
 `MemTypeCode`  
 Přístupy pouze kód paměti.  
  
 `MemTypeData`  
 Přístupy do paměti data nebo zásobníku.  
  
 `MemTypeStack`  
 Přístupy pouze zásobníku paměti.  
  
 `MemTypeAny`  
 Přistupuje k jakýkoli druh paměti.  
  
## <a name="remarks"></a>Poznámky  
 Hodnoty v tento výčet se předají [IDiaStackWalkHelper::readMemory](../../debugger/debug-interface-access/idiastackwalkhelper-readmemory.md) metody k omezení přístupu k různé druhy paměti.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: cvconst.h  
  
## <a name="see-also"></a>Viz také  
 [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaStackWalkHelper::readMemory](../../debugger/debug-interface-access/idiastackwalkhelper-readmemory.md)
