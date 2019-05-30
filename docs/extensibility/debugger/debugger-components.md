---
title: Komponenty ladicího programu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Visual Studio], components
- components [Visual Studio SDK], debugging
- debugging [Debugging SDK], components
ms.assetid: 8b8ab77f-a134-495c-be42-3bc51aa62dfb
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 28afdd7f12e7d83b042f5c705c85fa567fdbb979
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66345896"
---
# <a name="debugger-components"></a>Komponenty ladicího programu
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Ladicí program je implementovaný jako VSPackage a spravuje celou ladicí relaci. Relace ladění se skládá z následujících elementů:

- **Ladění balíčku:** [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Ladicí program poskytuje stejné uživatelské rozhraní bez ohledu na to, co je právě laděna.

- **Správce ladění relace (SDM):** Poskytuje konzistentní programové rozhraní do [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladicí program pro správu různých ladicí stroj. Je implementováno [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

- **Správce ladění procesu (PDM):** Pro všechny spuštěné instance spravuje [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], seznam všech programů, které mohou být nebo jsou právě laděny. Je implementováno [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

- **Ladicí stroj (DE):** Je zodpovědný za monitorování program laděn, stav běžící program SDM a PDM komunikaci a interakci s vyhodnocovací filtr výrazů a poskytovatel symbolů poskytnout analýza v reálném čase stavu paměti programu a proměnné. Je implementováno [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] (pro jazyky podporuje) a externích dodavatelů, kteří chtějí podporují vlastní běhu.

- **Vyhodnocovací filtr výrazů (EE):** Poskytuje podporu pro dynamicky vyhodnocovat proměnné a výrazy zadaný uživatelem, když program se zastavil v určitém místě. Je implementováno [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] (pro jazyky podporuje) a jiných dodavatelů, kteří požadují pro podporu jejich jazycích.

- **Poskytovatel symbolů (SP):** Zkratka obslužnou rutinu symbolů, mapuje symboly pro ladění programu spuštěné instance programu tak, aby smysluplné informace lze zadat (například úroveň zdrojového kódu, ladění a vyhodnocení výrazu). Je implementováno [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] (pro modul Common Language Runtime [CLR] symboly a databáze programu [PDB] symbol formátu souboru) a jiných dodavatelů, kteří mají své vlastní proprietární metodou ukládání informací o ladění.

  Následující diagram znázorňuje vztah mezi těmito elementy ladicího programu sady Visual Studio.

  ![Přehled komponenty ladění](../../extensibility/debugger/media/dbugcompovrview.gif "DBugCompOvrview")

## <a name="in-this-section"></a>V tomto oddílu
 [Ladění balíčku](../../extensibility/debugger/debug-package.md) popisuje ladit balíček, který se spouští v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] shell a zpracovává všechny uživatelské rozhraní.

 [Správce ladění procesu](../../extensibility/debugger/process-debug-manager.md) poskytuje přehled funkcí PDM, což je správce procesy, které lze ladit.

 [Správce ladění relace](../../extensibility/debugger/session-debug-manager.md) definuje SDM, který poskytuje jednotný přehled o relaci ladění do integrovaného vývojového prostředí. SDM spravuje DE.

 [Ladicí stroj](../../extensibility/debugger/debug-engine.md) dokumenty ladění služby, které poskytuje DE.

 [Provozní režimy](../../extensibility/debugger/operational-modes.md) najdete zde přehled tří režimů, ve kterých mohou pracovat integrovaném vývojovém prostředí: návrh režimu a režimu spuštění, režimu pozastavení. Přechod mechanismy jsou také popsány.

 [Chyba při vyhodnocování výrazu](../../extensibility/debugger/expression-evaluator.md) vysvětlující účel EE v době běhu.

 [Poskytovatel symbolů](../../extensibility/debugger/symbol-provider.md) Tento článek popisuje, jak v implementaci, poskytovatel symbolů vyhodnocuje proměnné a výrazy.

 [Typ vizualizéru a vlastní prohlížeč](../../extensibility/debugger/type-visualizer-and-custom-viewer.md) popisuje typ vizualizéru a vlastní prohlížeč a jakou roli hraje vyhodnocovací filtr výrazů i podpoře.

## <a name="related-sections"></a>Související oddíly
 [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md) popisuje hlavní koncepty ladění architektury.

 [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md) vysvětluje, jak funguje DE současně v kontextech hodnocení kódu, dokumentace a výraz. Popisuje všech třech kontextech, umístění, pozice nebo vyhodnocení relevantní k němu.

 [Ladění úlohy](../../extensibility/debugger/debugging-tasks.md) obsahuje odkazy na různé úlohy ladění, například spuštění programu a vyhodnocení výrazů.

## <a name="see-also"></a>Viz také:
- [Začínáme](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)