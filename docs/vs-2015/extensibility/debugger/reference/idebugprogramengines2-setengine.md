---
title: IDebugProgramEngines2::SetEngine | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramEngines2::SetEngine
helpviewer_keywords:
- IDebugProgramEngines2::SetEngine
ms.assetid: c05857ee-89cf-455e-8f1e-300cce4a2eab
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7541971da9420b0527b7c9885f1421b8c2ce0075
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68182174"
---
# <a name="idebugprogramengines2setengine"></a>IDebugProgramEngines2::SetEngine
Říká program nebo program uzel které ladicího stroje (DE) použít pro ladění tohoto programu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT SetEngine( 
   REFGUID guidEngine
);
```

```csharp
int SetEngine( 
   ref Guid guidEngine
);
```

#### <a name="parameters"></a>Parametry
 `guidEngine`

 [in] Identifikátor GUID je DE.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDebugProgramEngines2](../../../extensibility/debugger/reference/idebugprogramengines2.md)