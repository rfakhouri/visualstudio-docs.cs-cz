---
title: IDebugProcess2::EnumThreads | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProcess2::EnumThreads
helpviewer_keywords: IDebugProcess2::EnumThreads
ms.assetid: 05677385-7a7f-4545-8438-af00dde85db0
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6e1cc33d1a84f5f8a3cd186b148f57e296a350f4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprocess2enumthreads"></a>IDebugProcess2::EnumThreads
Načte seznam všechna vlákna spuštěné v procesu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT EnumThreads(  
   IEnumDebugThreads2** ppEnum  
);  
```  
  
```csharp  
int EnumThreads(  
   out IEnumDebugThreads2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppEnum`  
 [out] Vrátí [IEnumDebugThreads2](../../../extensibility/debugger/reference/ienumdebugthreads2.md) objekt, který obsahuje seznam všech vláken ve všech aplikacích v procesu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vytvoří výčet vláken spuštěná v každém programu a kombinuje je do procesu zobrazení vláken. Jedno vlákno může spustit v několika programy; Tato metoda vytvoří výčet daném vláknu pouze jednou.  
  
 Tato metoda představuje seznam vlákna procesu bez duplicitní položky. Jinak se vytvořit výčet podprocesů spuštěných v určitém programu, použijte [enumthreads –](../../../extensibility/debugger/reference/idebugprogram2-enumthreads.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [IEnumDebugThreads2](../../../extensibility/debugger/reference/ienumdebugthreads2.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [Enumthreads –](../../../extensibility/debugger/reference/idebugprogram2-enumthreads.md)