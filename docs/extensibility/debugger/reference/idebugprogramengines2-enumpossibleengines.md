---
title: IDebugProgramEngines2::EnumPossibleEngines | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramEngines2::EnumPossibleEngines
helpviewer_keywords:
- IDebugProgramEngines2::EnumPossibleEngines
ms.assetid: 993d70a4-f6a5-4e47-a603-0b162b9fde00
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9dc3185b644a1045428ead9f2c9851916df3249c
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56698232"
---
# <a name="idebugprogramengines2enumpossibleengines"></a>IDebugProgramEngines2::EnumPossibleEngines
Vrátí GUID pro všechny možné ladění motorů (DE), které můžete ladit tento program.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT EnumPossibleEngines( 
   DWORD  celtBuffer,
   GUID*  rgguidEngines,
   DWORD* pceltEngines
);
```

```csharp
int EnumPossibleEngines( 
   uint      celtBuffer,
   GUID[]    rgguidEngines,
   ref DWORD pceltEngines
);
```

#### <a name="parameters"></a>Parametry
 `celtBuffer`

 [in] Počet identifikátorů GUID DE vrátit. Také určuje maximální velikost `rgguidEngines` pole.

 `rgguidEngines`

 [out v] Pole DE identifikátory GUID pro vyplnění.

 `pceltEngines`

 [out] Vrátí skutečný počet DE identifikátory GUID, které jsou vráceny.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrátí [C++] `HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)` nebo [C#] 0x8007007A, pokud vyrovnávací paměť není dostatečně velký.

## <a name="remarks"></a>Poznámky
 Aby bylo možné zjistit, kolik motory existuje jsou, volejte tuto metodu jednou se `celtBuffer` parametr nastaven na hodnotu 0 a `rgguidEngines` parametr nastaven na hodnotu null. Vrátí `HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)` (0x8007007A pro jazyk C#) a `pceltEngines` parametr vrací potřebná velikost vyrovnávací paměti.

## <a name="see-also"></a>Viz také
- [IDebugProgramEngines2](../../../extensibility/debugger/reference/idebugprogramengines2.md)