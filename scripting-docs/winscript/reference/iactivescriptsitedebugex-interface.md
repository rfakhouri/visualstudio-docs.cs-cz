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
ms.openlocfilehash: e390b610d6912de0078b817c9dfb503e5924a374
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54797426"
---
# <a name="iactivescriptsitedebugex-interface"></a>IActiveScriptSiteDebugEx – rozhraní

Implementace tohoto rozhraní spolu s `IActiveScriptSiteDebug` rozhraní při psaní hostitele, který je potřeba získat oznámení chyb za běhu v aplikaci a volitelně připojit k aplikaci pro ladění. Správce ladění procesu poskytuje oznámení prostřednictvím `IActiveScriptDebug` Pokud ladicí program skriptů Just-In-Time je v počítači nalezena. Pokud ladicí program skriptu žádné Just-In-Time je nalezen, PDM poskytuje oznámení prostřednictvím `IActiveScriptDebugEx` místo.

Získat oznámení chyb za běhu, musí zvládnout váš hostitel `ActiveScriptSiteDebug::OnScriptErrorDebug`. Založené na akci uživatele, potom se můžete rozhodnout, jestli chcete připojit interní ladicího programu a vraťte se nebo se vraťte spouštění v ladicím programu OnScriptErrorDebug `pfEnterDebugger` parametru.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí

|Metoda|Popis|
|------------|-----------------|
|[IActiveScriptSiteDebugEx::OnCanNotJITScriptErrorDebug](../../winscript/reference/iactivescriptsitedebugex-oncannotjitscripterrordebug.md)|Informuje o tom, že hostitel o Chyba za běhu skriptu při ladění procesu Manager nelze najít externí ladění JIT.|