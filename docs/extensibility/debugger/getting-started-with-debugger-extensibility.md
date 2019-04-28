---
title: Začínáme s rozšiřitelností ladicího programu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- getting started, Debugging SDK
- debugging [Debugging SDK], getting started
- Debugging SDK, getting started
ms.assetid: d6ce6f43-1409-4bf7-93cd-f3464ca23504
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6f3fe14cff05f37ef7ee6f10026fd727696a223f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62925703"
---
# <a name="get-started-with-debugger-extensibility"></a>Začínáme s rozšiřitelností ladicího programu
[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] Poskytuje informace, které potřebujete k vytváření a přizpůsobování umožňuje ladit programy v rámci komponenty ladicího programu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] prostředí.

 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění bylo přidáno vylepšení se odvozené z rozsáhlé použitelnost testů na předchozí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladicí programy. Můžete použít [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění krokovat vícejazyčné aplikace, nebo můžete implementovat na průběžné úpravy proměnných při ladění aplikací a řešení pro více jazyků.

 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění je provedeno out-of-process program, který se právě ladí a proto je teď míň obtěžující do procesního prostoru aplikace. V důsledku toho je usnadňuje psaní součásti, které pracují s ladicím programem, aniž by to ovlivnilo ladicí program.

 Na co nejlíp využít [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)], měli byste se seznámit s následujícími položkami:

- [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Integrované vývojové prostředí (IDE)

- Programovací jazyk C++

- KNIHOVNY ATL MODELU COM

## <a name="in-this-section"></a>V tomto oddílu
 [Plán pro rozšíření ladicího programu](../../extensibility/debugger/roadmap-for-extending-the-debugger.md) popisuje proces implementace produktu, v závislosti na vaší kompilátoru a její výstup ladění.

 [Komponenty ladicího programu](../../extensibility/debugger/debugger-components.md) najdete zde přehled [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění komponenty, které zahrnují ladicího stroje (DE), Chyba při vyhodnocování výrazu (EE) a obslužné rutiny symbolů (SH).

 [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md) popisuje hlavní koncepty ladění architektury.

 [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md) vysvětluje, jak funguje ladicího stroje (DE) současně v kontextech hodnocení kódu, dokumentace a výraz. Popisuje všech třech kontextech, umístění, pozice nebo vyhodnocení relevantní k němu.

 [Ladění úlohy](../../extensibility/debugger/debugging-tasks.md) obsahuje odkazy na různé úlohy ladění, například spuštění programu a vyhodnocení výrazů.