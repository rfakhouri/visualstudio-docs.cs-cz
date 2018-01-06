---
title: "Začínáme s ladicí program rozšiřitelnost | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- getting started, Debugging SDK
- debugging [Debugging SDK], getting started
- Debugging SDK, getting started
ms.assetid: d6ce6f43-1409-4bf7-93cd-f3464ca23504
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 964b6bcc18e74174aa59e7a1bb4441e24d3918d7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="getting-started-with-debugger-extensibility"></a>Začínáme s rozšiřitelnost ladicí program
[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] Poskytuje informace, které musí mít vytvářet a přizpůsobovat ladicí program komponenty používané k ladění aplikací z uvnitř [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] prostředí.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]ladění přidala vylepšení odvozené z rozsáhlé použitelnost testování provádí na předchozí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladicí programy. Můžete použít [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění krok prostřednictvím vícejazyčné aplikace, nebo můžete implementovat na průběžně úpravy proměnných při ladění aplikace a řešení více jazyků.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]ladění je proveden out-of-process s programem laděné a je proto šetrnější v prostoru procesu aplikace. V důsledku toho je psát součásti, které pracují s ladicím programem, aniž by to ovlivnilo vaše ladicí program.  
  
 Nejlépe využít [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)], měli byste se seznámit s následující:  
  
-   [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Integrované vývojové prostředí (IDE)  
  
-   Programovacího jazyka C++  
  
-   ATL COM  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Plán pro rozšíření ladicího programu](../../extensibility/debugger/roadmap-for-extending-the-debugger.md)  
 Popisuje proces implementace ladění v produktu, v závislosti na vaší kompilátoru a její výstup.  
  
 [Komponenty ladicího programu](../../extensibility/debugger/debugger-components.md)  
 Obsahuje přehled [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění komponent, které zahrnují modul ladění (DE), vyhodnocovací filtr výrazů (EE) a symbol obslužné rutiny (SH).  
  
 [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)  
 Popisuje hlavní koncepty ladění architektury.  
  
 [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md)  
 Vysvětluje, jak funguje modul ladění (DE) současně v kódu, dokumentace a kontexty vyhodnocení výrazu. Popisuje, pro každou tři kontexty, umístění, pozice nebo vyhodnocení relevantní k němu.  
  
 [Úlohy ladění](../../extensibility/debugger/debugging-tasks.md)  
 Obsahuje odkazy na různé ladění úlohy, jako je například spuštěním programu a vyhodnocení výrazů.