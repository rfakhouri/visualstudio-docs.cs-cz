---
title: "Funkce zpětného volání, které jsou implementované integrovaného vývojového prostředí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control plug-ins, callback functions
- callback functions, source control plug-ins
ms.assetid: 4a8833f0-6ac0-4ea7-9400-8275aa991468
caps.latest.revision: "24"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 3c1845a82947286800145ff898f8f49f8c3c2477
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="callback-functions-implemented-by-the-ide"></a>Funkce zpětného volání, které implementují rozhraní IDE
Chcete-li integraci s integrované vývojové prostředí (IDE) jako bezproblémové nejblíže a nabízí jednotnou koncového uživatele prostředí, modul plug-in zdrojového kódu můžete použít funkce zpětného volání, které implementují rozhraní IDE. Modul plug-in můžete volat tyto funkce v příslušnou dobu během operace řízení zdroj předávat informace k prostředí IDE; prostředí IDE pak můžete zobrazit tyto informace jako vložené prvky v jeho nativní uživatelského rozhraní. Uživatel má méně fragmentovaných prostředí v tomto scénáři než pokud modul plug-in pracujících vlastní uživatelské rozhraní.  
  
 Požadovaná hlavička souboru je scc.h. Výchozí umístění je \Program Files\VSIP 8.0\EnvSDK\common\inc\\. Je také ve složce VSIP, který má modul plug-in ukázka zdroj ovládacího prvku na \Program Files\VSIP 8.0\MSSCCI\\.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)  
 Popisuje funkce zpětného volání, který je používán [SccOpenProject](../extensibility/sccopenproject-function.md) pro zobrazení zpráv ze zdrojového kódu modulu plug-in pomocí rozhraní IDE.  
  
 [POPLISTFUNC](../extensibility/poplistfunc.md)  
 Popisuje funkce zpětného volání, který je používán [SccPopulateList](../extensibility/sccpopulatelist-function.md) Pokud IDE nemá úplný přístup k informacím, které je k dispozici pouze pro modul plug-in, jako je například kompletní seznam souborů v části Správa verzí zdrojového kódu.  
  
 [QUERYCHANGESFUNC](../extensibility/querychangesfunc.md)  
 Popisuje funkce zpětného volání, který je používán [SccQueryChanges](../extensibility/sccquerychanges-function.md) operaci.  
  
 [POPDIRLISTFUNC](../extensibility/popdirlistfunc.md)  
 Popisuje funkce zpětného volání, který je používán [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md) operaci.  
  
 [OPTNAMECHANGEPFN](../extensibility/optnamechangepfn.md)  
 Popisuje funkce zpětného volání, která nastavuje volání [SccSetOption](../extensibility/sccsetoption-function.md) umožňující modulu plug-in pro komunikaci název změn zpět do prostředí IDE zdrojového kódu.  
  
## <a name="related-sections"></a>Související oddíly  
 [SccOpenProject](../extensibility/sccopenproject-function.md)  
 Otevře se projektu.  
  
 [SccPopulateList](../extensibility/sccpopulatelist-function.md)  
 Prozkoumá seznam souborů pro jejich aktuální stav. Kromě toho používá `pfnPopulate` funkce, které oznámí souboru neodpovídá kritériím pro volající `nCommand`.  
  
 [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)  
 Prozkoumá seznam adresářů a souborů v projektu nebo projektů, které jsou v části Správa zdrojového kódu. Každý název adresáře a souboru nalezen předaný funkci zpětného volání.  
  
 [SccQueryChanges](../extensibility/sccquerychanges-function.md)  
 Prozkoumá název změny, které byly provedeny seznam souborů. Každý název souboru je předaný funkci zpětného volání společně s jeho změnu stavu.  
  
 [SccSetOption](../extensibility/sccsetoption-function.md)  
 Nastaví širokou škálu možností. Každá možnost začíná `SCC_OPT_xxx` a má svou vlastní definované sady hodnot.  
  
 [Moduly plug-in správy zdrojového kódu](../extensibility/source-control-plug-ins.md)  
 Popisuje obsah části referenční dokumentace sady SDK Plug-in Zdroj ovládacího prvku.