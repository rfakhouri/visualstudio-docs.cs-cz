---
title: Idiaenumdebugstreamdata::get__newenum – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumDebugStreamData::get__NewEnum method
ms.assetid: 023b3e31-0fc9-478d-88e8-af2ce762f322
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e6246ec0a26b01144bfcc648079861b16fa6edb9
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56627633"
---
# <a name="idiaenumdebugstreamdatagetnewenum"></a>IDiaEnumDebugStreamData::get__NewEnum
Načte <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> verzi výčet.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get__NewEnum ( 
   IUnknown** pRetVal
);
```

#### <a name="parameters"></a>Parametry
 pRetVal

[out] Vrátí `IUnknown` rozhraní zastupující <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> verzi výčet.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDiaEnumDebugStreamData](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)