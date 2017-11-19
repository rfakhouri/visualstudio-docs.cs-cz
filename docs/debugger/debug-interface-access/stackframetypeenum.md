---
title: StackFrameTypeEnum | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: StackFrameTypeEnum enumeration
ms.assetid: 61e40163-eee0-4c1f-af47-cef3771bdc41
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 37d8e960d256b8746781668068978aa72f45155c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="stackframetypeenum"></a>StackFrameTypeEnum
Určuje typ rámce zásobníku.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
enum StackFrameTypeEnum {  
   FrameTypeFPO,  
   FrameTypeTrap,  
   FrameTypeTSS,  
   FrameTypeStandard,  
   FrameTypeFrameData,  
   FrameTypeUnknown = -1  
};  
```  
  
## <a name="elements"></a>Elementy  
 `FrameTypeFPO`  
 Ukazatel na rámec vynechání; Informace o FPO k dispozici.  
  
 `FrameTypeTrap`  
 Rámce depeše jádra.  
  
 `FrameTypeTSS`  
 Rámce depeše jádra.  
  
 `FrameTypeStandard`  
 Standardní EBP rámce zásobníku.  
  
 `FrameTypeFrameData`  
 Ukazatel na rámec vynechání; Informace rámce data nejsou k dispozici.  
  
 `FrameTypeUnknown`  
 Rámce, který nemá žádné informace o ladění.  
  
## <a name="remarks"></a>Poznámky  
 Hodnoty v tento výčet jsou vráceny prostřednictvím volání [idiastackframe::get_type –](../../debugger/debug-interface-access/idiastackframe-get-type.md) metoda.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: cvconst.h  
  
## <a name="see-also"></a>Viz také  
 [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [Idiastackframe::get_type –](../../debugger/debug-interface-access/idiastackframe-get-type.md)