---
title: Začínáme s rozšiřitelností ladicího programu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- getting started, Debugging SDK
- debugging [Debugging SDK], getting started
- Debugging SDK, getting started
ms.assetid: d6ce6f43-1409-4bf7-93cd-f3464ca23504
caps.latest.revision: 18
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: d1c616c7cf8ed90ec3d76046892167b9b742a1b0
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60085672"
---
# <a name="getting-started-with-debugger-extensibility"></a>Začínáme s rozšiřitelností ladicího programu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

[!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)] Poskytuje informace, které potřebujete k vytváření a přizpůsobování umožňuje ladit programy v rámci komponenty ladicího programu [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] prostředí.  
  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ladění bylo přidáno vylepšení se odvozené z rozsáhlé použitelnost testů na předchozí [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ladicí programy. Můžete použít [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ladění krokovat vícejazyčné aplikace, nebo můžete implementovat na průběžné úpravy proměnných při ladění aplikací a řešení pro více jazyků.  
  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ladění je provedeno out-of-process program, který se právě ladí a proto je teď míň obtěžující do procesního prostoru aplikace. V důsledku toho je usnadňuje psaní součásti, které pracují s ladicím programem, aniž by to ovlivnilo ladicí program.  
  
 Na co nejlíp využít [!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)], měli byste se seznámit s následující:  
  
- [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Integrované vývojové prostředí (IDE)  
  
- Programovací jazyk C++  
  
- KNIHOVNY ATL MODELU COM  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Plán pro rozšíření ladicího programu](../../extensibility/debugger/roadmap-for-extending-the-debugger.md)  
 Popisuje proces implementace produktu, v závislosti na vaší kompilátoru a její výstup ladění.  
  
 [Komponenty ladicího programu](../../extensibility/debugger/debugger-components.md)  
 Najdete zde přehled [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ladění komponenty, které zahrnují ladicího stroje (DE), Chyba při vyhodnocování výrazu (EE) a obslužné rutiny symbolů (SH).  
  
 [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)  
 Popisuje hlavní koncepty ladění architektury.  
  
 [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md)  
 Vysvětluje, jak funguje ladicího stroje (DE) současně v kódu, dokumentace a kontexty vyhodnocení výrazu. Popisuje všech třech kontextech, umístění, pozice nebo vyhodnocení relevantní k němu.  
  
 [Úlohy ladění](../../extensibility/debugger/debugging-tasks.md)  
 Obsahuje odkazy na různé úlohy ladění, jako je například spuštění programu a vyhodnocení výrazů.
