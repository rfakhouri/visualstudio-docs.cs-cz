---
title: Iactivescriptprofilercontrol – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 1448b394-9743-41b5-8eb9-5026a45773a4
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 86f4fb8dea97930f717800a14a27740b76eb6c2e
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58160755"
---
# <a name="iactivescriptprofilercontrol-interface"></a>IActiveScriptProfilerControl – rozhraní
Implementované skriptovací stroj, který podporuje vytváření profilů. Obvykle, objekt, který implementuje `IActiveScriptProfilerControl` také implementuje [IActiveScript –](../../winscript/reference/iactivescript.md) rozhraní. V takovém případě můžete získat popisovač `IActiveScriptProfilerControl` rozhraní voláním `IUnknown::QueryInterface` metodu na objekt. Rozhraní obsahuje potřebné metody pro spouštění a zastavování profilace na skriptovacím stroji.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IActiveScriptProfilerControl::StartProfiling](../../winscript/reference/iactivescriptprofilercontrol-startprofiling.md)|Spustí profilaci na skriptovacím stroji.|  
|[IActiveScriptProfilerControl::SetProfilerEventMask](../../winscript/reference/iactivescriptprofilercontrol-setprofilereventmask.md)|Profiler nastaví masky události v skriptovací stroj.|  
|[IActiveScriptProfilerControl::StopProfiling](../../winscript/reference/iactivescriptprofilercontrol-stopprofiling.md)|Zastaví profilaci na skriptovacím stroji.|  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní profileru aktivních skriptů](../../winscript/reference/active-script-profiler-interfaces.md)