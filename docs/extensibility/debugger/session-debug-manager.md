---
title: Relace ladění Manager | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- session debug manager, unifying session views
- session debug manager, broadcasting
- debugging [Debugging SDK], session debug manager
- session debug manager
- session debug manager, debug engine multiplexing
- session debug manager, delegating
ms.assetid: fbb1928d-dddc-43d1-98a4-e23b0ecbae09
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 001c0b954cd47b9825a6982f2474d6fd6d415e23
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="session-debug-manager"></a>Správce ladicí relace
Správce ladicí relace (SDM) spravuje libovolný počet modulů ladění (DE) ladění libovolný počet programy v několika procesů na libovolný počet počítačů. Kromě toho modul ladění multiplexor, SDM poskytuje jednotný pohled na relaci ladění k prostředí IDE.  
  
## <a name="session-debug-manager-operation"></a>Operace správce ladicí relace  
 Správce ladicí relace (SDM) spravuje DE. Může existovat více než jeden modul ladění spuštěný na počítači ve stejnou dobu. Chcete-li multiplexovaný DEs, SDM zabalí počet rozhraní z DEs a vystavuje je jako jeden rozhraní IDE.  
  
 Pokud chcete zvýšit výkon, nejsou multiplexní některé rozhraní. Místo toho se používají přímo z DE a volání tato rozhraní se nepřenášejí prostřednictvím SDM. Například nejsou multiplexní rozhraní používá paměť, kód a kontexty dokument, protože najdete konkrétní instrukce, paměť či dokumentu v konkrétní program programem konkrétní DE. Žádné jiné DE by se měl podílet na této úrovni komunikace.  
  
 To není pravda všechny kontextů. Volání rozhraní kontext vyhodnocení výrazu projít SDM. Při vyhodnocování výrazu SDM zabalí [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) rozhraní, která poskytuje k rozhraní IDE, protože je vyhodnocena tento výraz se může zahrnovat víc DEs, která jsou ladění programů v rámci jednoho procesu, který může být spuštění ve stejném vlákně.  
  
 SDM obvykle funguje jako mechanismus delegování, ale může fungovat jako mechanismus všesměrového vysílání. Při vyhodnocení výrazu, například SDM funguje jako mechanismus všesměrového vysílání upozornit všechny DEs, jejich spuštění kódu v zadané vlákna. Podobně SDM obdrží zastavení událostí, vysílá na položku Všechny programy, že by se měla zastavit, spuštěná. Při volání krok SDM všesměrově všechny programy, budou nadále pracovat. Zarážky jsou všesměrové vysílání, pro každý DE.  
  
 SDM nesleduje aktuálním programem, vlákno nebo rámce zásobníku. Proces, program a vlákno informace se odesílají do SDM ve spojení s konkrétní ladění událostí.  
  
## <a name="see-also"></a>Viz také  
 [Ladění modulu](../../extensibility/debugger/debug-engine.md)   
 [Ladicí program komponenty](../../extensibility/debugger/debugger-components.md)   
 [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md)