---
title: IDebugProgram2::GetEngineInfo | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2::GetEngineInfo
helpviewer_keywords:
- IDebugProgram2::GetEngineInfo
ms.assetid: 3a4f2dc0-e082-4d8d-aeaf-463ab09d279b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2b7a866730be3e6dfce8d68c655eb1f1b4d3f4da
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68148704"
---
# <a name="idebugprogram2getengineinfo"></a>IDebugProgram2::GetEngineInfo
Získá název a identifikátor GUID ladicího stroje (DE) spuštění tohoto programu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetEngineInfo( 
   BSTR* pbstrEngine,
   GUID* pguidEngine
);
```

```csharp
int GetEngineInfo( 
   out string pbstrEngine,
   out GUID   pguidEngine
);
```

#### <a name="parameters"></a>Parametry
 `pbstrEngine`

 [out] Vrátí název DE spuštěním tohoto programu.

 `pguidEngine`

 [out] Vrátí identifikátor GUID DE spuštěním tohoto programu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Každý DE definuje vlastní identifikátor GUID pro identifikaci.

## <a name="see-also"></a>Viz také
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)