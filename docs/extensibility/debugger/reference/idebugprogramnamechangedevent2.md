---
title: IDebugProgramNameChangedEvent2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugProgramNameChangedEvent2 interface
ms.assetid: be1f1cd5-0b2f-435c-a052-dca28a7c978d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b4bbf66a7b284bbf6b5123c1c7266d032ba5001f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62869924"
---
# <a name="idebugprogramnamechangedevent2"></a>IDebugProgramNameChangedEvent2
Odesílat ladicího stroje (DE) Správce ladění relace (SDM) Pokud se změní název programu.

## <a name="syntax"></a>Syntaxe

```
IDebugProgramNameChangedEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 DE implementuje toto rozhraní do sestavy, které se změnily název programu. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) na stejný objekt jako toto rozhraní musí implementovat rozhraní. Používá SDM [QueryInterface](/cpp/atl/queryinterface) přístup **IDebugEvent2** rozhraní.

## <a name="notes-for-callers"></a>Poznámky pro volající
 DE vytvoří a odešle tento objekt událostí k hlášení o změnu názvu programu. DE posílání této události [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) funkce zpětného volání, který poskytl SDM při připojení k laděnému programu. Dodavatel port. Tento vlastní port odešle tato událost pomocí I rozhraní.

## <a name="requirements"></a>Požadavky
 Záhlaví: Msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll