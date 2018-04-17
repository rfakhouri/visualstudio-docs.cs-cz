---
title: CV_access_e | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CV_access_e enumeration
ms.assetid: 33c05d65-abb4-4800-a382-54a3805ea7b0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1cd11b7d72e84eb773a833414bb6c14716827cf9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="cvaccesse"></a>CV_access_e
Určuje rozsah viditelnost (úroveň přístupu) členské funkce a proměnné.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
typedef enum CV_access_e {   
   CV_private   = 1,  
   CV_protected = 2,  
   CV_public    = 3  
} CV_access_e;  
```  
  
## <a name="elements"></a>Elementy  
 CV_private  
 Člen má soukromý přístup.  
  
 CV_protected  
 Člen je chráněný přístup.  
  
 CV_public  
 Člen má veřejný přístup.  
  
## <a name="remarks"></a>Poznámky  
 `friend` Specifikátor přístupu se sem nezahrnuje vzhledem k tomu, že je obvykle používán třetí funkce, které mají přístup k privátní a chráněné elementy třídy. Použití [idiasymbol::get_symtag –](../../debugger/debug-interface-access/idiasymbol-get-symtag.md) metody k vyhledání symboly s `SymTagFriend` přístup.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: cvconst.h  
  
## <a name="see-also"></a>Viz také  
 [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [Idiasymbol::get_access –](../../debugger/debug-interface-access/idiasymbol-get-access.md)   
 [IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)