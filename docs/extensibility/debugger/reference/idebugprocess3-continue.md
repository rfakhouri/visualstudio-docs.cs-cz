---
title: IDebugProcess3::Continue | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProcess3::Continue
helpviewer_keywords:
- IDebugProcess3::Continue
ms.assetid: 57506242-5763-4c08-adb9-8a78ce02cebb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 38bb11237d5016e3747c5a615e61144511c17fad
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31117475"
---
# <a name="idebugprocess3continue"></a>IDebugProcess3::Continue
Pokračuje v spuštění tohoto procesu z zastaveném stavu. Uchování jakékoli předchozí stav spuštění (například krok), a tento proces se spustí provádění znovu.  
  
> [!NOTE]
>  Tato metoda by měla použít místo [pokračovat](../../../extensibility/debugger/reference/idebugprogram2-continue.md).  
  
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
 [v] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) objekt reprezentující vlákno pokračovat.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je volána pro tento postup, bez ohledu na to, jak velký počet procesů se právě ladí nebo které proces vygenerovat událost zastavit. Implementace musí zachovat předchozí stav spuštění (například krok) a pokračovat v provádění, jako by měl nikdy zastaven před dokončením vykonávání předchozí. To znamená, pokud vlákna v tento proces dělal operaci krok převzetí a byla zastavena, protože byl zastaven jiný proces a potom `Continue` byla volána, zadaný vlákno musí dokončit operaci původní krok over.  
  
 **Upozornění** Neodesílat zastavení události nebo okamžitou (synchronní) události [událostí](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) při zpracování volání; v opačném případě ladicí program může přestat reagovat.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [Události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)