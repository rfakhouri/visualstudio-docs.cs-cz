---
title: IDebugProgramHost2::GetHostId | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProgramHost2::GetHostId
helpviewer_keywords:
- IDebugProgramHost2::GetHostId
ms.assetid: 7702e221-feb1-446b-a224-cb46c420987e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: db729c87c4644862d203400b006e76c8d8b7c031
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53875482"
---
# <a name="idebugprogramhost2gethostid"></a>IDebugProgramHost2::GetHostId
Získá identifikátor procesu procesu, který je hostitelem tohoto programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetHostId(   
   AD_PROCESS_ID* pdwId  
);  
```  
  
```csharp  
int GetHostId(   
   AD_PROCESS_ID[] pdwId  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pdwId`  
 [out v] [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) struktura, která se vyplní informace o identifikátor procesu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgramHost2](../../../extensibility/debugger/reference/idebugprogramhost2.md)   
 [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)