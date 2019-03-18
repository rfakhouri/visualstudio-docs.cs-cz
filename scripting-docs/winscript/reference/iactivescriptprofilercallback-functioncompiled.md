---
title: IActiveScriptProfilerCallback::FunctionCompiled | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
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
ms.openlocfilehash: 1a039f7a682babebdccad276adce55e69bb8e0bc
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58153718"
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