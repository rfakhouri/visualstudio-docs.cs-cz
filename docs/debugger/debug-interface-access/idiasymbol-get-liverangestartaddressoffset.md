---
title: IDiaSymbol::get_liveRangeStartAddressOffset | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_liveRangeStartAddressOffset
ms.assetid: f5b28914-0a14-4b22-8259-59d7f97ee610
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: af4a5ec86a3626771e7b3a91b4d528700d57f270
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiasymbolgetliverangestartaddressoffset"></a>IDiaSymbol::get_liveRangeStartAddressOffset
Vrátí posunutí část počáteční adresa rozsahu, ve kterém je platný místní symbolu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_liveRangeStartAddressOffset (   
   DWORD* offset  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `offset`  
 [out] Vrátí posunutí část počáteční rozsah adres.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
> [!NOTE]
>  Kód chyby: znamená, že symbol nemá informace o rozsahu za provozu.  
  
## <a name="remarks"></a>Poznámky  
 Adresu v poli části a posun je začátek rozsahu, ve kterém je platný symbolu.  
  
 Část část adresy, použijte [IDiaSymbol::get_liveRangeStartAddressSection](../../debugger/debug-interface-access/idiasymbol-get-liverangestartaddresssection.md).  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Dia2.h  
  
 Knihovna: diaguids.lib  
  
 Knihovny DLL: msdia100.dll  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)