---
title: IActiveScriptProfilerCallback::Initialize | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptProfilerCallback.Initialize
apilocation:
- scrobj.dll
ms.assetid: a257111e-a50b-4962-9dd6-c893d40f6985
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 66ef6dc37e1f2f8117e440089ee36958d616dda0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62993355"
---
# <a name="iactivescriptprofilercallbackinitialize"></a>IActiveScriptProfilerCallback::Initialize
Volána k inicializaci objektu profileru pokaždé, když profilace je spuštěna na skriptovacím stroji.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT Initialize(  
    [in] DWORD dwContext);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwContext`  
 [in] 4bajtový hodnotu, která je předána [IActiveScriptProfilerControl::StartProfiling](../../winscript/reference/iactivescriptprofilercontrol-startprofiling.md).  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí hodnotu HRESULT. Možné hodnoty jsou následující:  
  
|Návratová hodnota|Význam|  
|------------------|-------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud objekt profileru nelze inicializovat metodu, měla by vrátit chybu HRESULT oznámit skriptovací stroj. V takovém případě by měly skriptovací stroj přímo volat [IActiveScriptProfilerCallback::Shutdown](../../winscript/reference/iactivescriptprofilercallback-shutdown.md)předáním HRESULT v parametru a uvolněte objektu profileru.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptProfilerCallback – rozhraní](../../winscript/reference/iactivescriptprofilercallback-interface.md)