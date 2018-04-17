---
title: IDebugEngineLaunch2::LaunchSuspended | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEngineLaunch2::LaunchSuspended
helpviewer_keywords:
- IDebugEngineLaunch2::LaunchSuspended
ms.assetid: 5dd2643e-c20a-470e-9024-2a423eb39856
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a05e8f034ec30f0f387675759cb7601f7b3fc3e7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugenginelaunch2launchsuspended"></a>IDebugEngineLaunch2::LaunchSuspended
Tato metoda spustí proces prostřednictvím modul ladění (DE).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT LaunchSuspended (   
   LPCOLESTR             pszMachine,  
   IDebugPort2*          pPort,  
   LPCOLESTR             pszExe,  
   LPCOLESTR             pszArgs,  
   LPCOLESTR             pszDir,  
   BSTR                  bstrEnv,  
   LPCOLESTR             pszOptions,  
   LAUNCH_FLAGS          dwLaunchFlags,  
   DWORD                 hStdInput,  
   DWORD                 hStdOutput,  
   DWORD                 hStdError,  
   IDebugEventCallback2* pCallback,  
   IDebugProcess2**      ppDebugProcess  
);  
```  
  
```csharp  
int LaunchSuspended(  
   string               pszServer,   
   IDebugPort2          pPort,   
   string               pszExe,   
   string               pszArgs,   
   string               pszDir,   
   string               bstrEnv,   
   string               pszOptions,   
   enum_LAUNCH_FLAGS    dwLaunchFlags,   
   uint                 hStdInput,   
   uint                 hStdOutput,   
   uint                 hStdError,  
   IDebugEventCallback2 pCallback,   
   out IDebugProcess2   ppProcess  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszMachine`  
 [v] Název počítače, ve kterém se má spustit proces. Chcete-li určit místní počítač, použijte hodnotu null.  
  
 `pPort`  
 [v] [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) rozhraní představující port, který se bude program spouštět v.  
  
 `pszExe`  
 [v] Název spustitelného souboru, který má být spuštěna.  
  
 `pszArgs`  
 [v] Argumenty, které mají být předána do spustitelného souboru. Může mít hodnotu null, pokud žádné argumenty.  
  
 `pszDir`  
 [v] Název pracovní adresář používá spustitelný soubor. Může mít hodnotu null, pokud není třeba žádné pracovní adresář.  
  
 `bstrEnv`  
 [v] Blok prostředí řetězce ukončené hodnotou NULL, za nímž následuje další ukončovací hodnotu NULL.  
  
 `pszOptions`  
 [v] Parametry pro spustitelný soubor.  
  
 `dwLaunchFlags`  
 [v] Určuje, [LAUNCH_FLAGS](../../../extensibility/debugger/reference/launch-flags.md) pro relaci.  
  
 `hStdInput`  
 [v] Popisovač alternativní vstupního datového proudu. Může být 0, pokud přesměrování není potřeba.  
  
 `hStdOutput`  
 [v] Zpracování alternativní výstupního proudu. Může být 0, pokud přesměrování není potřeba.  
  
 `hStdError`  
 [v] Zpracování do výstupního datového proudu alternativní chyby. Může být 0, pokud přesměrování není potřeba.  
  
 `pCallback`  
 [v] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) objekt, který přijme události ladicí program.  
  
 `ppDebugProcess`  
 [out] Vrátí výsledná [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) objekt, který reprezentuje spuštěného procesu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Za normálních okolností [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] spustí program pomocí [LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md) metoda a potom připojí ladicí program pozastavenou programu. Existují však případech, ve kterých se ladění modul může třeba spustit program (například pokud modul ladění je součástí překladač a program laděné je interpretovaný jazyk), v takovém případě [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] používá `IDebugEngineLaunch2::LaunchSuspended` – metoda .  
  
 [ResumeProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md) metoda je volána před zahájením procesu po proces byla úspěšně spuštěna v pozastaveném stavu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [LAUNCH_FLAGS](../../../extensibility/debugger/reference/launch-flags.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md)   
 [ResumeProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md)