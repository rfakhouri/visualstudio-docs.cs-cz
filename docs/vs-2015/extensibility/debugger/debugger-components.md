---
title: Komponenty ladicího programu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Visual Studio], components
- components [Visual Studio SDK], debugging
- debugging [Debugging SDK], components
ms.assetid: 8b8ab77f-a134-495c-be42-3bc51aa62dfb
caps.latest.revision: 31
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 12f865e7d4c44cfa4002b330ed85ec95f95a8ef9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68200660"
---
# <a name="debugger-components"></a>Komponenty ladicího programu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Ladicí program je implementovaný jako VSPackage a spravuje celou ladicí relaci. Relace ladění se skládá z následujících elementů:  
  
- **Ladění balíčku:** [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Ladicí program poskytuje stejné uživatelské rozhraní bez ohledu na to, co je právě laděna.  
  
- **Správce ladění relace (SDM):** Poskytuje konzistentní programové rozhraní do [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ladicí program pro správu různých ladicí stroj. Je implementováno [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
- **Správce ladění procesu (PDM):** Pro všechny spuštěné instance spravuje [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], seznam všech programů, které mohou být nebo jsou právě laděny. Je implementováno [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
- **Ladicí stroj (DE):** Je zodpovědný za monitorování program laděn, stav běžící program SDM a PDM komunikaci a interakci s vyhodnocovací filtr výrazů a poskytovatel symbolů poskytnout analýza v reálném čase stavu paměti programu a proměnné. Je implementováno [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] (pro jazyky podporuje) a externích dodavatelů, kteří chtějí podporují vlastní běhu.  
  
- **Vyhodnocovací filtr výrazů (EE):** Poskytuje podporu pro dynamicky vyhodnocovat proměnné a výrazy zadaný uživatelem, když program se zastavil v určitém místě. Je implementováno [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] (pro jazyky podporuje) a jiných dodavatelů, kteří požadují pro podporu jejich jazycích.  
  
- **Poskytovatel symbolů (SP):** Zkratka obslužnou rutinu symbolů, mapuje symboly pro ladění programu spuštěné instance programu tak, aby smysluplné informace lze zadat (například úroveň zdrojového kódu, ladění a vyhodnocení výrazu). Je implementováno [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] (pro modul Common Language Runtime [CLR] symboly a databáze programu [PDB] symbol formátu souboru) a jiných dodavatelů, kteří mají své vlastní proprietární metodou ukládání informací o ladění.  
  
  Následující diagram znázorňuje vztah mezi těmito elementy ladicího programu sady Visual Studio.  
  
  ![Přehled komponenty ladění](../../extensibility/debugger/media/dbugcompovrview.gif "DBugCompOvrview")  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Ladění balíčku](../../extensibility/debugger/debug-package.md)  
 Tento článek popisuje ladit balíček, který se spouští v [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] shell a zpracovává všechny uživatelské rozhraní.  
  
 [Správce ladění procesu](../../extensibility/debugger/process-debug-manager.md)  
 Poskytuje přehled funkcí PDM, což je správce procesy, které lze ladit.  
  
 [Správce ladění relace](../../extensibility/debugger/session-debug-manager.md)  
 Definuje SDM, který poskytuje jednotný přehled o relaci ladění do integrovaného vývojového prostředí. SDM spravuje DE.  
  
 [Ladicí stroj](../../extensibility/debugger/debug-engine.md)  
 Ladění služby, které poskytuje DE dokumenty.  
  
 [Provozní režimy](../../extensibility/debugger/operational-modes.md)  
 Najdete zde přehled tří režimů, ve kterých mohou pracovat integrovaném vývojovém prostředí: návrh režimu a režimu spuštění, režimu pozastavení. Přechod mechanismy jsou také popsány.  
  
 [Vyhodnocovač výrazů](../../extensibility/debugger/expression-evaluator.md)  
 Vysvětluje účel EE v době běhu.  
  
 [Poskytovatel symbolů](../../extensibility/debugger/symbol-provider.md)  
 Tento článek popisuje, jak v implementaci, poskytovatel symbolů vyhodnocuje proměnné a výrazy.  
  
 [Vizualizér typů a vlastní prohlížeč](../../extensibility/debugger/type-visualizer-and-custom-viewer.md)  
 Tento článek popisuje, co se vizualizér typů a vlastní prohlížeč a jakou roli hraje vyhodnocovací filtr výrazů i podpoře.  
  
## <a name="related-sections"></a>Související oddíly  
 [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)  
 Popisuje hlavní koncepty ladění architektury.  
  
 [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md)  
 Vysvětluje, jak je DE pracuje současně v rámci kódu, dokumentace a kontexty vyhodnocení výrazu. Popisuje všech třech kontextech, umístění, pozice nebo vyhodnocení relevantní k němu.  
  
 [Úlohy ladění](../../extensibility/debugger/debugging-tasks.md)  
 Obsahuje odkazy na různé úlohy ladění, jako je například spuštění programu a vyhodnocení výrazů.  
  
## <a name="see-also"></a>Viz také  
 [Začínáme](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)
