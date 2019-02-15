---
title: CV_access_e | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CV_access_e enumeration
ms.assetid: 33c05d65-abb4-4800-a382-54a3805ea7b0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2b5fa908692167b49c6bb92c892fb143b882d231
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2019
ms.locfileid: "56318573"
---
# <a name="cvaccesse"></a>CV_access_e
Určuje obor viditelnost (úroveň přístupu) členské funkce a proměnné.

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
Člen chrání přístup.

CV_public  
Člen má veřejný přístup.

## <a name="remarks"></a>Poznámky
`friend` Specifikátor přístupu zde není obsažena vzhledem k tomu, že se obvykle používá funkce bez členů, které mají přístup k soukromým a chráněným elementy třídy. Použití [idiasymbol::get_symtag –](../../debugger/debug-interface-access/idiasymbol-get-symtag.md) metodu pro hledání symbolů se `SymTagFriend` přístup.

## <a name="requirements"></a>Požadavky
Záhlaví: cvconst.h

## <a name="see-also"></a>Viz také
[Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)  
[IDiaSymbol::get_access](../../debugger/debug-interface-access/idiasymbol-get-access.md)  
[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)
