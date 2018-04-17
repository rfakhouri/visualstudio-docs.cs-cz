---
title: Diaaddressmapentry – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DiaAddressMapEntry enumeration
ms.assetid: 5d0ae226-981d-4541-a801-fc4993fe663b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bc13e8813c0e1bddd1f6cb9abd3d70b26eb5a8e1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="diaaddressmapentry"></a>DiaAddressMapEntry
Popisuje položku v adres mapují.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
struct DiaAddressMapEntry {   
   DWORD rva,  
   DWORD rvaTo  
};  
```  
  
## <a name="elements"></a>Elementy  
 `rva`  
 Relativní virtuální adresy (RVA) v bitové kopii A.  
  
 `rvaTo`  
 Relativní virtuální adresy `rva` je namapována na obrázku B.  
  
## <a name="remarks"></a>Poznámky  
 Adres mapují poskytuje překlad z jedné bitové kopie rozložení (A) do jiné (B). Pole `DiaAddressMapEntry` struktury seřazené podle `rva` definuje mapování adresy.  
  
 Chcete-li přeložit adresu, `addrA`, v bitové kopii A na adresu, `addrB`, v bitové kopii B, proveďte následující kroky:  
  
1.  Hledat mapy pro položku, `e`, s nejvyšší `rva` menší než nebo rovna hodnotě `addrA`.  
  
2.  Nastavit `delta = addrA - e.rva`.  
  
3.  Nastavit `addrB = e.rvaTo + delta`.  
  
 Pole `DiaAddressMapEntry` struktury předána [idiaaddressmap::set_addressmap –](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md) metoda.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: dia2.h  
  
## <a name="see-also"></a>Viz také  
 [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaAddressMap::set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)