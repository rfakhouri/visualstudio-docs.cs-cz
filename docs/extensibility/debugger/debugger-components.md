---
title: Ladicího programu součásti | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Visual Studio], components
- components [Visual Studio SDK], debugging
- debugging [Debugging SDK], components
ms.assetid: 8b8ab77f-a134-495c-be42-3bc51aa62dfb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b465772f8d3ddba173ecb406845f978765f63cdc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31108346"
---
# <a name="debugger-components"></a>Ladicí program komponenty
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Je implementovaný jako VSPackage a spravuje celý ladicí relace ladicí program. Relaci ladění zahrnuje následující prvky:  
  
-   **Balíček ladění:** [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladicí program poskytuje stejné uživatelské rozhraní bez ohledu na to, co ladit.  
  
-   **Správce ladicí relace (SDM):** poskytuje konzistentní programové rozhraní do [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladicí program ke správě různých modulů ladění. Je implementováno modulem [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
-   **Správce ladění procesu (PDM):** spravuje pro všech spuštěných instancích [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], seznam všechny programy, které může být nebo se právě ladí. Je implementováno modulem [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
-   **Ladění modulu (DE):** je odpovědná za monitorování program probíhá ladění, komunikaci stav spuštěným programem SDM a PDM a interakci s vyhodnocovací filtr výrazů a symbol zprostředkovatele, aby se zajistil analýzu v reálném čase Stav paměti programu a proměnné. Je implementováno modulem [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] (pro jazyky podporuje) a jiných dodavatelů, kteří chtějí pro podporu vlastních běhu.  
  
-   **Vyhodnocovací filtr výrazů (EE):** poskytuje podporu pro dynamicky vyhodnocení výrazů zadané uživatelem, když program se zastavilo na určitém místě a proměnné. Je implementováno modulem [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] (pro jazyky podporuje) a jiných dodavatelů, kteří chtějí podporovat jejich jazycích.  
  
-   **Symbol zprostředkovatele (SP):** označované taky jako obslužnou rutinu symbol mapuje symboly pro ladění programu na spuštěnou instanci program tak, aby důležité informace lze zadat (například ladění a výraz hodnocení úroveň zdrojového kódu). Je implementováno modulem [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] (pro modul Common Language Runtime [CLR] symboly a databáze programu [PDB] symbolů formát souboru) a pomocí jiných dodavatelů, kteří mají své vlastní vlastní metoda ukládání ladicí informace.  
  
 Následující diagram znázorňuje vztah mezi tyto prvky ladicího programu sady Visual Studio.  
  
 ![Přehled součásti ladění](../../extensibility/debugger/media/dbugcompovrview.gif "DBugCompOvrview")  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Ladění balíčku](../../extensibility/debugger/debug-package.md)  
 Popisuje ladění balíčku, který se spouští v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] prostředí shell a zpracovává všechny uživatelské rozhraní.  
  
 [Správce ladění procesu](../../extensibility/debugger/process-debug-manager.md)  
 Obsahuje přehled funkce PDM, což je správce procesů, které můžete ladit.  
  
 [Správce ladění relace](../../extensibility/debugger/session-debug-manager.md)  
 Definuje SDM, které poskytuje jednotný pohled na relaci ladění k prostředí IDE. SDM spravuje DE.  
  
 [Ladicí stroj](../../extensibility/debugger/debug-engine.md)  
 Ladění služby, které poskytuje DE dokumenty.  
  
 [Provozní režimy](../../extensibility/debugger/operational-modes.md)  
 Poskytuje přehled o tři režimy, ve kterých může fungovat i rozhraní IDE: režimu, režimu spuštění a pozastavení režimu návrhu. Přechod mechanismy jsou popsány i.  
  
 [Vyhodnocovač výrazů](../../extensibility/debugger/expression-evaluator.md)  
 Vysvětlující účel EE za běhu.  
  
 [Poskytovatel symbolů](../../extensibility/debugger/symbol-provider.md)  
 Popisuje, jak, v implementaci zprostředkovatele symbol vyhodnotí proměnné a výrazy.  
  
 [Vizualizér typů a vlastní prohlížeč](../../extensibility/debugger/type-visualizer-and-custom-viewer.md)  
 Popisuje, co je typ vizualizér a vlastní prohlížeč a jakou roli hrají vyhodnocovací filtr výrazů v doprovodné obě.  
  
## <a name="related-sections"></a>Související oddíly  
 [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)  
 Popisuje hlavní koncepty ladění architektury.  
  
 [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md)  
 Vysvětluje, jak funguje DE současně v kódu, dokumentace a kontexty vyhodnocení výrazu. Popisuje, pro každou tři kontexty, umístění, pozice nebo vyhodnocení relevantní k němu.  
  
 [Úlohy ladění](../../extensibility/debugger/debugging-tasks.md)  
 Obsahuje odkazy na různé ladění úlohy, jako je například spuštěním programu a vyhodnocení výrazů.  
  
## <a name="see-also"></a>Viz také  
 [Začínáme](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)