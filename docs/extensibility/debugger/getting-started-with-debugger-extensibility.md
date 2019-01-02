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
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8db5e9d42036a7e4b5f1726e2771e143395c5820
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53833255"
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
 [Plán pro rozšíření ladicího programu](../../extensibility/debugger/roadmap-for-extending-the-debugger.md)  
 Popisuje proces implementace produktu, v závislosti na vaší kompilátoru a její výstup ladění.  
  
 [Komponenty ladicího programu](../../extensibility/debugger/debugger-components.md)  
 Najdete zde přehled [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění komponenty, které zahrnují ladicího stroje (DE), Chyba při vyhodnocování výrazu (EE) a obslužné rutiny symbolů (SH).  
  
 [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)  
 Popisuje hlavní koncepty ladění architektury.  
  
 [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md)  
 Vysvětluje, jak funguje ladicího stroje (DE) současně v kódu, dokumentace a kontexty vyhodnocení výrazu. Popisuje všech třech kontextech, umístění, pozice nebo vyhodnocení relevantní k němu.  
  
 [Ladění úloh](../../extensibility/debugger/debugging-tasks.md)  
 Obsahuje odkazy na různé úlohy ladění, jako je například spuštění programu a vyhodnocení výrazů.