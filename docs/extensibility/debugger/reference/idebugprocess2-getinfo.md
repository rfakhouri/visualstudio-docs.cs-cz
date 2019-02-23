---
title: IDebugProcess2::GetInfo | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess2::GetInfo
helpviewer_keywords:
- IDebugProcess2::GetInfo
ms.assetid: 46021dce-bb97-46c3-b0cc-e5b3b68acc35
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3d2a3b8b1ef028562502454994da18e799b8f28b
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56703541"
---
# <a name="idebugprocess2getinfo"></a>IDebugProcess2::GetInfo
Získá popis procesu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetInfo(
   PROCESS_INFO_FIELDS  Fields,
   PROCESS_INFO*        pProcessInfo
);
```

```csharp
int GetInfo(
   enum_PROCESS_INFO_FIELDS  Fields,
   PROCESS_INFO[]            pProcessInfo
);
```

#### <a name="parameters"></a>Parametry
 `Fields`

 [in] Kombinací hodnot z [PROCESS_INFO_FIELDS](../../../extensibility/debugger/reference/process-info-fields.md) výčet, který určuje, jaké pole `pProcessInfo` parametr mají být vyplněna.

 `pProcessInfo`

 [out] A [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md) struktura, která se vyplní popis procesu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)
- [PROCESS_INFO_FIELDS](../../../extensibility/debugger/reference/process-info-fields.md)
- [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)