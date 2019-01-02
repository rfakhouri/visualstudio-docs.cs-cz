---
title: IDebugEngine2::CauseBreak | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugEngine2::CauseBreak
helpviewer_keywords:
- IDebugEngine2::CauseBreak
ms.assetid: 17fe4698-b04e-4798-8412-80e0da60c387
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1d0c3862468d5ad1a9c548297a69d9ae10521e59
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53964374"
---
# <a name="idebugengine2causebreak"></a>IDebugEngine2::CauseBreak
Požadavky, že všechny programy právě laděny ve tento ladicí stroj (DE) pro zastavení provádění příště, jeden z jejich vláken pokusí o spuštění.  
  
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
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je asynchronní: [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md) události se odešle, když program další pokusy o spuštění po volání této metody.  
  
## <a name="see-also"></a>Viz také  
 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)   
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)