---
title: IDebugProgram2::Execute | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgram2::Execute
helpviewer_keywords: IDebugProgram2::Execute
ms.assetid: f7205ce8-0ac6-4fcd-b6ec-b720b4fcaccf
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: be6a1f1b2259b573b829490d6015eb1964790679
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprogram2execute"></a>IDebugProgram2::Execute
Dál spuštěním tohoto programu z zastaveném stavu. Všechny předchozí stav spuštění (například krok) není zaškrtnuto, a program se spustí provádění znovu.  
  
> [!NOTE]
>  Tato metoda je zastaralá. Použití [Execute](../../../extensibility/debugger/reference/idebugprocess3-execute.md) metoda místo.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Execute(  
   void  
);  
```  
  
```csharp  
int Execute();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Když uživatel spustí provádění z zastaveném stavu, v některých jiných programu přístup z více vláken, tato metoda je volána v této aplikaci. Tato metoda je volána, i když uživatel vybere **spustit** příkaz **ladění** nabídky v prostředí IDE. Implementace této metody může být stejně jednoduché jako volání [obnovit](../../../extensibility/debugger/reference/idebugthread2-resume.md) metoda na aktuální vlákno v programu.  
  
> [!WARNING]
>  Neodesílat zastavení události nebo okamžitou (synchronní) události [událostí](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) při zpracování volání; v opačném případě ladicí program může přestat reagovat.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [Události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)   
 [Obnovení](../../../extensibility/debugger/reference/idebugthread2-resume.md)