---
title: IDebugThread2::GetName | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugThread2::GetName
helpviewer_keywords: IDebugThread2::GetName
ms.assetid: eec54b8f-4a0e-4919-b0f9-81d4bd1e0b6f
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1c608c01b788c88385814fced4fae99d267e96f4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugthread2getname"></a>IDebugThread2::GetName
Získá název vlákna.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetName (   
   BSTR* pbstrName  
);  
```  
  
```csharp  
int GetName (   
   out string pbstrName  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pbstrName`  
 [out] Vrací název vlákno.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Načtený název je vždy název, který lze zobrazit a tento název popisuje vlákno. Název vlákna může být odvozen od spuštění architektura podporuje s názvem vláken, nebo může být název odvozené z modulu ladění. Alternativně lze nastavit název vlákno voláním [setthreadname –](../../../extensibility/debugger/reference/idebugthread2-setthreadname.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [Setthreadname –](../../../extensibility/debugger/reference/idebugthread2-setthreadname.md)