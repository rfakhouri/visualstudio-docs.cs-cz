---
title: Iactivescriptsitedebugex – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptSiteDebugEx Interface
ms.assetid: 76869378-1a7b-47bd-8cd0-acc31f91d58d
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c1e462630f7bf52c4ca94aa59df22616e9a335a7
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54345874"
---
# <a name="iactivescriptsitedebugex-interface"></a>IActiveScriptSiteDebugEx – rozhraní
Implementace tohoto rozhraní spolu s `IActiveScriptSiteDebug` rozhraní při psaní hostitele, který je potřeba získat oznámení chyb za běhu v aplikaci a volitelně připojit k aplikaci pro ladění. Správce ladění procesu poskytuje oznámení prostřednictvím `IActiveScriptDebug` Pokud ladicí program skriptů Just-In-Time je v počítači nalezena. Pokud ladicí program skriptu žádné Just-In-Time je nalezen, PDM poskytuje oznámení prostřednictvím `IActiveScriptDebugEx` místo.  
  
 Získat oznámení chyb za běhu, musí zvládnout váš hostitel [ActiveScriptSiteDebug::OnScriptErrorDebug](http://msdn.microsoft.com/en-us/cf7639f9-a699-4571-9f3a-82ef52c0b5f4). Založené na akci uživatele, potom se můžete rozhodnout, jestli chcete připojit interní ladicího programu a vraťte se nebo se vraťte spouštění v ladicím programu OnScriptErrorDebug `pfEnterDebugger` parametru.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IActiveScriptSiteDebugEx::OnCanNotJITScriptErrorDebug](../../winscript/reference/iactivescriptsitedebugex-oncannotjitscripterrordebug.md)|Informuje o tom, že hostitel o Chyba za běhu skriptu při ladění procesu Manager nelze najít externí ladění JIT.|