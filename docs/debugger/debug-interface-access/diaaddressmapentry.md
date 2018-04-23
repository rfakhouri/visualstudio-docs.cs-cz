---
title: Diaaddressmapentry – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
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
ms.openlocfilehash: 0a29de8f18a9d3123d73210d0e362c2ae2d32641
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
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