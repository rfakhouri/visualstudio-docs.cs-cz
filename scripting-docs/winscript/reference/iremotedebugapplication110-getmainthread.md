---
title: IRemoteDebugApplication110::GetMainThread | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IRemoteDebugApplication110::GetMainThread
ms.assetid: 9982acc9-3d35-4dcf-8ca9-662469de4072
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 20d895f8bd6d4919def00625e9f285afdfe4f866
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349861"
---
# <a name="iremotedebugapplication110getmainthread"></a>IRemoteDebugApplication110::GetMainThread
Vrátí hlavní vlákno pro hostitele, které volají [setsite –](http://go.microsoft.com/fwlink/?LinkId=232439), v opačném případě vrátí E_FAIL.  
  
> [!IMPORTANT]
>  [Iremotedebugapplication – rozhraní](../../winscript/reference/iremotedebugapplication-interface.md) je implementováno komponentou Pdm verze 11.0 nebo novější. Nachází se v souboru activdbg100.h.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetMainThread([out] IRemoteDebugApplicationThread **ppThread);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppThread`  
 [out] Hlavní [iremotedebugapplicationthread – rozhraní](../../winscript/reference/iremotedebugapplicationthread-interface.md).  
  
## <a name="see-also"></a>Viz také  
 [Iremotedebugapplication – rozhraní](../../winscript/reference/iremotedebugapplication-interface.md)   
 [IRemoteDebugApplication110 – rozhraní](../../winscript/reference/iremotedebugapplication110-interface.md)