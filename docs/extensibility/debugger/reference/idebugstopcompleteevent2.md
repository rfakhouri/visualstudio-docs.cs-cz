---
title: IDebugStopCompleteEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugStopCompleteEvent2 interface
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: aa8941decfb4e64906c57b719df711ce8779df9c
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2018
---
# <a name="idebugstopcompleteevent2"></a>IDebugStopCompleteEvent2

Modul ladění (DE) může poslat této události volitelné pro relaci ladění správce (SDM), pokud program byla zastavena.

## <a name="syntax"></a>Syntaxe

```
IDebugStopCompleteEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory

Toto rozhraní byla zavedena v systému Visual Studio 2005. Předchozí verze nepodporuje asynchronní zastavit.

[Zastavit](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) volá SDM ve scénářích více procesů nebo více program. V případě, že jeden program odesílá události zastavení SDM, požaduje SDM ostatních programů příliš zastavit.

Asynchronně informovat SDM, který program přestal slouží k zastavení. Informuje o SDM je užitečné pro modul překladač ladění, kde někdy žádný kód běží uvnitř vyladěnou programu, tak [Zastavit](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) nelze dokončit, synchronně. Pokud modul ladění chce využít toto asynchronní oznámení, musí vracet `S_ASYNC_STOP` z [Zastavit](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md).

## <a name="requirements"></a>Požadavky

Záhlaví: msdbg.h

Namespace: Microsoft.VisualStudio.Debugger.Interop

Assembly: Microsoft.VisualStudio.Debugger.Interop.dll