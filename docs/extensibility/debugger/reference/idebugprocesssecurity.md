---
title: IDebugProcessSecurity | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugProcessSecurity interface
ms.assetid: 8a52ddca-bd99-49c0-9778-469dce7abd44
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 12c1cc5af90fa0ff337a105f6d3d7232b72ab6ac
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62917431"
---
# <a name="idebugprocesssecurity"></a>IDebugProcessSecurity
`IDebugProcessSecurity` je implementováno dodavatele portu uživatele upozornit, že není bezpečné připojování k procesu.

## <a name="syntax"></a>Syntaxe

```
IDebugProcessSecurity : IUnknown
```

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IDebugProcessSecurity`.

|Metoda|Popis|
|------------|-----------------|
|[GetUserName](../../../extensibility/debugger/reference/idebugprocesssecurity-getusername.md)|Získá uživatelské jméno od dodavatele portu.|
|[QueryCanSafelyAttach](../../../extensibility/debugger/reference/idebugprocesssecurity-querycansafelyattach.md)|Uživatele upozorňuje, že není bezpečné připojení k ladění procesu.|

## <a name="remarks"></a>Poznámky
 Implementace tohoto rozhraní zobrazí upozornění a umožnění uživateli zrušit, pokud proces, ke kterému se připojuje může považovány za nebezpečné.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Porty](../../../extensibility/debugger/ports.md)
- [Dodavatelé portů](../../../extensibility/debugger/port-suppliers.md)
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)