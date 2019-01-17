---
title: IDebugApplication110::AsynchronousCallInMainThread | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplication110::AsynchronousCallInMainThread
ms.assetid: 13b80ff0-4bed-48c1-8031-d4147b51bf6c
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6e3f98ff917475f0f0733163862ff20ef56f04bb
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54344119"
---
# <a name="idebugapplication110asynchronouscallinmainthread"></a>IDebugApplication110::AsynchronousCallInMainThread
Provede asynchronní volání v hlavním vlákně.  
  
> [!IMPORTANT]
>  [Idebugapplication110 – rozhraní](../../winscript/reference/idebugapplication110-interface.md) je implementováno komponentou Pdm verze 11.0 nebo novější. Nachází se v souboru activdbg100.h.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT AsynchronousCallInMainThread([in] IDebugThreadCall* pptc, [in] DWORD_PTR dwParam1, [in] DWORD_PTR dwParam2, [in] DWORD_PTR dwParam3);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pptc`  
 [Idebugthreadcall – rozhraní](../../winscript/reference/idebugthreadcall-interface.md) objekt volat.  
  
 `dwParam1`  
 První parametr volání.  
  
 `dwParam1`  
 První parametr volání.  
  
 `dwParam2`  
 Druhý parametr volání.  
  
 `dwParam3`  
 Třetí parametr volání.  
  
## <a name="see-also"></a>Viz také  
 [IDebugApplication110 – rozhraní](../../winscript/reference/idebugapplication110-interface.md)