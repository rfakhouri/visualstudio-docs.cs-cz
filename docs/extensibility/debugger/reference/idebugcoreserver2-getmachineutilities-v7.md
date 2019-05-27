---
title: IDebugCoreServer2::GetMachineUtilities_V7 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCoreServer2::GetMachineUtilities_V7
helpviewer_keywords:
- IDebugCoreServer2::GetMachineUtilities_V7
ms.assetid: 64c1f08f-853b-4498-9810-29791581ef2f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 0aff4ccea937536530d74dde13a5ba8a7b14bca7
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66205675"
---
# <a name="idebugcoreserver2getmachineutilitiesv7"></a>IDebugCoreServer2::GetMachineUtilities_V7
Tato metoda načte počítač nástroje pro server.

> [!NOTE]
> Tato metoda je zastaralá: Nepoužívejte ([!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] vždy vrátí `E_NOTIMPL` Pokud tato metoda je volána). Je zachován z historických důvodů.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetMachineUtilities_V7(
   IDebugMDMUtil2_V7** ppUtil
);
```

```csharp
int GetMachineUtilities_V7(
   out IDebugMDMUtil2_V7 ppUtil
);
```

## <a name="parameters"></a>Parametry
`ppUtil`\
[out] Vrátí `IDebugMDMUtil2_V7` rozhraní, které představuje informace o počítači nástroje.

## <a name="return-value"></a>Návratová hodnota
 Vždy vrátí `E_NOTIMPL`, která udává, že metoda není implementována.

## <a name="remarks"></a>Poznámky
 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] vždy vrátí `E_NOTIMPL` Pokud tato metoda je volána.

## <a name="see-also"></a>Viz také:
- [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)