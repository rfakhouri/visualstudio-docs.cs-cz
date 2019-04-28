---
title: IDiaStackWalker::getEnumFrames2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalker2::getEnumFrames2 method
ms.assetid: 73196d3f-112c-4b3a-997b-7c6b815d4afc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 35886ea0456426c30c44d5fd8e90399d4a2143ef
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62837937"
---
# <a name="idiastackwalkergetenumframes2"></a>IDiaStackWalker::getEnumFrames2
Načte čítač rámce zásobníku pro typ konkrétní platformy.

## <a name="syntax"></a>Syntaxe

```C++

      HRESULT getEnumFrames2( 
   enum  CV_CPU_TYPE_e    cpuid,
   IDiaStackWalkHelper*   pHelper,
   IDiaEnumStackFrames**  ppEnum
);
```

#### <a name="parameters"></a>Parametry
 `cpuid`

[in] Hodnota z [cv_cpu_type_e – výčet](../../debugger/debug-interface-access/cv-cpu-type-e.md) výčet určující typ platformy.

 `pHelper`

[in] Pomocná rutina [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md) objektu.

 `ppEnum`

[out] Vrátí [idiaenumstackframes –](../../debugger/debug-interface-access/idiaenumstackframes.md) objekt, který obsahuje seznam [idiastackframe –](../../debugger/debug-interface-access/idiastackframe.md) objekty.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 K získání seznamu rámce zásobníku pro právě x86 platformy, volání [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md) metody.

## <a name="see-also"></a>Viz také
- [IDiaStackWalker](../../debugger/debug-interface-access/idiastackwalker.md)
- [CV_CPU_TYPE_e – výčet](../../debugger/debug-interface-access/cv-cpu-type-e.md)
- [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)
- [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)
- [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)