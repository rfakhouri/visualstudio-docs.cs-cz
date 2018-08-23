---
title: Stackframetypeenum – | Dokumentace Microsoftu
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
- StackFrameTypeEnum enumeration
ms.assetid: 61e40163-eee0-4c1f-af47-cef3771bdc41
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 081be0d7b9369462bae703b571629897bd5df94c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631483"
---
# <a name="stackframetypeenum"></a>StackFrameTypeEnum
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [stackframetypeenum –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/stackframetypeenum).  
  
Určuje typ rámce zásobníku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
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
 Tento parametr vynechán, ukazatel na rámec Informace o FPO k dispozici.  
  
 `FrameTypeTrap`  
 Rámec depeše jádra.  
  
 `FrameTypeTSS`  
 Rámec depeše jádra.  
  
 `FrameTypeStandard`  
 Standardní EBP rámce zásobníku.  
  
 `FrameTypeFrameData`  
 Tento parametr vynechán, ukazatel na rámec Rámec informace o datech k dispozici.  
  
 `FrameTypeUnknown`  
 Snímek, který nemá dostupné žádné ladicí informace.  
  
## <a name="remarks"></a>Poznámky  
 Hodnoty v tomto výčtu jsou vráceny prostřednictvím volání [idiastackframe::get_type –](../../debugger/debug-interface-access/idiastackframe-get-type.md) metody.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: cvconst.h  
  
## <a name="see-also"></a>Viz také  
 [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaStackFrame::get_type](../../debugger/debug-interface-access/idiastackframe-get-type.md)



