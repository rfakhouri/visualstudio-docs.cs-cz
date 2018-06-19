---
title: Idiasymbol::get_intrinsic – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_intrinsic method
ms.assetid: f969f595-d9f9-48b9-adaa-63a6e4e09575
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e5293c17d73e1c0b9232862f3b8ff491a55b7e24
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31462857"
---
# <a name="idiasymbolgetintrinsic"></a>IDiaSymbol::get_intrinsic
Načte příznak určující, zda je třída vnitřního typu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_intrinsic(   
   BOOL* pRetVal)  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí `TRUE` Pokud třída je vnitřní typ; jinak vrátí `FALSE`.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` nebo chybový kód.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená vlastnost není k dispozici pro symbol.  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Dia2.h  
  
 Knihovna: diaguids.lib  
  
 Knihovny DLL: msdia100.dll  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)