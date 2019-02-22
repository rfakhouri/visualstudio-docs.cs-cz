---
title: IDebugPort2::GetProcess | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPort2::GetPortSupplier
helpviewer_keywords:
- IDebugPort2::GetPortSupplier
ms.assetid: 3e2431b0-0e19-450d-8e1d-d7c314c8f872
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 64d165fedf791e26cf291ed4b6255de81873953a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56694761"
---
# <a name="idebugport2getprocess"></a>IDebugPort2::GetProcess
Získá zadaný proces, který běží na portu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetProcess( 
   AD_PROCESS_ID    ProcessId,
   IDebugProcess2** ppProcess
);
```

```csharp
int GetProcess( 
   AD_PROCESS_ID      ProcessId,
   out IDebugProcess2 ppProcess
);
```

#### <a name="parameters"></a>Parametry
 `ProcessId`

 [in] [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) struktura, která určuje identifikátor procesu.

 `ppProcess`

 [out] Vrátí [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) objekt reprezentující proces.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)
- [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)