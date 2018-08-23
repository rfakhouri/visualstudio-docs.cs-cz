---
title: IDebugCodeContext3 | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugCodeContext3 interface
ms.assetid: 524eb882-0ad5-4bfb-95eb-eb3abb3d0237
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7064cddbf81a01e7d55d64249d4ff4da6e585728
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42672486"
---
# <a name="idebugcodecontext3"></a>IDebugCodeContext3
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugCodeContext3](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugcodecontext3).  
  
Rozšiřuje [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) rozhraní povolit načtení modulu a proces rozhraní.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugCodeContext3 : IDebugCodeContext2  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Pomocí ladicími stroji implementovat a používat [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] ladit balíček.  
  
## <a name="methods"></a>Metody  
 Kromě metod na `IDebugCodeContext2` rozhraní, toto rozhraní implementuje následujících metod:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Getmodule –](../../../extensibility/debugger/reference/idebugcodecontext3-getmodule.md)|Získá odkaz na rozhraní modulu ladění.|  
|[Getprocess –](../../../extensibility/debugger/reference/idebugcodecontext3-getprocess.md)|Získá referenci k rozhraní ladění procesu.|  
  
## <a name="remarks"></a>Poznámky  
 Toto je volitelné rozhraní, která obvykle není nutné implementovat.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

