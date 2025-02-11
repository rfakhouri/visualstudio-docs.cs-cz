---
title: Správce ladění relace | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- session debug manager, unifying session views
- session debug manager, broadcasting
- debugging [Debugging SDK], session debug manager
- session debug manager
- session debug manager, debug engine multiplexing
- session debug manager, delegating
ms.assetid: fbb1928d-dddc-43d1-98a4-e23b0ecbae09
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 9fd7c7555c19f850a15161f6fba00b1184621a9e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68157826"
---
# <a name="session-debug-manager"></a>Správce ladění relace
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Správce ladění relace (SDM) spravuje libovolný počet ladicí stroj (DE) ladění libovolný počet programy ve více procesech v libovolném počtu počítačů. Kromě toho, že ladicí stroj multiplexor SDM poskytuje jednotný přehled o relaci ladění do integrovaného vývojového prostředí.  
  
## <a name="session-debug-manager-operation"></a>Operace správce ladění relace  
 Správce ladění relace (SDM) spravuje DE. Může existovat více než jeden ladicí stroj běžící v počítači ve stejnou dobu. SDM multiplexovaný DEs, zabalí počet rozhraní z na algoritmus DEs a zveřejňuje rozhraní IDE, jako jednoho rozhraní.  
  
 Pokud chcete zvýšit výkon, nejsou multiplexní některá rozhraní. Místo toho se používají přímo z DE a volání pro tato rozhraní se nepřenášejí prostřednictvím SDM. Například nejsou multiplexní rozhraní používá s pamětí, kód a kontexty dokument, protože odkazují na konkrétní instrukce, paměť nebo dokumentu v konkrétní aplikaci ladit pomocí konkrétní DE. Žádné DE by se měl podílet na této úrovni komunikace.  
  
 Toto není platí pro všechny kontexty. Volání rozhraní kontextu vyhodnocení výrazu projít SDM. Při vyhodnocení výrazu SDM zabalí [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) rozhraní, které nabízí rozhraní IDE, protože při vyhodnocování tohoto výrazu může zahrnovat více DEs, který ladíte programy ve stejném procesu, který může být spuštění ve stejném vlákně.  
  
 SDM běžně slouží jako vhodný mechanismus delegování, ale může fungovat jako mechanismus všesměrového vysílání. Při vyhodnocení výrazu, například SDM slouží jako mechanismus všesměrového vysílání upozornit všechny DEs, aby mohli spouštět kód na zadaný podproces. Obdobně SDM obdrží událostí ukončení, vysílá na položku Všechny programy, že by se měla zastavit, spuštěná. Při volání krok SDM vysílá pro všechny aplikace, může i dál běží. Zarážky jsou všesměrového vysílání, na každý DE.  
  
 SDM nesleduje aktuální program, vlákno nebo blok zásobníku. Proces, program a vlákna informace se odesílají do SDM ve spojení s konkrétní ladění události.  
  
## <a name="see-also"></a>Viz také  
 [Ladicí stroj](../../extensibility/debugger/debug-engine.md)   
 [Komponenty ladicího programu](../../extensibility/debugger/debugger-components.md)   
 [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md)
