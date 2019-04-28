---
title: IDiaStackFrame::get_rawLVarInstanceValue | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackFrame::get_rawLVarInstanceValue method
ms.assetid: ce526259-85a6-475b-9274-0b3a21d95db2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c8ff78c38ad077084b3dea9c96e3251ffddb2206
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62573011"
---
# <a name="idiastackframegetrawlvarinstancevalue"></a>IDiaStackFrame::get_rawLVarInstanceValue
Tato metoda načte hodnotu místní proměnné zadané jako nezpracovaný bajtů.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_rawLVarInstanceValue(
   IDiaLVarInstance* pInstance,
   DWORD             cbDataMax,
   DWORD*            pcbData,
   BYTE*             pbData
);
```

#### <a name="parameters"></a>Parametry
 `pInstance`

[in] `IDiaLVarInstance` Objekt představující instance má být získána hodnota pro lokální proměnné.

 `cbDataMax`

[in] Maximální počet bajtů ve vyrovnávací paměti na které odkazuje `pbData`. To může být maximálně 8 bajtů (`sizeof(ULONGLONG)`).

 `pcbData`

[out] Vrátí skutečný počet bajtů uložených do vyrovnávací paměti.

 `pbData`

[out] Vyrovnávací paměti, která vyplní data. IP adresa nesmí být `NULL`.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)