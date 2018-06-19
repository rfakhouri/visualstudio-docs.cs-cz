---
title: IDebugPortEx2::LaunchSuspended | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugPortEx2::LaunchSuspended
helpviewer_keywords:
- IDebugPortEx2::LaunchSuspended
ms.assetid: 34b2cf99-2e52-4757-8969-1d12ac517ec0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 9f22afc50a1a2874d4853acbf9ff72cae622e790
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31114888"
---
# <a name="idebugportex2launchsuspended"></a>IDebugPortEx2::LaunchSuspended
Spouští spustitelný soubor.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT LaunchSuspended(   
   LPCOLESTR        pszExe,  
   LPCOLESTR        pszArgs,  
   LPCOLESTR        pszDir,  
   BSTR             bstrEnv,  
   DWORD            hStdInput,  
   DWORD            hStdOutput,  
   DWORD            hStdError,  
   IDebugProcess2** ppPortProcess  
);  
```  
  
```csharp  
int LaunchSuspended(   
   string             pszExe,  
   string             pszArgs,  
   string             pszDir,  
   string             bstrEnv,  
   uint               hStdInput,  
   uint               hStdOutput,  
   uint               hStdError,  
   out IDebugProcess2 ppPortProcess  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszExe`  
 [v] Název spustitelného souboru, který má být spuštěna. To může být úplná cesta nebo relativně k zadané v pracovní adresář `pszDir` parametr.  
  
 `pszArgs`  
 [v] Argumenty, které mají být předána do spustitelného souboru. Může mít hodnotu null, pokud žádné argumenty.  
  
 `pszDir`  
 [v] Název pracovní adresář používá spustitelný soubor. Může mít hodnotu null, pokud není třeba žádné pracovní adresář.  
  
 `bstrEnv`  
 [v] Blok prostředí řetězce ukončené hodnotou null, za nímž následuje další ukončovací hodnotu NULL.  
  
 `hStdInput`  
 [v] Popisovač alternativní vstupního datového proudu. Může být 0, pokud přesměrování není potřeba.  
  
 `hStdOutput`  
 [v] Zpracování alternativní výstupního proudu. Může být 0, pokud přesměrování není potřeba.  
  
 `hStdError`  
 [v] Zpracování do výstupního datového proudu alternativní chyby. Může být 0, pokud přesměrování není potřeba.  
  
 `ppPortProcess`  
 [out] Vrátí [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) objekt, který reprezentuje spuštěného procesu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda by měla spusťte proces, to je pozastavená a neběží. žádný kód. [ResumeProcess](../../../extensibility/debugger/reference/idebugportex2-resumeprocess.md) metoda je volána obnovit proces.  
  
 Program lze spustit také z modul ladění. Podrobnosti najdete v tématu [spuštění programu](../../../extensibility/debugger/launching-a-program.md).  
  
## <a name="see-also"></a>Viz také  
 [IDebugPortEx2](../../../extensibility/debugger/reference/idebugportex2.md)   
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)   
 [ResumeProcess](../../../extensibility/debugger/reference/idebugportex2-resumeprocess.md)   
 [Spuštění programu](../../../extensibility/debugger/launching-a-program.md)