---
title: IDebugProgram2::Continue | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::Continue
helpviewer_keywords:
- IDebugProgram2::Continue
ms.assetid: e5a6e02a-d21b-4a03-a034-e8de1f71ce2e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f52fccf640cca32d4291b3d6fb8626c38370ded3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprogram2continue"></a>IDebugProgram2::Continue
Dál spuštěním tohoto programu z zastaveném stavu. Uchování jakékoli předchozí stav spuštění (například krok), a program se spustí provádění znovu.  
  
> [!NOTE]
>  Tato metoda je zastaralá. Použití [pokračovat](../../../extensibility/debugger/reference/idebugprocess3-continue.md) metoda místo.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Continue(   
   IDebugThread2* pThread  
);  
```  
  
```csharp  
int Continue(   
   IDebugThread2 pThread  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pThread`  
 [v] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) objekt, který reprezentuje vlákno.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je volána na tento program bez ohledu na to, kolik programy se právě ladí nebo program, který vygeneruje událost zastavit. Implementace musí zachovat předchozí stav spuštění (například krok) a pokračovat v provádění, jako by měl nikdy zastaven před dokončením vykonávání předchozí. To znamená, pokud vlákna v tento program dělal operaci krok převzetí a byla zastavena, protože některé jiný program zastaví, a pak se tato metoda volána, program musí původní krok přes operaci dokončit.  
  
> [!WARNING]
>  Neodesílat zastavení události nebo okamžitou (synchronní) události [událostí](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) při zpracování volání; v opačném případě ladicí program může přestat reagovat.  
  
## <a name="see-also"></a>Viz také  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [Události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)