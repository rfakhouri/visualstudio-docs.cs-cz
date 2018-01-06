---
title: IDebugProgram3::ExecuteOnThread | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugProgram3::ExecuteOnThread
ms.assetid: 2f5211e3-7a3f-47bf-9595-dfc8b4895d0d
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 649b16c1b57b2f66772c2117b776e6b79ad862be
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogram3executeonthread"></a>IDebugProgram3::ExecuteOnThread
Spustí program ladicí program. Vlákno je vrácen do poskytnout ladicí program informace, na které vlákno je uživatel zobrazení při provádění programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT ExecuteOnThread(  
   [in] IDebugThread2* pThread)  
```  
  
```csharp  
int ExecuteOnThread(  
   IDebugThread2 pThread  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pThread`  
 [v] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Existují tři různé způsoby, aby ladicí program může pokračovat v provádění po zastavení:  
  
-   Spusťte: Zrušte všechny předchozí krok a běžet, dokud další zarážek a tak dále.  
  
-   Krok: Zrušit žádné staré krok a spustit až po dokončení kroku nového.  
  
-   Pokračovat: Spusťte znovu a ponechání aktivní žádné staré krok.  
  
 Vlákno předaný `ExecuteOnThread` je užitečné, když při rozhodování o tom, který krok zrušit. Pokud si nejste jisti, vlákno spuštěna provést zruší všechny kroky. S znalostmi vlákno stačí zrušit kroku na aktivních vláken.  
  
## <a name="see-also"></a>Viz také  
 [Spuštění](../../../extensibility/debugger/reference/idebugprogram2-execute.md)   
 [IDebugProgram3](../../../extensibility/debugger/reference/idebugprogram3.md)