---
title: "Idiasymbol::get_registerid – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSymbol::get_registerId method
ms.assetid: f881e793-eb9e-48dc-a847-dd61d77174fc
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d5fe8b131e715f5fa55d2d2f99cb8c4714996290
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiasymbolgetregisterid"></a>IDiaSymbol::get_registerId
Načte označení registrace umístění při [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md) je nastaven na `LocIsEnregistered`.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_registerId (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí označení registrace umístění.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` nebo chybový kód.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.  
  
## <a name="remarks"></a>Poznámky  
 Pokud symbol je relativní vzhledem k registraci, to znamená, pokud je symbol [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md) je nastaven na `LocIsRegRel`, použijte `get_registerId` metoda následuje volání [idiasymbol::get_offset –](../../debugger/debug-interface-access/idiasymbol-get-offset.md) Metoda posun sám zaregistrovat, kde se nachází symbolu.  
  
## <a name="see-also"></a>Viz také  
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md)