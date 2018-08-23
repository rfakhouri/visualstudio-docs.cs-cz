---
title: Dimenze | Dokumentace Microsoftu
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
- Dimension Symbol
ms.assetid: 94f791da-bfea-454f-8a14-da31e8e1596a
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cfe5deec761426692b8f8fa1507ce4b3ca56629d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42677533"
---
# <a name="dimension"></a>Rozměr
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [dimenze](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/dimension).  
  
Každé pole až po FORTRAN má dimenze, která je identifikovaná `SymTagDimension` symbol.  
  
## <a name="properties"></a>Vlastnosti  
 V následující tabulce jsou uvedeny další platné vlastnosti pro tento typ symbolu.  
  
|Vlastnost|Datový typ|Popis|  
|--------------|---------------|-----------------|  
|[IDiaSymbol::get_lowerBound](../../debugger/debug-interface-access/idiasymbol-get-lowerbound.md)|`IDiaSymbol*`|Dolní mez pole dimenze až po FORTRAN.|  
|[IDiaSymbol::get_lowerBoundId](../../debugger/debug-interface-access/idiasymbol-get-lowerboundid.md)|`DWORD`|ID symbolu dolní mez.|  
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|ID indexu symbolu.|  
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Vrátí `SymTagDimension` (jeden z [symtagenum – výčet](../../debugger/debug-interface-access/symtagenum.md) hodnoty).|  
|[IDiaSymbol::get_upperBound](../../debugger/debug-interface-access/idiasymbol-get-upperbound.md)|`IDiaSymbol*`|Horní mez až po FORTRAN dimenze pole.|  
|[IDiaSymbol::get_upperBoundId](../../debugger/debug-interface-access/idiasymbol-get-upperboundid.md)|`DWORD`|ID symbolu horní mez.|  
  
## <a name="see-also"></a>Viz také  
 [ArrayType](../../debugger/debug-interface-access/arraytype.md)   
 [Hierarchie tříd typů symbolů](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)



