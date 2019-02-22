---
title: IDebugEngineProgram2::WatchForThreadStep | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngineProgram2::WatchForThreadStep
helpviewer_keywords:
- IDebugEngineProgram2::WatchForThreadStep
ms.assetid: b70922a3-1313-409a-b3b7-50c7cd13e394
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b5381cff406e3b6e182a6ecbb191381061fb3758
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56710380"
---
# <a name="idebugengineprogram2watchforthreadstep"></a>IDebugEngineProgram2::WatchForThreadStep
Sleduje spuštění (nebo zastavení sledování provádění) v dané vlákno.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT WatchForThreadStep( 
   IDebugProgram2* pOriginatingProgram,
   DWORD           dwTid,
   BOOL            fWatch,
   DWORD           dwFrame
);
```

```csharp
int WatchForThreadStep( 
   IDebugProgram2 pOriginatingProgram,
   uint           dwTid,
   int            fWatch,
   uint           dwFrame
);
```

#### <a name="parameters"></a>Parametry
 `pOriginatingProgram`

 [in] [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) objekt představující program se stupňovitým.

 `dwTid`

 [in] Určuje identifikátor vlákna, které chcete sledovat.

 `fWatch`

 [in] Nenulová (`TRUE`) znamená, že spuštění sledování pro spuštění ve vlákně identifikovaný `dwTid`; v opačném případě nula (`FALSE`) znamená, že zastavit sledování pro spuštění na `dwTid`.

 `dwFrame`

 [in] Určuje index snímku, který určuje typ kroku. Není-li hodnota je nula (0), typ kroku je "Krokovat s vnořením" a program by se měla zastavit pokaždé, když identifikované vlákna `dwTid` spustí. Když `dwFrame` je nenulová, typ kroku je "Krokovat přes" a program by se měla zastavit jenom v případě, že identifikované vlákna `dwTid` běží v objektu frame, jejíž index je větší než do zásobníku nebo `dwFrame`.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Když správce ladění relace (SDM) kroky program identifikován `pOriginatingProgram` parametr, upozorní všech ostatních připojených programů po zavolání metody.

 Tato metoda se vztahuje pouze na stejném vlákně krokování.

## <a name="see-also"></a>Viz také
- [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)