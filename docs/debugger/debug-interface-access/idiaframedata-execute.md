---
title: IDiaFrameData::execute | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::execute method
ms.assetid: 7a6c7d03-1ff1-4059-bd54-5f407eeebc26
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 78440c703ece2aa54e54594d57156dbb17848915
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62832648"
---
# <a name="idiaframedataexecute"></a>IDiaFrameData::execute
Provádí odvíjení zásobníku a vrátí výsledky v rozhraní rámce zásobníku funkce walk.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT execute ( 
   IDiaStackWalkFrame* frame
);
```

#### <a name="parameters"></a>Parametry
 `frame`

[in] [Idiastackwalkframe –](../../debugger/debug-interface-access/idiastackwalkframe.md) objekt, který obsahuje stav rámce registrů.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. V následující tabulce jsou uvedeny možné návratové hodnoty pro tuto metodu.

|Value|Popis|
|-----------|-----------------|
|E_DIA_INPROLOG|Nelze spustit blok zásobníku v kódu prologu.|
|E_DIA_SYNTAX|Analyzovat v aplikaci rámce došlo k chybě.|
|E_DIA_FRAME_ACCESS|Nepovedlo se přístup registrů nebo paměti.|
|E_DIA_VALUE|Při výpočtu hodnoty (například dělení nulou).|

## <a name="remarks"></a>Poznámky
 Tato metoda je volána při ladění k provedení operace unwind zásobníku. [Idiastackwalkframe –](../../debugger/debug-interface-access/idiastackwalkframe.md) objektu je implementováno klientské aplikace pro příjem aktualizací registry a poskytovat metody používané `execute` metody.

## <a name="see-also"></a>Viz také
- [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
- [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)