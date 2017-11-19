---
title: "Idiasymbol::get_addressoffset – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSymbol::get_addressOffset method
ms.assetid: c15639b0-7f37-46c7-891b-40273b7f6319
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3e13e130febd36f4b9bf8e0964ac00b78647b034
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiasymbolgetaddressoffset"></a>IDiaSymbol::get_addressOffset
Načte posunutí součástí na adresu umístění. Použijte, když [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md) je nastaven na `LocIsStatic`.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_addressOffset (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí posunutí část na adresu umístění.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` nebo chybový kód.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.  
  
## <a name="remarks"></a>Poznámky  
 Pro statické členy v externí knihovny DLL posun vrácená touto metodou být 0, jak tato metoda je založena na získání virtuální adresy člena. Virtuální adresy jsou platné pouze v případě [idiasession::put_loadaddress –](../../debugger/debug-interface-access/idiasession-put-loadaddress.md) metoda v [idiasession –](../../debugger/debug-interface-access/idiasession.md) rozhraní byla volána s nenulovou parametr zadání adresy zatížení knihovnu DLL.  
  
 Část oddílu adresu získáte volání [idiasymbol::get_addresssection –](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md) metoda.  
  
## <a name="requirements"></a>Požadavky  
  
|Požadavek|Popis|  
|-----------------|-----------------|  
|Hlavičky:|dia2.h|  
|Verze:|V7.0 DIA SDK|  
  
## <a name="see-also"></a>Viz také  
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md)   
 [Idiasymbol::get_addresssection –](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)   
 [Idiasession::put_loadaddress –](../../debugger/debug-interface-access/idiasession-put-loadaddress.md)   
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)