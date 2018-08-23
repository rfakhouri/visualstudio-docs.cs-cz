---
title: IDebugEngineLaunch2 | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugEngineLaunch2
helpviewer_keywords:
- IDebugEngineLaunch2 interface
ms.assetid: 5eaf2ad8-3fbf-446e-b48b-5327ad3f5255
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3b4f70dac4d8831b02e458be3b8b4e38e5703b5d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667027"
---
# <a name="idebugenginelaunch2"></a>IDebugEngineLaunch2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugEngineLaunch2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugenginelaunch2).  
  
Ladicí stroj (DE) používá ke spuštění a ukončení aplikace.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugEngineLaunch2 : IDebugEngine2  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní implementují vlastní DE v případě, že má zvláštní požadavky na spouštění procesu, který nelze zpracovat zcela port. Tento vlastní port. To je obvykle tento případ, když je DE je součástí interpretu a laděný proces je skript: interpretu je potřeba nejdřív spustit, a pak je načíst skript a je spuštěna. Port můžete spustit interpret, ale skript může vyžadovat zvláštní zpracování (což je, kde je DE má roli). Toto rozhraní je implementováno pouze v případě, že existují jedinečným požadavkům pro spuštění programu, který nemůže zpracovávat port. Tento vlastní port.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní je volán Správce ladění relace (SDM) Pokud SDM můžete získat toto rozhraní z [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) rozhraní (pomocí funkce QueryInterface). Pokud toto rozhraní můžete získat, SDM ví, že je DE má zvláštní požadavky a volá tato rozhraní ke spuštění programu nemuseli port, spusťte ji.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugEngineLaunch2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)|Prostřednictvím DE spustí nějaký proces.|  
|[ResumeProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md)|Obnoví spuštění procesu.|  
|[CanTerminateProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-canterminateprocess.md)|Určuje, pokud lze ukončit proces.|  
|[TerminateProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-terminateprocess.md)|Ukončení procesu.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)

