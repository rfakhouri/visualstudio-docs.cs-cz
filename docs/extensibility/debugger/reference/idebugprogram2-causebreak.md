---
title: IDebugProgram2::CauseBreak | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugProgram2::CauseBreak
helpviewer_keywords:
- IDebugProgram2::CauseBreak
ms.assetid: 07d353fc-68ab-4297-a18f-3d3c7a80e121
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 48029ed4e925073b0d121a88846aa2f0af0a51cc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogram2causebreak"></a>IDebugProgram2::CauseBreak
Požadavky, že program zastavit provádění další čas jeden z jeho vláken pokusí spustit.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT CauseBreak(   
   void   
);  
```  
  
```csharp  
int CauseBreak();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md) událost je odeslána, když se program vedle pokusí spustit kód po tato metoda je volána.  
  
 Tato metoda se asynchronní, že metoda vrátí okamžitě bez čekání na nutně ukončení programu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)