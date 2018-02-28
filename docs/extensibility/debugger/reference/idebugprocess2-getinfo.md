---
title: IDebugProcess2::GetInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugProcess2::GetInfo
helpviewer_keywords:
- IDebugProcess2::GetInfo
ms.assetid: 46021dce-bb97-46c3-b0cc-e5b3b68acc35
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 7d466c9cd1ea0ea98d736cabbb612a3d28c7fb99
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprocess2getinfo"></a>IDebugProcess2::GetInfo
Získá popis procesu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetInfo(  
   PROCESS_INFO_FIELDS  Fields,  
   PROCESS_INFO*        pProcessInfo  
);  
```  
  
```csharp  
int GetInfo(  
   enum_PROCESS_INFO_FIELDS  Fields,  
   PROCESS_INFO[]            pProcessInfo  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `Fields`  
 [v] Kombinace hodnot z [PROCESS_INFO_FIELDS](../../../extensibility/debugger/reference/process-info-fields.md) výčet, který určuje, které pole `pProcessInfo` parametr mají být vyplněna.  
  
 `pProcessInfo`  
 [out] A [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md) struktura, která obsahuje popis procesu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [PROCESS_INFO_FIELDS](../../../extensibility/debugger/reference/process-info-fields.md)   
 [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)