---
title: Iactivescripttraceinfo::startscripttracing – metoda | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 90fac5ed-ce15-49b7-a6f1-605ede6f34e2
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b87971e1fd2e484aa54ff4de56ee56e00b19b1e6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62991199"
---
# <a name="iactivescripttraceinfostartscripttracing-method"></a>IActiveScriptTraceInfo::StartScriptTracing – metoda
Spustí skript trasování.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT StartScriptTracing(     [in] IActiveScriptSiteTraceInfo * pSiteTraceInfo,     [in] GUID guidContextID );   
```  
  
#### <a name="parameters"></a>Parametry  
 `pSiteTraceInfo`  
 Ukazatel na iactivescriptsitetraceinfo – hostitele.  
  
 `guidContextId`  
 Identifikátor GUID kontextu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Je to možné návratové hodnoty pro tuto metodu jsou následující:  
  
1. S_OK: Úspěch.  
  
2. E_POINTER: `pSiteTraceInfo` je ukazatel s hodnotou NULL.  
  
3. E_NOTIMPL: Není implementováno.