---
title: IDebugProgramDestroyEvent2::GetExitCode | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProgramDestroyEvent2::GetExitCode
helpviewer_keywords:
- IDebugProgramDestroyEvent2::GetExitCode
ms.assetid: 7f540cf6-e2d1-42b0-913e-a26d654b7659
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 60b3cc7f05093a2cc0d5b414a53dcfd25edac57d
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54934371"
---
# <a name="idebugprogramdestroyevent2getexitcode"></a>IDebugProgramDestroyEvent2::GetExitCode
Získá ukončovací kód programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetExitCode(   
   DWORD* pdwExit  
);  
```  
  
```csharp  
int GetExitCode(   
   out uint pdwExit  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pdwExit`  
 [out] Vrátí ukončovací kód programu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgramDestroyEvent2](../../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)