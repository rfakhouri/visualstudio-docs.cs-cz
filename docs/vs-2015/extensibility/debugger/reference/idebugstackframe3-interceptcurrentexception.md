---
title: IDebugStackFrame3::InterceptCurrentException | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugStackFrame3::InterceptCurrentException
helpviewer_keywords:
- IDebugStackFrame3::InterceptCurrentException
ms.assetid: 116c7324-7645-4c15-b484-7a5cdd065ef5
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 42472690431d48a9baafbb0abee27c1a07d24fcd
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63428693"
---
# <a name="idebugstackframe3interceptcurrentexception"></a>IDebugStackFrame3::InterceptCurrentException
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Voláno rozhraním ladicího programu na aktuální rámec zásobníku, když chce zachytit aktuální výjimku.  
  
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
 [in] Určuje různé akce. V současné době pouze [INTERCEPT_EXCEPTION_ACTION](../../../extensibility/debugger/reference/intercept-exception-action.md) hodnotu `IEA_INTERCEPT` je podporován a musí být zadán.  
  
 `pqwCookie`  
 [out] Jedinečná hodnota identifikaci konkrétní výjimce.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.  
  
 Následují nejčastější vrátí chyba.  
  
|Chyba|Popis|  
|-----------|-----------------|  
|`E_EXCEPTION_CANNOT_BE_INTERCEPTED`|Nelze zachytit aktuální výjimku.|  
|`E_EXCEPTION_CANNOT_UNWIND_ABOVE_CALLBACK`|Aktuální rámec provádění ještě nebyl byla prohledána pro obslužnou rutinu.|  
|`E_INTERCEPT_CURRENT_EXCEPTION_NOT_SUPPORTED`|Tato metoda není podporována pro tento rámec.|  
  
## <a name="remarks"></a>Poznámky  
 Když dojde k výjimce, ladicí program získá kontrolu v době běhu na klíčových místech během zpracování procesu výjimek. Během těchto klíčových momentů ladicí program můžete požádat o aktuální rámec zásobníku Pokud rámce chce zachytit výjimku. Tímto způsobem zachycené výjimky je v podstatě na průběžné obslužné rutiny výjimky pro blok zásobníku i v případě, že rámec zásobníku nemá obslužné rutiny výjimky (například bloku try/catch v kódu programu).  
  
 Pokud ladicí program se chce vědět, pokud by měl být zachycena výjimka, volá tuto metodu na aktuální objekt rámce zásobníku. Tato metoda je zodpovědná za zpracování všech podrobnosti o výjimce. Pokud [IDebugStackFrame3](../../../extensibility/debugger/reference/idebugstackframe3.md) rozhraní není implementováno nebo `InterceptStackException` metoda vrátí všechny chyby, bude ladicí program pokračovat, obvykle zpracování výjimky.  
  
> [!NOTE]
> Výjimky mohou být zachyceny pouze ve spravovaném kódu, to znamená, že při spuštění programu, který se právě ladí v .NET, dobu běhu. Samozřejmě můžete implementovat třetích stran jazyk implementátory `InterceptStackException` ve své vlastní ladicími stroji, pokud se tedy rozhodne.  
  
 Po dokončení zachycení [IDebugInterceptExceptionCompleteEvent2](../../../extensibility/debugger/reference/idebuginterceptexceptioncompleteevent2.md) signalizován.  
  
## <a name="see-also"></a>Viz také  
 [IDebugStackFrame3](../../../extensibility/debugger/reference/idebugstackframe3.md)   
 [INTERCEPT_EXCEPTION_ACTION](../../../extensibility/debugger/reference/intercept-exception-action.md)   
 [IDebugInterceptExceptionCompleteEvent2](../../../extensibility/debugger/reference/idebuginterceptexceptioncompleteevent2.md)
