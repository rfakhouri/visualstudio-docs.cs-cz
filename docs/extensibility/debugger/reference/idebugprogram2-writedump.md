---
title: IDebugProgram2::WriteDump | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2::WriteDump
helpviewer_keywords:
- IDebugProgram2::WriteDump
ms.assetid: 375afb8c-882d-44db-bfa7-e2c9eb555122
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: abafa1e3673a334105e8b8ec6e7957f631f000b2
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56684205"
---
# <a name="idebugprogram2writedump"></a>IDebugProgram2::WriteDump
Výpis zapíše do souboru.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT WriteDump( 
   DUMPTYPE  DumpType,
   LPCOLESTR pszDumpUrl
);
```

```csharp
int WriteDump( 
   enum_DUMPTYPE  DumpType,
   string         pszDumpUrl
);
```

#### <a name="parameters"></a>Parametry
 `DumpType`

 [in] Hodnota z [DUMPTYPE](../../../extensibility/debugger/reference/dumptype.md) výčet, který určuje typ s výpisem paměti, například řečeno nebo long.

 `pszDumpUrl`

 [in] Adresa URL s výpisem paměti pro zápis. Obvykle je to ve formě `file://c:\path\filename.ext`, ale mohou být jakákoliv platná adresa URL.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Výpis program obvykle zahrnuje aktuální rámec zásobníku, zásobník samotný seznam vlákna spuštěná v programu a pravděpodobně paměti, která vlastní program.

## <a name="see-also"></a>Viz také
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)