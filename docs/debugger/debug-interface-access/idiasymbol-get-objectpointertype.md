---
title: IDiaSymbol::get_objectPointerType | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_objectPointerType method
ms.assetid: bce193b9-67b0-4c35-96e5-6a664937322e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ce60ea631fe0c769740a2c3aa20281b13e525d18
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54916194"
---
# <a name="idiasymbolgetobjectpointertype"></a>IDiaSymbol::get_objectPointerType
Načte typ ukazatel objektu pro metodu třídy.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_objectPointerType (   
   IDiaSymbol** pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objekt, který představuje ukazatel objektu pro metodu třídy.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.  
  
## <a name="remarks"></a>Poznámky  
 Tato vlastnost se týká jenom pro symboly s [symtagenum – výčet](../../debugger/debug-interface-access/symtagenum.md) typ `SymTagFunctionType`.  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md)