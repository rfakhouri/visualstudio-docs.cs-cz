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
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62835771"
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

[out] Ukazatel na `DWORD` , který obsahuje počet akcelerátoru ukazatel značek v C++ funkci AMP zástupné procedury.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda je volána na `IDiaSymbol` rozhraní, který odpovídá zástupné procedury funkce C++ AMP akcelerátor.

## <a name="see-also"></a>Viz také
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)