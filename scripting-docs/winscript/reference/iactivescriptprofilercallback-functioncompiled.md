---
title: IActiveScriptProfilerCallback::FunctionCompiled | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptProfilerCallback.FunctionCompiled
apilocation:
- scrobj.dll
ms.assetid: a7e9ef17-3891-4731-9d08-c37bc489be61
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4bd032914605c61b13a0a56a42e510c2af252f7e
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54091400"
---
# <a name="iactivescriptprofilercallbackfunctioncompiled"></a>IActiveScriptProfilerCallback::FunctionCompiled
Profiler upozorní, že při kompilaci skriptu, který skriptovací modul narazil na funkci.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT FunctionCompiled(  
    [in] PROFILER_TOKEN functionId,  
    [in] PROFILER_TOKEN scriptId,  
    [in] [string] const WCHAR *pwszFunctionName,  
    [in] [string] const WCHAR *pwszFunctionNameHint,  
    [in] IUnknown *pIDebugDocumentContext);  
```  
  
#### <a name="parameters"></a>Parametry  
 `functionId`  
 [in] Jedinečné ID funkce. Toto ID je přiřazena službou skriptovací stroj.  
  
 `scriptId`  
 [in] Jedinečné ID skript, který je součástí funkce.  
  
 `pwszFunctionName`  
 [in] Název funkce nebo hodnota null pro anonymní funkce.  
  
 `pwszFunctionNameHint`  
 [in] Odvozený název funkce nebo hodnota null, pokud skriptovací modul nelze odvodit libovolný název.  
  
 `pIDebugDocumentContext`  
 [in] Pokud je k dispozici, ukazatel na `IUnknown` rozhraní, které profiler se musí dotazovat pro [idebugdocumentcontext – rozhraní](../../winscript/reference/idebugdocumentcontext-interface.md) ukazatele. V opačném případě hodnota null.  
  
## <a name="return-value"></a>Návratová hodnota  
 Skriptovací modul se ignoruje vrácenou hodnotu této metody.  
  
## <a name="remarks"></a>Poznámky  
 Skriptovací stroj může poskytnout kontext dokumentu, pouze v případě, že to je podporované hostitelem.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptProfilerCallback – rozhraní](../../winscript/reference/iactivescriptprofilercallback-interface.md)