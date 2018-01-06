---
title: "Vývoj aplikací pomocí návrháře pracovních postupů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "17"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 61d58b172c185a908a6314664ccd4cfe2172dc8c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="developing-applications-with-the-workflow-designer"></a>Vývoj aplikací pomocí návrháře pracovních postupů
[!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] Je vizuálního návrháře a ladicí program pro grafické vytváření a ladění [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] aplikace v [!INCLUDE[netfx40_long](../workflow-designer/includes/netfx40_long_md.md)] který je hostován v [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] vývojové prostředí. Umožňuje vytvořit aplikace složené pracovního postupu, knihovna aktivit nebo [!INCLUDE[indigo1](../workflow-designer/includes/indigo1_md.md)] službu pomocí šablony a návrháře aktivit. [!INCLUDE[crabout](../test/includes/crabout_md.md)]pracovní postupy, najdete v článku [modelu Windows Workflow Foundation &#91;. NET Framework 4 &#93; ](http://msdn.microsoft.com/Library/9a23ea6b-d600-483e-89cd-8889cfec5f66).  
  
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
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Používání návrháře postupu provádění](../workflow-designer/using-the-workflow-designer.md)  
 Ukazuje postup vytvoření nových aktivit a projektů pracovního postupu pomocí předdefinovaných Designer a jak použít jiné nástroje poskytované návrháře pro zpracování argumenty, proměnné, výrazy, import a navigace s popisem cesty.  
  
 [Používání návrhářů aktivit](../workflow-designer/using-the-activity-designers.md)  
 Popisuje kategorie aktivit a šablony a jejich návrhářů, které jsou k dispozici systému.  
  
 [Ladění pracovních postupů pomocí návrháře postupu provádění](../workflow-designer/debugging-workflows-with-the-workflow-designer.md)  
 Popisují, jak provést tradiční ladění postupy a také ladění XAML a výrazy.  
  
 [Nápověda k uživatelskému rozhraní návrháře postupu provádění](../workflow-designer/workflow-designer-ui-help.md)  
 Obsahuje témata kontextové nápovědy pro dialogová okna poskytované [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)], a také pokyny k funkce návrháře prostředí, klávesové zkratky a chybové zprávy.  
  
 [Vývoj aplikací pracovních postupů určených pro .NET Framework verze 3.0 nebo 3.5](../workflow-designer/developing-workflow-applications-targeting-the-dotnet-3-0-or-dotnet-3-5-framework.md)  
 Obsahuje pokyny k použití návrháře starší verze, která je cílena [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].  
  
 [Návrhář opětovného hostování &#91; Ukázky WF &#93;](http://msdn.microsoft.com/Library/b676ad31-5f64-4d84-9a36-b4d7113a2f4d)  
 Tento příklad ukazuje postup vytvoření rozložení WPF tak, aby obsahovala návrháře.  
  
 [Návrháři vlastních aktivit](/dotnet/framework/windows-workflow-foundation/samples/custom-activity-designers)  
 Tato část obsahuje ukázky aktivity, které používají vlastní Designer pro zobrazení v Návrháři pracovních postupů.