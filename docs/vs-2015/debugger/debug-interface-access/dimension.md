---
title: Dimenze | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Dimension Symbol
ms.assetid: 94f791da-bfea-454f-8a14-da31e8e1596a
caps.latest.revision: 18
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 1b760d6a7808154b8daabe43d4cf6399c3b91977
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68164345"
---
# <a name="dimension"></a>Rozměr
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

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
