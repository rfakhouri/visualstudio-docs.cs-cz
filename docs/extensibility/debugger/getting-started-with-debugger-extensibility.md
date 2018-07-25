---
title: Začínáme s rozšiřitelností ladicího programu | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
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
ms.openlocfilehash: e1a812575d14ef6595d58cc3ecc5d9f94b8f5635
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/24/2018
ms.locfileid: "39231279"
---
# <a name="get-started-with-debugger-extensibility"></a>Začínáme s rozšiřitelností ladicího programu
[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] Poskytuje informace, které potřebujete k vytváření a přizpůsobování umožňuje ladit programy v rámci komponenty ladicího programu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] prostředí.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění bylo přidáno vylepšení se odvozené z rozsáhlé použitelnost testů na předchozí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladicí programy. Můžete použít [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění krokovat vícejazyčné aplikace, nebo můžete implementovat na průběžné úpravy proměnných při ladění aplikací a řešení pro více jazyků.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění je provedeno out-of-process program, který se právě ladí a proto je teď míň obtěžující do procesního prostoru aplikace. V důsledku toho je usnadňuje psaní součásti, které pracují s ladicím programem, aniž by to ovlivnilo ladicí program.  
  
 Na co nejlíp využít [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)], měli byste se seznámit s následujícími položkami:  
  
-   [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Integrované vývojové prostředí (IDE)  
  
-   Programovací jazyk C++  
  
-   KNIHOVNY ATL MODELU COM  
  
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