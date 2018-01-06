---
title: IDebugThread2::SetNextStatement | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugThread2::SetNextStatement
helpviewer_keywords: IDebugThread2::SetNextStatement
ms.assetid: 9e2834dd-4ecf-45af-8e6c-f9318ebdac06
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 6c70c1c1d3e525ccc676554d3b40df224423e313
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugthread2setnextstatement"></a>IDebugThread2::SetNextStatement
Nastaví aktuální ukazatel instrukce v kontextu daného kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT SetNextStatement (   
   IDebugStackFrame2*  pStackFrame,  
   IDebugCodeContext2* pCodeContext  
);  
```  
  
```csharp  
int SetNextStatement (   
   IDebugStackFrame2  pStackFrame,  
   IDebugCodeContext2 pCodeContext  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pStackFrame`  
 Vyhrazeno pro budoucí použití; Nastavte na hodnotu null.  
  
 `pCodeContext`  
 [v] [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) objekt, který popisuje kód umístění chystáte provést a jeho kontextu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby. V následující tabulce jsou uvedeny další možné hodnoty.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|E_CANNOT_SET_NEXT_STATEMENT_ON_NONLEAF_FRAME|Další příkaz nemůže být v zásobníku hlubší v rámce zásobníku.|  
|E_CANNOT_SETIP_TO_DIFFERENT_FUNCTION|Další příkaz není přidružený žádné rámce v zásobníku.|  
|E_CANNOT_SET_NEXT_STATEMENT_ON_EXCEPTION|Některé moduly ladění nelze nastavit další příkaz po výjimce.|  
  
## <a name="remarks"></a>Poznámky  
 Ukazatel instrukce označuje další instrukce nebo příkaz provést. Tato metoda se používá, opakujte řádek zdrojového kódu a vynutit spuštění, chcete-li pokračovat v jiné funkci, například.  
  
## <a name="see-also"></a>Viz také  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)