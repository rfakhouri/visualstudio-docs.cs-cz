---
title: IActiveScriptProfilerCallback2 Interface | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptProfilerCallback2 interface
ms.assetid: 8f2e62e4-c232-4dc3-a2c0-54dd06298306
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b0a0df287db477c5bf768798f200ea0d97de6d1e
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63385945"
---
# <a name="iactivescriptprofilercallback2-interface"></a>IActiveScriptProfilerCallback2 – rozhraní
Poskytuje metody, které jsou používány skriptovací stroj objekt profileru upozornit, pokud dojde k událostem Document Object Model (DOM). Toto rozhraní je implementováno v objektu profileru.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IActiveScriptProfilerCallback2::OnFunctionEnterByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionenterbyname.md)|Upozorní objekt profileru, který skriptovací stroj bude běžet modelu DOM volání funkce.|  
|[IActiveScriptProfilerCallback2::OnFunctionExitByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionexitbyname.md)|Profiler upozorní, že objekt, který skriptovací modul dokončení volání funkce modelu DOM.|  
  
## <a name="remarks"></a>Poznámky  
 `IActiveScriptProfilerCallback2` Rozhraní prvního vydání pomocí aplikace Internet Explorer 9.  
  
 Poskytuje oznámení o volání funkcí, které nejsou volání do modelu DOM [iactivescriptprofilercallback – rozhraní](../../winscript/reference/iactivescriptprofilercallback-interface.md).  
  
> [!NOTE]
> Chcete-li přidat možnost spuštění a zastavení profilování při spuštění skriptu, volání těchto metod. Pomocí těchto metod můžete získat úplný zásobník volání, pokud [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] je spuštěna při spuštění nebo zastavení profilování.  
> 
> - Volání [IActiveScriptProfilerControl2::CompleteProfilerStart](../../winscript/reference/iactivescriptprofilercontrol2-completeprofilerstart.md) pro oznámení profileru, které jste spustili profilace.  
>   - Volání [IActiveScriptProfilerControl2::PrepareProfilerStop](../../winscript/reference/iactivescriptprofilercontrol2-prepareprofilerstop.md) pro oznámení profileru, že vám brzy ukončí profilaci.  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní profileru aktivních skriptů](../../winscript/reference/active-script-profiler-interfaces.md)