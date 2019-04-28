---
title: IDebugProgramHost2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramHost2
helpviewer_keywords:
- IDebugProgramHost2 interface
ms.assetid: 2c37b3aa-97a9-4665-8709-edd917f18cb1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: dadbd74480c990c4e7317244ec225d775347a6c2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62916859"
---
# <a name="idebugprogramhost2"></a>IDebugProgramHost2
Toto rozhraní poskytuje informace o hostiteli (proces) o programu.

## <a name="syntax"></a>Syntaxe

```
IDebugProgramHost2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Ladicí stroj implementuje toto rozhraní na stejný objekt jako [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) rozhraní pro zadání informací o hostitelský proces. Toto je volitelné rozhraní.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Volání [QueryInterface](/cpp/atl/queryinterface) na `IDebugProgram2` rozhraní k získání tohoto rozhraní.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IDebugProgramHost2`.

|Metoda|Popis|
|------------|-----------------|
|[GetHostName](../../../extensibility/debugger/reference/idebugprogramhost2-gethostname.md)|Získá název, popisný název nebo název souboru hostitelského procesu tohoto programu.|
|[GetHostId](../../../extensibility/debugger/reference/idebugprogramhost2-gethostid.md)|Získá identifikátor procesu hostitelský proces tohoto programu.|
|[GetHostMachineName](../../../extensibility/debugger/reference/idebugprogramhost2-gethostmachinename.md)|Získá název počítače, který hostitelský proces tento program běží na.|

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)