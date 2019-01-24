---
title: IDebugStopCompleteEvent2 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- IDebugStopCompleteEvent2 interface
ms.assetid: ff3e89f4-61bb-489d-901c-447260100218
caps.latest.revision: 7
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: a9c2a6a6e69bf47751706710801dd78c832ccd2c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54753663"
---
# <a name="idebugstopcompleteevent2"></a>IDebugStopCompleteEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Ladicí stroj (DE) můžete odeslat této události volitelné správce ladění relace (SDM) po zastavení programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugStopCompleteEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto je nové rozhraní pro [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]. Předchozí verze nepodporuje asynchronní zastavení.  
  
 [Zastavit](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) je volán SDM ve scénářích pro více procesů nebo více programů. Pokud jeden program odešle událostí ukončení SDM, SDM požádá o další programy zastavit příliš.  
  
 Používá se k asynchronně informovat SDM, program se zastavila. To je užitečné pro interpret ladicí modul, kde někdy žádný kód běží uvnitř laděného programu, takže [Zastavit](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) nemůže být dokončena synchronně. Pokud ladicí stroj chce využívat tato asynchronní oznámení, musí vracet `S_ASYNC_STOP` z [Zastavit](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md).  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll
