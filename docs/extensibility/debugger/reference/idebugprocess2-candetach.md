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
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 21fc550482021397e219e685074a9cc9c6e6c837
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55015573"
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