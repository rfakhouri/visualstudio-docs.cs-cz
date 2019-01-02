---
title: IDebugProcess2::CanDetach | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProcess2::CanDetach
helpviewer_keywords:
- IDebugProcess2::CanDetach
ms.assetid: 2830f7c3-69fb-474a-97b8-5b869e38d546
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f092fc0ec8467a6b78addff50b3d8d8f37ee29d5
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53962912"
---
# <a name="idebugprocess2candetach"></a>IDebugProcess2::CanDetach
Určuje, pokud správce ladění relace (SDM) můžete odpojit proces.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT CanDetach(  
   void  
);  
```  
  
```csharp  
int CanDetach();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK.` vrátí `S_FALSE` Pokud ladicí program nelze odpojit od procesu. V opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [CanDetach](../../../extensibility/debugger/reference/idebugprogram2-candetach.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)