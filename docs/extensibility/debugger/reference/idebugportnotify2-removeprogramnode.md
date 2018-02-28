---
title: IDebugPortNotify2::RemoveProgramNode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugPortNotify2::RemoveProgramNode
helpviewer_keywords:
- IDebugPortNotify2::RemoveProgramNode
ms.assetid: 3668157b-66d2-416e-a359-fc04dcd18a48
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 8bd07eafde56cb9d753aeaf5911daeea9275b6a9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugportnotify2removeprogramnode"></a>IDebugPortNotify2::RemoveProgramNode
Zruší registraci program, který můžete ladit z port, který je spuštěn na.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT RemoveProgramNode(   
   IDebugProgramNode2* pProgramNode  
);  
```  
  
```csharp  
int RemoveProgramNode(   
   IDebugProgramNode2 pProgramNode  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pProgramNode`  
 [v] [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) objecy, který představuje program, který se zrušit registraci.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda odebere program uzlu, která byla přidána pomocí volání [AddProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [AddProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)