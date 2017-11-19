---
title: IDebugProgram2::Step | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgram2::Step
helpviewer_keywords: IDebugProgram2::Step
ms.assetid: e4c2ffce-9810-4088-8162-eac9ef04f2a9
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d0e4b8533c1b6a14c61fc556f06594945037bbbd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprogram2step"></a>IDebugProgram2::Step
Provede krok.  
  
> [!NOTE]
>  Tato metoda je zastaralá. Použití [krok](../../../extensibility/debugger/reference/idebugprocess3-step.md) metoda místo.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Step(   
   IDebugThread2*  pThread,  
   STEPKIND        sk,  
   STEPUNIT        step  
);  
```  
  
```csharp  
int Step(   
   IDebugThread2  pThread,  
   enum_STEPKIND  sk,  
   enum_STEPUNIT  step  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pThread`  
 [v] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) objekt, který reprezentuje vlákno se stupeň.  
  
 `sk`  
 [v] Hodnota z [STEPKIND](../../../extensibility/debugger/reference/stepkind.md) výčet, který určuje typ kroku.  
  
 `step`  
 [v] Hodnota z [STEPUNIT](../../../extensibility/debugger/reference/stepunit.md) výčet, který určuje tuto jednotku kroku (například pomocí příkazu nebo instrukce).  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 V případě, že je všechny synchronizace vláken nebo komunikace mezi vlákny, jiná vlákna v programu měli spustit, když je krokování s konkrétní vlákno.  
  
> [!WARNING]
>  Neodesílat zastavení události nebo okamžitou (synchronní) události [událostí](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) při zpracování volání; v opačném případě ladicí program může přestat reagovat.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [Události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)