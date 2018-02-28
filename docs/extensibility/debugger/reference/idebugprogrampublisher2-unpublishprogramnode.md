---
title: IDebugProgramPublisher2::UnpublishProgramNode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugProgramPublisher2::UnpublishProgramNode
helpviewer_keywords:
- IDebugProgramPublisher2::UnpublishProgramNode
ms.assetid: 57c7e6e1-b84e-4e14-ad83-cbbb64e2f526
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 58431059c3afdf392e6ebc5eb9c3d1b3c6f93ddc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogrampublisher2unpublishprogramnode"></a>IDebugProgramPublisher2::UnpublishProgramNode
Odebere zadaný program uzel dostupnost pro ladění moduly (DEs) a správce ladicí relace (SDM).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT UnpublishProgramNode(  
   IDebugProgramNode2* pProgramNode  
);  
```  
  
```csharp  
int UnpublishProgramNode(  
   IDebugProgramNode2 pProgramNode  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pProgramNode`  
 [v] [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) objekt reprezentující uzlu program, který je právě odebírán.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Po odebrání uzlu program již není k dispozici pro dotázat na informace o programu.  
  
 Chcete-li program uzel k dispozici, volání [PublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogramnode.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgramPublisher2](../../../extensibility/debugger/reference/idebugprogrampublisher2.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [PublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogramnode.md)