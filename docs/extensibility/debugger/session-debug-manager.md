---
title: Správce ladění relace | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- session debug manager, unifying session views
- session debug manager, broadcasting
- debugging [Debugging SDK], session debug manager
- session debug manager
- session debug manager, debug engine multiplexing
- session debug manager, delegating
ms.assetid: fbb1928d-dddc-43d1-98a4-e23b0ecbae09
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6c7dd40796fbf0141cc60bf86204bce462594f8f
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66348568"
---
# <a name="session-debug-manager"></a>Správce ladění relace
Správce ladění relace (SDM) spravuje libovolný počet ladicí stroj (DE), které ladíte programy ve více procesech libovolný počet napříč libovolným počtem počítačů. Kromě toho, že ladicí stroj multiplexor SDM poskytuje jednotný přehled o relaci ladění do integrovaného vývojového prostředí.

## <a name="session-debug-manager-operation"></a>Operace správce ladění relace
 Správce ladění relace (SDM) spravuje DE. Může existovat více než jeden ladicí stroj běžící v počítači ve stejnou dobu. SDM multiplexovaný DEs, zabalí počet rozhraní z na algoritmus DEs a zveřejňuje rozhraní IDE, jako jednoho rozhraní.

 Pokud chcete zvýšit výkon, nejsou multiplexní některá rozhraní. Místo toho se používají přímo z DE a volání těchto rozhraní neprochází přes SDM. Například nejsou multiplexní rozhraní používá s pamětí, kód a kontexty dokument, protože odkazují na konkrétní instrukce, paměť nebo dokumentu v konkrétní aplikaci ladit pomocí konkrétní DE. Žádné DE by se měl podílet na této úrovni komunikace.

 Toto není platí pro všechny kontexty. Volání rozhraní kontextu vyhodnocení výrazu projít SDM. Při vyhodnocení výrazu SDM zabalí [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) rozhraní, které nabízí rozhraní IDE, protože při vyhodnocování tohoto výrazu může zahrnovat více DEs, který ladíte programy ve stejném procesu, který může být spuštění ve stejném vlákně.

 SDM běžně slouží jako vhodný mechanismus delegování, ale může fungovat jako mechanismus všesměrového vysílání. Při vyhodnocení výrazu, například SDM slouží jako mechanismus všesměrového vysílání upozornit všechny DEs, aby mohli spouštět kód na zadaný podproces. Obdobně SDM obdrží událostí ukončení, vysílá programů, že by se měla zastavit, spuštěná. Při volání krok SDM vysílá programy, může i dál běží. Zarážky jsou všesměrového vysílání, na každý DE.

 SDM nesleduje aktuální program, vlákno nebo blok zásobníku. Proces, program a informace o vláknech se odešlou do SDM ve spojení s konkrétní ladění události.

## <a name="see-also"></a>Viz také:
- [Ladicí stroj](../../extensibility/debugger/debug-engine.md)
- [Komponenty ladicího programu](../../extensibility/debugger/debugger-components.md)
- [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md)