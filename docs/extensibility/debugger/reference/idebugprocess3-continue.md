---
title: IDebugProcess3::Continue | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProcess3::Continue
helpviewer_keywords: IDebugProcess3::Continue
ms.assetid: 57506242-5763-4c08-adb9-8a78ce02cebb
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d748d7ab60efdb7f9f3e17070c3292b25ebc38ee
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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