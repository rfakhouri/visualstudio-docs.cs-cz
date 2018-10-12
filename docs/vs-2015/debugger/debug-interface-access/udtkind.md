---
title: Udtkind – | Dokumentace Microsoftu
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
- UdtKind enumeration
ms.assetid: 400b59b9-373c-42cb-aae1-570494214328
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cab812e6d5ec14e393cadd5c0404c3a705865fbc
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49273218"
---
# <a name="udtkind"></a>UdtKind
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Popisuje různé uživatelem definovaný typ (UDT).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
enum UdtKind {   
   UdtStruct,  
   UdtClass,  
   UdtUnion,  
   UdtInterface  
};  
```  
  
## <a name="elements"></a>Elementy  
 UdtStruct  
 UDT je struktura.  
  
 UdtClass  
 UDT je třída.  
  
 UdtUnion  
 UDT je sjednocení.  
  
 UdtInterface  
 UDT je rozhraní.  
  
## <a name="remarks"></a>Poznámky  
 Jsou vrácené hodnoty v tento výčet [idiasymbol::get_udtkind –](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md) metody.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: cvconst.h  
  
## <a name="see-also"></a>Viz také  
 [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_udtKind](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md)



