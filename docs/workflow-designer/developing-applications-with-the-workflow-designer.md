---
title: "Vývoj aplikací pomocí návrháře pracovních postupů | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DefaultWorkflowDesigner
- DefaultWorkflowDesigner.UI
helpviewer_keywords:
- Visual Studio 2010 Workflow Designer [WFD], overview
- Workflow Designer [WFD]
- Visual Studio 2010 Workflow Designer [WFD]
- Workflow Designer [WFD], overview
ms.assetid: 4cd062b1-b496-4668-bbc1-ee85545e066d
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 75a6fb6eef1f5e8e174607ac141646ab237dd285
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="developing-applications-with-the-workflow-designer"></a>Vývoj aplikací pomocí návrháře pracovních postupů

Návrháři pracovních postupů Windows je vizuálního návrháře a ladicí program pro grafické vytváření a ladění [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] aplikace v [!INCLUDE[netfx40_long](../workflow-designer/includes/netfx40_long_md.md)] který je hostován v [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] vývojové prostředí. Umožňuje vytvořit aplikace složené pracovního postupu, knihovna aktivit nebo [!INCLUDE[indigo1](../workflow-designer/includes/indigo1_md.md)] službu pomocí šablony a návrháře aktivit. Další informace o pracovních postupech najdete v tématu [modelu Windows Workflow Foundation &#91;rozhraní .NET Framework 4&#93;](http://msdn.microsoft.com/Library/9a23ea6b-d600-483e-89cd-8889cfec5f66).

 Toto jsou některé nové funkce návrhu, které nastavit tuto novou verzi [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] vedle starších verzí [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]:

-   [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] Je sestaven pomocí [!INCLUDE[avalon1](../workflow-designer/includes/avalon1_md.md)]. To vylepšuje možnosti Návrhář aktivity a zvyšuje výkon pro rozsáhlé a složité pracovní postupy.

-   Vlastní aktivity jsou nyní navrženy s [!INCLUDE[avalon2](../workflow-designer/includes/avalon2_md.md)], použití XAML a programovací model pro vytváření návrháře aktivit je jednodušší.

-   Vývojový diagram aktivity byl implementován, takže můžete vizualizovat toku programu pomocí známých vývojový diagram modelování styl.

-   [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] Má nové proměnné návrháře umožňující deklarace a obor proměnné v rámci vaše pracovní postupy, je vytvoření vazby na aktivity.

-   V [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)], [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] nabízí úplné funkce IntelliSense, při vytváření výrazy jazyka Visual Basic v rámci vaší [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] pracovních postupů.

-   Zkušenosti s laděním teď zasahuje do XAML, abyste mohli nastavit zarážky ve vaší definice pracovního postupu XAML a ke kroku do kódu XAML v modul runtime, který poskytuje podobné jako v spravovaného kódu.

-   Opětovné hostování [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] mimo [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] je výrazně jednodušší porovnání s předchozími verzemi, současnosti vyžaduje jenom pár řádků kódu.

-   Nové <xref:System.Activities.Statements.Flowchart> aktivita a její [vývojový diagram](../workflow-designer/flowchart-activity-designer.md) umožňují vizualizovat vaše toku programu pomocí známých vývojový diagram modelování stylu.

-   Zasílání zpráv aktivity vylepšily, což umožňuje zapsat plně deklarativního (žádný kód) [!INCLUDE[indigo1](../workflow-designer/includes/indigo1_md.md)] služby.

-   **Přidat odkaz na službu...**  funkce vám umožní generovat aktivity, automaticky které přístup k webovým službám.