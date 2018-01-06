---
title: "Výběr šablony řešení jazyka domény | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language Tools, solution templates
ms.assetid: 9c05955f-1548-4df6-b09b-4b348823c237
caps.latest.revision: "24"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: b636ab7937c85199c26b8ce8a95fa33cdcc7976b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="choosing-a-domain-specific-language-solution-template"></a>Výběr šablony řešení jazyka specifického pro doménu
Pokud chcete vytvořit řešení jazyka domény, vyberte jednu z šablony řešení, které jsou k dispozici v Průvodci Návrhář jazyk specifické pro doménu. Výběrem šablony, která nejvíce podobá jazyk, který chcete vytvořit můžete minimalizovat úpravy, které je nutné provést k počáteční řešení.  
  
 Následující řešení šablony jsou dostupné v Průvodci Návrhář jazyk specifické pro doménu.  
  
|Šablony|Funkce|Popis|  
|--------------|--------------|-----------------|  
|Diagramy tříd|-Prostředí tvarů<br />– Dědičnost třída<br />-Vztah dědičnosti<br />-Tvar dědičnosti<br />-Vlastnosti vztahu|Tuto šablonu řešení použijte, pokud váš jazyk specifické pro doménu zahrnuje entity a vztahy, které mají vlastnosti. Tato šablona vytvoří specifické pro doménu jazyk, který vypadá takto: diagramů tříd UML. Hlavní entity jsou třídy a rozhraní, společně s přidružení, generalizace a implementace vztahy. Třídy nebo rozhraní se zobrazí jako pole, která obsahuje seznam atributů.|  
|Diagramy komponent|-Porty|Tuto šablonu řešení použijte, pokud jazyka specifické pro doménu obsahuje součásti, který je součástí softwaru system. Tato šablona vytvoří jazyk specifické pro doménu, která se podobá diagramy komponent UML. Hlavní entity, které jsou součástí a porty, které se zobrazují jako malé obrazce na vnější součástí.|  
|Diagramy toku úkolů|-Bitové kopie a geometrické obrazce<br />-   *Plaveckých drah*|Tuto šablonu řešení použijte, pokud váš jazyk specifické pro doménu obsahuje pracovní postupy, stavů nebo pořadí. Tato šablona vytvoří jazyk specifické pro doménu, která se podobá diagramy činnosti UML. Hlavní entity je aktivitou, a hlavní bude přechod mezi aktivitami. Šablona obsahuje několik dalších prvků jako počáteční stav, konečného stavu a synchronizace panelu.|  
|Minimální jazyk|-Jedné třídy a tvar<br />-Jeden vztah a konektor|Tuto šablonu řešení použijte, pokud váš jazyk specifické pro doménu není jevil jako další šablony. Tato šablona vytvoří specifické pro doménu jazyk, který má dvě třídy a jedna relace, která jsou reprezentována v **sada nástrojů** jako **pole** a **řádku**. Třídy a relace mít vlastnost příklad řetězec.|  
|Minimální WinForm návrháře|-Malá modelu.<br />– Windows formulář, který zobrazí modelu.|Tuto šablonu použijte, pokud chcete sestavit aplikaci, ve kterém je vázána DSL do formuláře Windows, nikoli grafický Návrhář.<br /><br /> Formulář, který funguje jako uživatelské rozhraní pro jazyk je ve složce Dsl\UI.<br /><br /> Měli byste vytvořit projekt před otevřením formuláře návrháře.<br /><br /> Další informace najdete v tématu [vytváření jazyk specifické pro doménu Windows Forms-Based](../modeling/creating-a-windows-forms-based-domain-specific-language.md).|  
|Návrhář minimální WPF|-Malá modelu<br />– Windows Presentation Foundation uživatelské rozhraní, které zobrazí modelu|Tuto šablonu použijte, pokud chcete sestavit aplikaci, ve kterém je vázána DSL uživatelské rozhraní WPF, nikoli grafický Návrhář.<br /><br /> Návrhář pro uživatelské rozhraní je ve složce Dsl\UI.<br /><br /> Měli byste vytvořit projekt před otevřením návrháře uživatelského rozhraní.<br /><br /> Další informace najdete v tématu [vytváření jazyk specifické pro doménu WPF-Based](../modeling/creating-a-wpf-based-domain-specific-language.md).|  
|Knihovna DSL|-Minimální knihovny|Tuto šablonu použijte, pokud chcete vytvořit definici částečné DSL, který lze importovat do jiné DSL definice.|  
  
## <a name="see-also"></a>Viz také  
 [Přehled Nástrojů DSL](../modeling/overview-of-domain-specific-language-tools.md)
