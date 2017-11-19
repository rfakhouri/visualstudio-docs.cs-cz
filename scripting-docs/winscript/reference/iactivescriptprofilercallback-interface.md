---
title: "Iactivescriptprofilercallback – rozhraní | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 76f9164b-b086-4b29-ac79-76f9c76f1d11
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f4dc4b9d4e3b1f83a37e64e3a85387fd378d3ca7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptprofilercallback-interface"></a>IActiveScriptProfilerCallback – rozhraní
Poskytuje metody, které jsou používány skriptovacího stroje objekt profileru upozornit, když dojde k události. Toto rozhraní je implementováno objektem profileru.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IActiveScriptProfilerCallback::Initialize](../../winscript/reference/iactivescriptprofilercallback-initialize.md)|Voláno k inicializaci objektu profileru při každém profilace spuštění na skriptovacího stroje.|  
|[IActiveScriptProfilerCallback::Shutdown](../../winscript/reference/iactivescriptprofilercallback-shutdown.md)|Volá se pro uvolnění a vydání objekt profileru při každém profilace zastavení na skriptovacího stroje.|  
|[IActiveScriptProfilerCallback::ScriptCompiled](../../winscript/reference/iactivescriptprofilercallback-scriptcompiled.md)|Objekt, který skriptování modul kompilovat skript oznamuje profileru.|  
|[IActiveScriptProfilerCallback::FunctionCompiled](../../winscript/reference/iactivescriptprofilercallback-functioncompiled.md)|Objekt, který skriptování modul zjistil funkce při kompilování skriptu oznamuje profileru.|  
|[IActiveScriptProfilerCallback::OnFunctionEnter](../../winscript/reference/iactivescriptprofilercallback-onfunctionenter.md)|Upozorní profileru objekt, který skriptovacího stroje se chystá provést volání funkce, které není volání do objektu modelu dokumentu (DOM).|  
|[IActiveScriptProfilerCallback::OnFunctionExit](../../winscript/reference/iactivescriptprofilercallback-onfunctionexit.md)|Oznamuje profileru objekt, skriptovací stroj dokončení provádění funkce volání, které není volání do modelu DOM.|  
  
## <a name="remarks"></a>Poznámky  
 Oznámení o volání funkce do objektu modelu dokumentu (DOM) poskytuje [iactivescriptprofilercallback2 – rozhraní](../../winscript/reference/iactivescriptprofilercallback2-interface.md).  
  
> [!NOTE]
>  Pokud chcete přidat možnost spuštění a zastavení profilování po spuštění skriptu, volání těchto metod. Pomocí těchto metod, můžete získat zásobníku dokončení volání, pokud [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] běží při spuštění nebo zastavení profilování.  
>   
>  -   Volání [IActiveScriptProfilerControl2::CompleteProfilerStart](../../winscript/reference/iactivescriptprofilercontrol2-completeprofilerstart.md) profileru oznámit, že jste spustili profilace.  
> -   Volání [IActiveScriptProfilerControl2::PrepareProfilerStop](../../winscript/reference/iactivescriptprofilercontrol2-prepareprofilerstop.md) profileru upozornit, že bude brzy zastavíte profilace.  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní profileru aktivních skriptů](../../winscript/reference/active-script-profiler-interfaces.md)