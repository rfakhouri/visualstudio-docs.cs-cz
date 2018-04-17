---
title: MemoryTypeEnum | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MemoryTypeEnum enumeration
ms.assetid: 8778c047-edeb-4495-8f9f-3f8bbb297099
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 92eaaa63f276d9107dfa3155eb85d52884d3157c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="memorytypeenum"></a>MemoryTypeEnum
Určuje typ paměti pro přístup.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
enum MemoryTypeEnum {  
   MemTypeCode,  
   MemTypeData,  
   MemTypeStack,  
   MemTypeAny = -1  
};  
```  
  
#### <a name="parameters"></a>Parametry  
 `MemTypeCode`  
 Přistupuje jenom kódu paměti.  
  
 `MemTypeData`  
 Data nebo zásobníku paměti přístupů.  
  
 `MemTypeStack`  
 Přistupuje jenom zásobníku paměti.  
  
 `MemTypeAny`  
 Přístup k jakýkoli druh paměti.  
  
## <a name="remarks"></a>Poznámky  
 Hodnoty v tento výčet jsou předávány [IDiaStackWalkHelper::readMemory](../../debugger/debug-interface-access/idiastackwalkhelper-readmemory.md) metoda omezení přístupu pro různé typy paměti.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: cvconst.h  
  
## <a name="see-also"></a>Viz také  
 [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaStackWalkHelper::readMemory](../../debugger/debug-interface-access/idiastackwalkhelper-readmemory.md)