---
title: IDebugProgramEngines2::SetEngine | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProgramEngines2::SetEngine
helpviewer_keywords:
- IDebugProgramEngines2::SetEngine
ms.assetid: c05857ee-89cf-455e-8f1e-300cce4a2eab
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8c77cffc8b30d09e4136c6bdd94f30da85a4a77b
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53916056"
---
# <a name="idebugprogramengines2setengine"></a>IDebugProgramEngines2::SetEngine
Říká program nebo program uzel které ladicího stroje (DE) použít pro ladění tohoto programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT SetEngine(   
   REFGUID guidEngine  
);  
```  
  
```csharp  
int SetEngine(   
   ref Guid guidEngine  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `guidEngine`  
 [in] Identifikátor GUID je DE.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgramEngines2](../../../extensibility/debugger/reference/idebugprogramengines2.md)