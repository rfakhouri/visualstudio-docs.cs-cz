---
title: Vývoj aplikací pomocí návrháře pracovních postupů
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ecc9e42146bfa7de259551ff1c90d27201db5725
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31970122"
---
# <a name="developing-applications-with-the-workflow-designer"></a>Vývoj aplikací pomocí návrháře pracovních postupů

Návrháři pracovních postupů Windows je vizuálního návrháře a ladicí program pro grafické vytváření a ladění aplikace pro Windows Workflow Foundation (WF) v rozhraní .NET Framework 4, který je hostován ve vývojovém prostředí sady Visual Studio 2010. Umožňuje vytvořit aplikace složené pracovního postupu, knihovna aktivit nebo služby Windows Communication Foundation (WCF) pomocí šablony a návrháře aktivit. Další informace o pracovních postupech najdete v tématu [modelu Windows Workflow Foundation &#91;rozhraní .NET Framework 4&#93;](http://msdn.microsoft.com/Library/9a23ea6b-d600-483e-89cd-8889cfec5f66).

 Tady jsou některé nové funkce návrhu, které nastavit tuto novou verzi návrháře pracovních postupů vedle starších verzí návrháře pracovních postupů:

-   Návrhář postupu provádění vytvořená s využitím Windows Presentation Foundation (WPF). To vylepšuje možnosti Návrhář aktivity a zvyšuje výkon pro rozsáhlé a složité pracovní postupy.

-   Vlastní aktivity jsou nyní navrženy s [!INCLUDE[avalon2](../workflow-designer/includes/avalon2_md.md)], použití XAML a programovací model pro vytváření návrháře aktivit je jednodušší.

-   Vývojový diagram aktivity byl implementován, takže můžete vizualizovat toku programu pomocí známých vývojový diagram modelování styl.

-   Návrhář postupu provádění má nové proměnné návrháře umožňující deklarace a obor proměnné v rámci vaše pracovní postupy, vazba je pro aktivity.

-   V sadě Visual Studio 2010 návrháře pracovních postupů nabízí úplné funkce IntelliSense, při vytváření výrazy jazyka Visual Basic v rámci vaše pracovní postupy v rozhraní .NET Framework 4.

-   Zkušenosti s laděním teď zasahuje do XAML, abyste mohli nastavit zarážky ve vaší definice pracovního postupu XAML a ke kroku do kódu XAML v modul runtime, který poskytuje podobné jako v spravovaného kódu.

-   Opětovného hostování návrháře pracovních postupů mimo Visual Studio je výrazně jednodušší porovnání s předchozími verzemi, současnosti vyžaduje jenom pár řádků kódu.

-   Nové <xref:System.Activities.Statements.Flowchart> aktivita a její [vývojový diagram](../workflow-designer/flowchart-activity-designer.md) umožňují vizualizovat vaše toku programu pomocí známých vývojový diagram modelování stylu.

-   Zasílání zpráv aktivity vylepšily, což umožňuje zapsat plně deklarativního (žádný kód) služby Windows Communication Foundation (WCF).

-   **Přidat odkaz na službu...**  funkce vám umožní generovat aktivity, automaticky které přístup k webovým službám.