---
title: IDiaSymbol::get_numberOfAcceleratorPointerTags | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 1886e3ec-b227-4187-8d93-c5144b4b77ae
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 283533b20614ea727be620669ea5ab66cf00e5ed
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56605611"
---
# <a name="idiasymbolgetnumberofacceleratorpointertags"></a>IDiaSymbol::get_numberOfAcceleratorPointerTags
Vrátí počet značky akcelerátoru ukazatel ve funkci se zakázaným inzerováním C++ AMP.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_numberOfAcceleratorPointerTags(
   DWORD* count);
```

#### <a name="parameters"></a>Parametry
 `count`

[out] Ukazatel `DWORD` , který počet akcelerátoru uchovává ukazatel značky ve funkci se zakázaným inzerováním C++ AMP.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda je volána na `IDiaSymbol` rozhraní, který odpovídá zástupné procedury funkce C++ AMP akcelerátor.

## <a name="see-also"></a>Viz také
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)