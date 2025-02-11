---
title: IDebugEngineLaunch2::LaunchSuspended | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngineLaunch2::LaunchSuspended
helpviewer_keywords:
- IDebugEngineLaunch2::LaunchSuspended
ms.assetid: 5dd2643e-c20a-470e-9024-2a423eb39856
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: cef6382009d8139b8c166ce6b75a692e8e309557
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66337185"
---
# <a name="idebugenginelaunch2launchsuspended"></a>IDebugEngineLaunch2::LaunchSuspended
Tato metoda spustí nějaký proces pomocí ladicího stroje (DE).

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

## <a name="parameters"></a>Parametry
`pszMachine`\
[in] Název počítače, ve kterém chcete spustit proces. Chcete-li určit místní počítač použijte hodnotu null.

`pPort`\
[in] [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) představující port, který se bude program spouštět v rozhraní.

`pszExe`\
[in] Název spustitelného souboru, která se má spustit.

`pszArgs`\
[in] Argumenty k předání do spustitelného souboru. Může mít hodnotu null, pokud nejsou žádné argumenty.

`pszDir`\
[in] Název pracovní adresář, který používá spustitelný soubor. Může mít hodnotu null, pokud je potřeba žádné pracovní adresář.

`bstrEnv`\
[in] Blok prostředí řetězec zakončený NULL, za nímž následuje další ukončovací znak NULL.

`pszOptions`\
[in] Parametry pro spustitelný soubor.

`dwLaunchFlags`\
[in] Určuje, [LAUNCH_FLAGS](../../../extensibility/debugger/reference/launch-flags.md) pro relaci.

`hStdInput`\
[in] Popisovač alternativní vstupní datový proud. Může být 0, pokud se nevyžaduje přesměrování.

`hStdOutput`\
[in] Popisovač alternativní výstupní datový proud. Může být 0, pokud se nevyžaduje přesměrování.

`hStdError`\
[in] Zpracování do výstupního datového proudu alternativní chyby. Může být 0, pokud se nevyžaduje přesměrování.

`pCallback`\
[in] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) objekt, který přijímá události ladicího programu.

`ppDebugProcess`\
[out] Vrátí výsledný [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) objekt, který reprezentuje spuštěn proces.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Za normálních okolností [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] spustí program pomocí [LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md) metoda a potom připojí ladicí program k programu pozastavené. Ale existují okolnosti, ve kterých ladicí stroj možná bude nutné ke spuštění programu (například, pokud ladicí stroj je součástí interpretu a laděný program je interpretovaný jazyk), v takovém případě [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] používá `IDebugEngineLaunch2::LaunchSuspended` – metoda .

 [ResumeProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md) metoda je volána po v pozastaveném stavu se úspěšně spustila proces zahájíte proces.

## <a name="see-also"></a>Viz také:
- [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)
- [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)
- [LAUNCH_FLAGS](../../../extensibility/debugger/reference/launch-flags.md)
- [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)
- [LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md)
- [ResumeProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md)