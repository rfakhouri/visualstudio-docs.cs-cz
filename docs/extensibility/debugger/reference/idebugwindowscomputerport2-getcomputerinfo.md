---
title: IDebugWindowsComputerPort2::GetComputerInfo | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- GetComputerInfo
- IDebugWindowsComputerPort2::GetComputerInfo
ms.assetid: 654910b2-c239-44c8-92fc-317680a5672f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2f75428155cfff20ce280d8428839d4332d13031
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62868099"
---
# <a name="idebugwindowscomputerport2getcomputerinfo"></a>IDebugWindowsComputerPort2::GetComputerInfo
Načte informace o počítači, na kterém běží v ladicím programu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetComputerInfo(
   COMPUTER_INFO * pInfo
);
```

```csharp
public int GetComputerInfo(
   out COMPUTER_INFO[] pInfo
);
```

#### <a name="parameters"></a>Parametry
 `pInfo`

 [out] Odkaz na strukturu, která obsahuje informace o počítači.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDebugWindowsComputerPort2](../../../extensibility/debugger/reference/idebugwindowscomputerport2.md)
- [COMPUTER_INFO](../../../extensibility/debugger/reference/computer-info.md)