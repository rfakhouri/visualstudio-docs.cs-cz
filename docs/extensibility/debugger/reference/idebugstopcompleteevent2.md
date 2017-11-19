---
title: IDebugStopCompleteEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugStopCompleteEvent2 interface
ms.assetid: ff3e89f4-61bb-489d-901c-447260100218
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2e92138f969189a33e1a5aad5a083c8ac57852dc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugstopcompleteevent2"></a>IDebugStopCompleteEvent2
Modul ladění (DE) může poslat této události volitelné pro relaci ladění správce (SDM), pokud program byla zastavena.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugStopCompleteEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Jedná se o nové rozhraní pro [!INCLUDE[vsprvslong](../../../code-quality/includes/vsprvslong_md.md)]. Předchozí verze nepodporuje asynchronní zastavit.  
  
 [Zastavit](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) volá SDM ve scénářích více procesů nebo více program. V případě, že jeden program odesílá události zastavení SDM, požaduje SDM ostatních programů příliš zastavit.  
  
 Slouží k informování asynchronně SDM, který program byla zastavena. To je užitečné pro modul překladač ladění, kde někdy žádný kód běží uvnitř vyladěnou program, takže [Zastavit](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) nelze dokončit, synchronně. Pokud modul ladění chce využít toto asynchronní oznámení, musí vracet `S_ASYNC_STOP` z [Zastavit](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md).  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll