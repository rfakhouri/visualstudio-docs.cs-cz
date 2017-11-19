---
title: IDebugProgram2::GetProgramId | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgram2::GetProgramId
helpviewer_keywords: IDebugProgram2::GetProgramId
ms.assetid: 2c31c0aa-2b71-46c7-849c-356e237d26f8
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 094dde4330775b77a50ce98451fc9dafcd3bd23b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprogram2getprogramid"></a>IDebugProgram2::GetProgramId
Získá identifikátor GUID pro tento program.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetProgramId(   
   GUID* pguidProgramId  
);  
```  
  
```csharp  
int GetProgramId(   
   out Guid pguidProgramId  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pguidProgramId`  
 [out] Vrátí `GUID` pro tento program.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Modul ladění (DE) musí vrátit identifikátor program původně předána [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) nebo [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md) metody. To umožňuje identifikaci programu napříč ladicí program komponenty.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)   
 [Připojení](../../../extensibility/debugger/reference/idebugengine2-attach.md)