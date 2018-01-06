---
title: IDebugBreakpointChecksumRequest2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugBreakpointChecksumRequest2 interface
ms.assetid: 9cfdbca5-052c-48e9-8411-e2e9e4065d00
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 51fbcd168500c2ba2cd508b2a9b282896613dd64
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugbreakpointchecksumrequest2"></a>IDebugBreakpointChecksumRequest2
Představuje kontrolní součet dokumentu pro žádost o zarážek.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugBreakpointChecksumRequest2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Implementovaná pomocí [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] ladění balíčku a spotřebovávají ladění moduly.  
  
## <a name="methods"></a>Metody  
 Následující tabulka uvádí metody `IDebugBreakpointChecksumRequest2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetChecksum](../../../extensibility/debugger/reference/idebugbreakpointchecksumrequest2-getchecksum.md)|Načte kontrolního součtu dokumentu pro žádost zarážek zadaný jedinečný identifikátor algoritmu kontrolního součtu používat.|  
|[IsChecksumEnabled](../../../extensibility/debugger/reference/idebugbreakpointchecksumrequest2-ischecksumenabled.md)|Určuje, zda je povoleno kontrolního součtu tohoto dokumentu.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll