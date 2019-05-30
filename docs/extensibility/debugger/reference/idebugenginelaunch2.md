---
title: IDebugEngineLaunch2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngineLaunch2
helpviewer_keywords:
- IDebugEngineLaunch2 interface
ms.assetid: 5eaf2ad8-3fbf-446e-b48b-5327ad3f5255
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4b6f59c9444b0c54f8a230f8eb4487e16b65ebf4
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66345226"
---
# <a name="idebugenginelaunch2"></a>IDebugEngineLaunch2
Ladicí stroj (DE) používá ke spuštění a ukončení aplikace.

## <a name="syntax"></a>Syntaxe

```
IDebugEngineLaunch2 : IDebugEngine2
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Toto rozhraní implementují vlastní DE v případě, že má zvláštní požadavky na spouštění procesu, který nelze zpracovat zcela port. Tento vlastní port. To je obvykle tento případ, když je DE je součástí interpretu a laděný proces je skript: interpretu je potřeba nejdřív spustit, a pak je načíst skript a je spuštěna. Port můžete spustit interpret, ale skript může vyžadovat zvláštní zpracování (což je, kde je DE má roli). Toto rozhraní je implementováno pouze v případě, že existují jedinečným požadavkům pro spuštění programu, který nemůže zpracovávat port. Tento vlastní port.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Toto rozhraní je volán Správce ladění relace (SDM) Pokud SDM můžete získat toto rozhraní z [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) rozhraní (pomocí funkce QueryInterface). Pokud toto rozhraní můžete získat, SDM ví, že je DE má zvláštní požadavky a volá tato rozhraní ke spuštění programu nemuseli port, spusťte ji.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IDebugEngineLaunch2`.

|Metoda|Popis|
|------------|-----------------|
|[LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)|Prostřednictvím DE spustí nějaký proces.|
|[ResumeProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md)|Obnoví spuštění procesu.|
|[CanTerminateProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-canterminateprocess.md)|Určuje, pokud lze ukončit proces.|
|[TerminateProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-terminateprocess.md)|Ukončení procesu.|

## <a name="requirements"></a>Požadavky
 Záhlaví: Msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)