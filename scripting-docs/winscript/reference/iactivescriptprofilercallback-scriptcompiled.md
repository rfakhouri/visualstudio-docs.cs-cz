---
title: IActiveScriptProfilerCallback::ScriptCompiled | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptProfilerCallback.ScriptCompiled
apilocation:
- scrobj.dll
ms.assetid: 1bb8e9be-cbb1-4a61-b36c-805127a56ac7
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bf653e5623506a68e6353e3d9f97077592e87941
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54091504"
---
# <a name="iactivescriptprofilercallbackscriptcompiled"></a>IActiveScriptProfilerCallback::ScriptCompiled
Profiler upozorní, že objekt, který skriptovací modul kompilaci skriptu. Tato metoda je volána pro každý skript, který je kompilován.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT ScriptCompiled(  
    [in] PROFILER_TOKEN scriptId,  
    [in] PROFILER_SCRIPT_TYPE type,  
    [in] IUnknown *pIDebugDocumentContext);  
```  
  
#### <a name="parameters"></a>Parametry  
 `scriptId`  
 [in] Jedinečné ID skript, který byl zkompilován. Toto ID je přiřazena službou skriptovací stroj.  
  
 `type`  
 [in] Typ skriptu, který byl zkompilován. Hodnoty jsou definovány v [profiler_script_type – výčet](../../winscript/reference/profiler-script-type-enumeration.md).  
  
 `pIDebugDocumentContext`  
 [in] Pokud je k dispozici, ukazatel na `IUnknown` rozhraní, které profiler se musí dotazovat pro [idebugdocumentcontext – rozhraní](../../winscript/reference/idebugdocumentcontext-interface.md) ukazatele. Jinak to bude mít hodnotu null.  
  
## <a name="return-value"></a>Návratová hodnota  
 Skriptovací modul se ignoruje vrácenou hodnotu této metody.  
  
## <a name="remarks"></a>Poznámky  
 Skriptovací stroj může poskytnout kontext dokumentu, pouze v případě, že to je podporované hostitelem.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptProfilerCallback – rozhraní](../../winscript/reference/iactivescriptprofilercallback-interface.md)