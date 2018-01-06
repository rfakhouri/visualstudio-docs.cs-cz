---
title: IDebugThread2::Suspend | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugThread2::Suspend
helpviewer_keywords: IDebugThread2::Suspend
ms.assetid: 1e20be85-aa12-48de-bb83-0bf0976e99ae
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 3d7bf2c3673a5e3ca032e66215b130487d219b65
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugthread2suspend"></a>IDebugThread2::Suspend
Pozastaví vlákna.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Suspend (   
   DWORD *pdwSuspendCount  
);  
```  
  
```csharp  
HRESULT Suspend (   
   out uint pdwSuspendCount  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pdwSuspendCount`  
 [out] Vrátí počet pozastavit po operaci pozastavit.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Každé volání této metody zvýší počet pozastavit větší než 0. Tento počet pozastavit se zobrazí v **vláken** okno ladění.  
  
 Pro každé volání tuto metodu, musí být novější volání [obnovit](../../../extensibility/debugger/reference/idebugthread2-resume.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [Obnovení](../../../extensibility/debugger/reference/idebugthread2-resume.md)