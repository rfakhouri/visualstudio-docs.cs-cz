---
title: IDebugStackFrame3::InterceptCurrentException | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugStackFrame3::InterceptCurrentException
helpviewer_keywords:
- IDebugStackFrame3::InterceptCurrentException
ms.assetid: 116c7324-7645-4c15-b484-7a5cdd065ef5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d46ae2f3ae0c63c798fc42b93d50e5aee398ccf5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugstackframe3interceptcurrentexception"></a>IDebugStackFrame3::InterceptCurrentException
Voláno rozhraním ladicí program na aktuální rámec zásobníku, když chce intercept aktuální výjimku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT InterceptCurrentException(  
   INTERCEPT_EXCEPTION_ACTION dwFlags,  
   UINT64*                    pqwCookie  
);  
```  
  
```csharp  
int InterceptCurrentException(  
   uint dwFlags,   
   out  ulong pqwCookie  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwFlags`  
 [v] Určuje různé akce. V současné době pouze [INTERCEPT_EXCEPTION_ACTION](../../../extensibility/debugger/reference/intercept-exception-action.md) hodnota `IEA_INTERCEPT` je podporována a musí být zadán.  
  
 `pqwCookie`  
 [out] Identifikace konkrétní výjimka jedinečnou hodnotu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; jinak vrátí kód chyby.  
  
 Níže jsou uvedeny nejčastější vrátí chyba.  
  
|Chyba|Popis|  
|-----------|-----------------|  
|`E_EXCEPTION_CANNOT_BE_INTERCEPTED`|Nemůže být zachyceny aktuální výjimku.|  
|`E_EXCEPTION_CANNOT_UNWIND_ABOVE_CALLBACK`|Aktuální rámec provádění ještě nebyl byla prohledána pro obslužnou rutinu.|  
|`E_INTERCEPT_CURRENT_EXCEPTION_NOT_SUPPORTED`|Tato metoda není podporovaná pro tento snímek.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud je vyvolána výjimka, ladicí program získá kontrolu z čas spuštění na klíčové body během zpracování procesu výjimek. Během těchto klíčů situacích ladicího programu požádejte aktuální rámec zásobníku Pokud rámečku chce zachytávat výjimky. Tímto způsobem zachycené výjimky je v podstatě na průběžně obslužné rutiny výjimek pro rámce zásobníku, i v případě, že rámce zásobníku nemá obslužné rutiny výjimek (například bloku try/catch v kódu programu).  
  
 Po ladicího programu chce vědět, pokud by měl být zachyceny výjimku, zavolá tato metoda u aktuálního objektu rámce zásobníku. Tato metoda je zodpovědná za zpracování všech podrobností o výjimky. Pokud [IDebugStackFrame3](../../../extensibility/debugger/reference/idebugstackframe3.md) rozhraní není implementováno nebo `InterceptStackException` metoda vrátí všechny chyby, bude ladicího programu pokračovat zpracování výjimky normálně.  
  
> [!NOTE]
>  Výjimky mohou být zachyceny jenom ve spravovaném kódu, který je při spuštění programu laděné v rozhraní .NET čas spuštění. Samozřejmě můžete implementovat třetích stran jazyk implementátory `InterceptStackException` ve vlastní moduly ladění, pokud se tak rozhodne.  
  
 Po dokončení zachycení [IDebugInterceptExceptionCompleteEvent2](../../../extensibility/debugger/reference/idebuginterceptexceptioncompleteevent2.md) signalizace.  
  
## <a name="see-also"></a>Viz také  
 [IDebugStackFrame3](../../../extensibility/debugger/reference/idebugstackframe3.md)   
 [INTERCEPT_EXCEPTION_ACTION](../../../extensibility/debugger/reference/intercept-exception-action.md)   
 [IDebugInterceptExceptionCompleteEvent2](../../../extensibility/debugger/reference/idebuginterceptexceptioncompleteevent2.md)