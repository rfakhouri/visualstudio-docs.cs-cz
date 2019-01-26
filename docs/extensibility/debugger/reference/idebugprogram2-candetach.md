---
title: IDebugProgram2::CanDetach | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::CanDetach
helpviewer_keywords:
- IDebugProgram2::CanDetach
ms.assetid: dcd9ab6c-49e5-447e-aa7c-89f571f4a052
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 61e19d5d5eedef2837db7b1dbf56fe301c115509
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54950015"
---
# <a name="idebugprogram2candetach"></a>IDebugProgram2::CanDetach
Určuje, pokud ladicí stroj (DE) můžete odpojit od programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT CanDetach(  
   void  
);  
```  
  
```csharp  
int CanDetach();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud můžete odpojit, vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrátí `S_FALSE` Pokud DE nelze odpojit od programu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)