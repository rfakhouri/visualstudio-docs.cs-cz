---
title: IActiveScriptProfilerCallback::OnFunctionEnter | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptProfilerCallback.OnFunctionEnter
apilocation:
- scrobj.dll
ms.assetid: 12dab2b4-df4e-444d-99cb-25e1c278e6e8
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 887810d12a20045c95b0f837db1592b9b7bf301e
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095378"
---
# <a name="iactivescriptprofilercallbackonfunctionenter"></a>IActiveScriptProfilerCallback::OnFunctionEnter
Upozorní objekt profileru, který skriptovací stroj je před spuštěním volání funkce, která není volání do modelu Document Object Model (DOM).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT OnFunctionEnter(  
    [in] PROFILER_TOKEN scriptId,   
    [in] PROFILER_TOKEN functionId);  
```  
  
#### <a name="parameters"></a>Parametry  
 `scriptId`  
 [in] Jedinečné ID skript, který je součástí funkce. Toto ID je přiřazena službou skriptovací stroj.  
  
 `functionId`  
 [in] Jedinečné ID funkce. Toto ID je přiřazena službou skriptovací stroj.  
  
## <a name="return-value"></a>Návratová hodnota  
 Skriptovací modul se ignoruje vrácenou hodnotu této metody.  
  
## <a name="remarks"></a>Poznámky  
 Pro volání modelu DOM, volá skriptovací stroj [IActiveScriptProfilerCallback2::OnFunctionEnterByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionenterbyname.md) místo `IActiveScriptProfilerCallback::OnFunctionEnter`. Je to z důvodu velkého počtu jedinečných metody a vlastnosti v modelu DOM.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptProfilerCallback::OnFunctionExit](../../winscript/reference/iactivescriptprofilercallback-onfunctionexit.md)   
 [IActiveScriptProfilerCallback – rozhraní](../../winscript/reference/iactivescriptprofilercallback-interface.md)