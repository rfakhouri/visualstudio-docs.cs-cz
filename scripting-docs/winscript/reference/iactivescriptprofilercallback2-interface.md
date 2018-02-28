---
title: "Iactivescriptprofilercallback2 – rozhraní | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IActiveScriptProfilerCallback2 interface
ms.assetid: 8f2e62e4-c232-4dc3-a2c0-54dd06298306
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2dc9fcd8ca4afec0fb474c0f3a7317b608c7c9f6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptprofilercallback2-interface"></a>IActiveScriptProfilerCallback2 – rozhraní
Poskytuje metody, které jsou používány skriptovacího stroje objekt profileru upozornit, když dojde k události modelu DOM (Document Object). Toto rozhraní je implementováno objektem profileru.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IActiveScriptProfilerCallback2::OnFunctionEnterByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionenterbyname.md)|Upozorní profileru objekt, který skriptovací stroj bude běžet DOM volání funkce.|  
|[IActiveScriptProfilerCallback2::OnFunctionExitByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionexitbyname.md)|Objekt, který skriptování modul spuštění volání funkce DOM dokončeno oznamuje profileru.|  
  
## <a name="remarks"></a>Poznámky  
 `IActiveScriptProfilerCallback2` Rozhraní prvního vydání se aplikace Internet Explorer 9.  
  
 Volání funkce, které nejsou volání do modelu DOM oznámení poskytla služba [iactivescriptprofilercallback – rozhraní](../../winscript/reference/iactivescriptprofilercallback-interface.md).  
  
> [!NOTE]
>  Pokud chcete přidat možnost spuštění a zastavení profilování po spuštění skriptu, volání těchto metod. Pomocí těchto metod, můžete získat zásobníku dokončení volání, pokud [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] běží při spuštění nebo zastavení profilování.  
>   
>  -   Volání [IActiveScriptProfilerControl2::CompleteProfilerStart](../../winscript/reference/iactivescriptprofilercontrol2-completeprofilerstart.md) profileru oznámit, že jste spustili profilace.  
> -   Volání [IActiveScriptProfilerControl2::PrepareProfilerStop](../../winscript/reference/iactivescriptprofilercontrol2-prepareprofilerstop.md) profileru upozornit, že bude brzy zastavíte profilace.  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní profileru aktivních skriptů](../../winscript/reference/active-script-profiler-interfaces.md)