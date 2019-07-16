---
title: Stackframetypeenum – | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- StackFrameTypeEnum enumeration
ms.assetid: 61e40163-eee0-4c1f-af47-cef3771bdc41
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 655911bac1efbafe1838e24e2056282f9036479b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68179189"
---
# <a name="stackframetypeenum"></a>StackFrameTypeEnum
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

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
