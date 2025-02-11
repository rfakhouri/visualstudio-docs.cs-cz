---
title: IDebugEngineLaunch2::LaunchSuspended | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugEngineLaunch2::LaunchSuspended
helpviewer_keywords:
- IDebugEngineLaunch2::LaunchSuspended
ms.assetid: 5dd2643e-c20a-470e-9024-2a423eb39856
caps.latest.revision: 18
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 08f59f9f099f4cec52760c8a8364feb8f5481ffa
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68195754"
---
# <a name="idebugenginelaunch2launchsuspended"></a>IDebugEngineLaunch2::LaunchSuspended
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Tato metoda spustí nějaký proces pomocí ladicího stroje (DE).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
 [in] Název počítače, ve kterém chcete spustit proces. Chcete-li určit místní počítač použijte hodnotu null.  
  
 `pPort`  
 [in] [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) představující port, který se bude program spouštět v rozhraní.  
  
 `pszExe`  
 [in] Název spustitelného souboru, která se má spustit.  
  
 `pszArgs`  
 [in] Argumenty k předání do spustitelného souboru. Může mít hodnotu null, pokud nejsou žádné argumenty.  
  
 `pszDir`  
 [in] Název pracovní adresář, který používá spustitelný soubor. Může mít hodnotu null, pokud je potřeba žádné pracovní adresář.  
  
 `bstrEnv`  
 [in] Blok prostředí řetězec zakončený NULL, za nímž následuje další ukončovací znak NULL.  
  
 `pszOptions`  
 [in] Parametry pro spustitelný soubor.  
  
 `dwLaunchFlags`  
 [in] Určuje, [LAUNCH_FLAGS](../../../extensibility/debugger/reference/launch-flags.md) pro relaci.  
  
 `hStdInput`  
 [in] Popisovač alternativní vstupní datový proud. Může být 0, pokud se nevyžaduje přesměrování.  
  
 `hStdOutput`  
 [in] Popisovač alternativní výstupní datový proud. Může být 0, pokud se nevyžaduje přesměrování.  
  
 `hStdError`  
 [in] Zpracování do výstupního datového proudu alternativní chyby. Může být 0, pokud se nevyžaduje přesměrování.  
  
 `pCallback`  
 [in] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) objekt, který přijímá události ladicího programu.  
  
 `ppDebugProcess`  
 [out] Vrátí výsledný [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) objekt, který reprezentuje spuštěn proces.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Za normálních okolností [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] spustí program pomocí [LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md) metoda a potom připojí ladicí program k programu pozastavené. Ale existují okolnosti, ve kterých ladicí stroj možná bude nutné ke spuštění programu (například, pokud ladicí stroj je součástí interpretu a laděný program je interpretovaný jazyk), v takovém případě [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] používá `IDebugEngineLaunch2::LaunchSuspended` – metoda .  
  
 [ResumeProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md) metoda je volána po v pozastaveném stavu se úspěšně spustila proces zahájíte proces.  
  
## <a name="see-also"></a>Viz také  
 [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [LAUNCH_FLAGS](../../../extensibility/debugger/reference/launch-flags.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md)   
 [ResumeProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md)
