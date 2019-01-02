---
title: IDebugProgram2::CauseBreak | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::CauseBreak
helpviewer_keywords:
- IDebugProgram2::CauseBreak
ms.assetid: 07d353fc-68ab-4297-a18f-3d3c7a80e121
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c0e30e90aa1778904bc6c6349427c567ea3bb160
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53829667"
---
# <a name="idebugprogram2causebreak"></a>IDebugProgram2::CauseBreak
Požadavky, že program zastavit provádění na další čas, po jednu z jeho vlákna pokusy o spuštění.  
  
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
 [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md) události se odešle, když program dále pokusí o spuštění kódu po volání této metody.  
  
 Tato metoda je asynchronní metoda vrátí hodnotu okamžitě bez nutně čekání na ukončení programu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)