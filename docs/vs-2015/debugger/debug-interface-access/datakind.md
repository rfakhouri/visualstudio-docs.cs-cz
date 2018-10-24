---
title: Datakind – | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
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
- DataKind enumeration
ms.assetid: b64be708-22d6-4360-99e7-8f4e6b196de7
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d295c499fbb339d58340845bdcc508846d573c47
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49830493"
---
# <a name="datakind"></a>DataKind
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Určuje konkrétní obor datové hodnoty.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
enum DataKind {   
   DataIsUnknown,  
   DataIsLocal,  
   DataIsStaticLocal,  
   DataIsParam,  
   DataIsObjectPtr,  
   DataIsFileStatic,  
   DataIsGlobal,  
   DataIsMember,  
   DataIsStaticMember,  
   DataIsConstant  
};  
```  
  
## <a name="elements"></a>Elementy  
 DataIsUnknown  
 Datový symbol nejde určit.  
  
 DataIsLocal  
 Položka dat je místní proměnné.  
  
 DataIsStaticLocal  
 Položka dat je statické místní proměnné.  
  
 DataIsParam  
 Položka dat je formální parametr.  
  
 DataIsObjectPtr  
 Položka dat je ukazatelem na objekt (`this`).  
  
 DataIsFileStatic  
 Položka dat je proměnnou s rozsahem souboru.  
  
 DataIsGlobal  
 Položka dat je globální proměnné.  
  
 DataIsMember  
 Položka dat je proměnná člena objektu.  
  
 DataIsStaticMember  
 Položka dat je statická proměnná třídy.  
  
 DataIsConstant  
 Položka dat je konstantní hodnota.  
  
## <a name="remarks"></a>Poznámky  
 Jsou vrácené hodnoty v tento výčet [idiasymbol::get_datakind –](../../debugger/debug-interface-access/idiasymbol-get-datakind.md) metody.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: cvconst.h  
  
## <a name="see-also"></a>Viz také  
 [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_dataKind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)



