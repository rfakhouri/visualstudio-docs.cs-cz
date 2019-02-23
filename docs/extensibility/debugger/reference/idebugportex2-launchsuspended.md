---
title: IDebugPortEx2::LaunchSuspended | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortEx2::LaunchSuspended
helpviewer_keywords:
- IDebugPortEx2::LaunchSuspended
ms.assetid: 34b2cf99-2e52-4757-8969-1d12ac517ec0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a8d946097d7a8f50cab65b41aaef73654dfbd18a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56703198"
---
# <a name="idebugportex2launchsuspended"></a>IDebugPortEx2::LaunchSuspended
Spustí spustitelný soubor.

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

 [in] Název spustitelného souboru, která se má spustit. To může být úplná cesta nebo relativní vzhledem k zadaný v pracovní adresář `pszDir` parametru.

 `pszArgs`

 [in] Argumenty k předání do spustitelného souboru. Může mít hodnotu null, pokud nejsou žádné argumenty.

 `pszDir`

 [in] Název pracovní adresář, který používá spustitelný soubor. Může mít hodnotu null, pokud je potřeba žádné pracovní adresář.

 `bstrEnv`

 [in] Blok prostředí řetězec zakončený null, za nímž následuje další ukončovací znak NULL.

 `hStdInput`

 [in] Popisovač alternativní vstupní datový proud. Může být 0, pokud se nevyžaduje přesměrování.

 `hStdOutput`

 [in] Popisovač alternativní výstupní datový proud. Může být 0, pokud se nevyžaduje přesměrování.

 `hStdError`

 [in] Zpracování do výstupního datového proudu alternativní chyby. Může být 0, pokud se nevyžaduje přesměrování.

 `ppPortProcess`

 [out] Vrátí [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) objekt, který reprezentuje spuštěn proces.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda by měla spustit proces tak, že je pozastavený a neběží žádný kód. [ResumeProcess](../../../extensibility/debugger/reference/idebugportex2-resumeprocess.md) metoda je volána, aby se proces obnovil.

 Program můžete také spustit z ladicího stroje. Podrobnosti najdete v tématu [spuštění programu](../../../extensibility/debugger/launching-a-program.md).

## <a name="see-also"></a>Viz také
- [IDebugPortEx2](../../../extensibility/debugger/reference/idebugportex2.md)
- [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)
- [ResumeProcess](../../../extensibility/debugger/reference/idebugportex2-resumeprocess.md)
- [Spuštění programu](../../../extensibility/debugger/launching-a-program.md)