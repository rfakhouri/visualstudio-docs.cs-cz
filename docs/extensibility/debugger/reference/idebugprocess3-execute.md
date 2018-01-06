---
title: IDebugProcess3::Execute | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProcess3::Execute
helpviewer_keywords: IDebugProcess3::Execute
ms.assetid: d831cd81-d7bf-4172-8517-aa699867791f
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 95dc4728c3c51dc8e206393ccb2a8f27f470a51b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprocess3execute"></a>IDebugProcess3::Execute
Pokračuje v spuštění tohoto procesu z zastaveném stavu. Všechny předchozí stav spuštění (například krok) je vymazán a proces se spustí provádění znovu.  
  
> [!NOTE]
>  Tato metoda by měla použít místo [Execute](../../../extensibility/debugger/reference/idebugprogram2-execute.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Execute(  
   IDebugThread2* pThread  
);  
```  
  
```csharp  
int Execute(  
   IDebugThread2 pThread  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pThread`  
 [v] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) objekt reprezentující vlákno k provedení.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Když uživatel spustí provádění z zastaveném stavu v jiný proces na vlákno, tato metoda je volána tohoto postupu. Tato metoda je volána, i když uživatel vybere **spustit** příkaz **ladění** nabídky v prostředí IDE. Implementace této metody může být stejně jednoduché jako volání [obnovit](../../../extensibility/debugger/reference/idebugthread2-resume.md) metoda na aktuální vlákno v procesu.  
  
> [!WARNING]
>  Neodesílat zastavení události nebo okamžitou (synchronní) události [událostí](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) při zpracování volání; v opačném případě ladicí program může přestat reagovat.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [Obnovení](../../../extensibility/debugger/reference/idebugthread2-resume.md)   
 [Události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)