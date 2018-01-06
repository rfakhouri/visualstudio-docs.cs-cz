---
title: IDebugCodeContext3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugCodeContext3 interface
ms.assetid: 524eb882-0ad5-4bfb-95eb-eb3abb3d0237
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 364b7d1480449601b211e5ac1736d0d85a87da5d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcodecontext3"></a>IDebugCodeContext3
Rozšiřuje [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) rozhraní, abyste umožnili načtení modulu a proces rozhraní.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugCodeContext3 : IDebugCodeContext2  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Implementované moduly ladění a spotřebovávají [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] ladění balíčku.  
  
## <a name="methods"></a>Metody  
 Kromě metod na `IDebugCodeContext2` rozhraní, toto rozhraní implementuje následujících metod:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Getmodule –](../../../extensibility/debugger/reference/idebugcodecontext3-getmodule.md)|Získá odkaz na rozhraní modulu ladění.|  
|[Getprocess –](../../../extensibility/debugger/reference/idebugcodecontext3-getprocess.md)|Získá odkaz na rozhraní procesu ladění.|  
  
## <a name="remarks"></a>Poznámky  
 Toto je volitelné rozhraní, která obvykle nemá k implementaci.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll