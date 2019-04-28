---
title: IActiveScriptProfilerControl2::PrepareProfilerStop | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptProfilerControl2::PrepareProfilerStop
ms.assetid: e43a63bc-c44f-44a8-9db4-29062b9e6a16
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 11a32f36ec6eddcc06faa77e093f19e8df503fa4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62968760"
---
# <a name="iactivescriptprofilercontrol2prepareprofilerstop"></a>IActiveScriptProfilerControl2::PrepareProfilerStop
Oznámí profileru, že chcete zastavit profilaci ve všech příslušných skriptovacích strojů. Tímto způsobem můžete získat úplný zásobník volání, pokud [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] běží při zastavení profilování.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT PrepareProfilerStop();  
```  
  
#### <a name="parameters"></a>Parametry  
 Metoda nepřijímá žádné parametry.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí hodnotu HRESULT. Možné hodnoty jsou následující:  
  
|Návratová hodnota|Význam|  
|------------------|-------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`E_FAIL`|Nebylo možné spustit profilaci.|  
|`S_FALSE`|Profilace byla zastavena, když skript nebyl spuštěn.|  
|`ACTIVPROF_E_PROFILER_ABSENT`|Profilace není povolená.|  
  
## <a name="remarks"></a>Poznámky  
 Volání `IActiveScriptProfilerControl2::PrepareProfilerStop` zajistí, že jsou odesílány události pro funkce v zásobníku volání. Tato metoda má být volána před zastavit profilaci ve všech skriptovací stroj, který je na aktuální kartě. Metodu lze volat pro jakékoli skriptovací stroj.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptProfilerControl2::CompleteProfilerStart](../../winscript/reference/iactivescriptprofilercontrol2-completeprofilerstart.md)   
 [IActiveScriptProfilerControl2 – rozhraní](../../winscript/reference/iactivescriptprofilercontrol2-interface.md)