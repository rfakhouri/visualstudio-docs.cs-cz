---
title: Vlastnosti prostředí tvarů | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.dsltools.dsldesigner.compartmentshape
helpviewer_keywords:
- Domain-Specific Language, compartment shape
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 17e3b9dcc045cbcf1d2e0f2553c925bb99573865
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="properties-of-compartment-shapes"></a>Vlastnosti obrazců prostoru
Tvary prostředí jsou jedním z tvarů, které můžete použít k zobrazení třídu domény v jazyce specifické pro doménu. Můžete rozbalit nebo sbalit přihrádky.  
  
 Další informace najdete v tématu [jak definovat jazyka domény](../modeling/how-to-define-a-domain-specific-language.md). Další informace o tom, jak používat tyto vlastnosti najdete v tématu [přizpůsobení a rozšíření jazyka domény](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
 Obrazce prostředí mají vlastnosti, které jsou uvedeny v následující tabulce.  
  
|Vlastnost|Popis|Výchozí|  
|--------------|-----------------|-------------|  
|Výchozí rozbalte sbalit stavu|Pokud `Expanded`, ty prostředí jsou zobrazeny na vytvoření. Pokud `Collapsed`, nejsou.|Rozšířit|  
|Barva výplně|Barva výplně tento tvar.|prázdné|  
|Zadejte režim přechodu|Režim vyplnění přechodu tohoto tvaru.|vodorovné|  
|Geometrie|Geometrie tento tvar (obdélník nebo zaoblený obdélník).|rámeček|  
|Má výchozí body připojení|Pokud `True`tvar, který bude používat nahoru, dolů, doleva a správný připojovací body v Návrháři vygenerovaný.|False|  
|Je samostatný úsek záhlaví viditelné|Pokud `False`a tvar, který má jeden prostředí, hlavičku prostoru není viditelná.|Hodnota TRUE|  
|Barva obrysu|Obrysovou barvu tohoto tvaru.|černé|  
|Styl obrysu čárka|Styl obrysu dash tento tvar (ucelený, Dash, tečky, DashDot, DashDotDot, vlastní).|Plnou|  
|Tloušťka obrysu|Tloušťka obrysu tento tvar.|0.03125|  
|Barva textu|Barva použitá pro dekoratéry textu, které jsou přidruženy tento tvar.|černé|  
|Modifikátor přístupu|Úroveň přístupu prostředí tvaru (`public` nebo `internal`).|Public|  
|Vlastní atributy|Použít k přidání atributů do zdrojového kódu třídu, která se generují z tohoto prostoru pro obrazce|\<žádné >|  
|Generuje dvojitou odvozené|Pokud `True`, budou generovány základní třídu a částečné třídy (pro podporu přizpůsobení prostřednictvím přepsání). Další informace najdete v tématu [přepsání a rozšíření třídy generované](../modeling/overriding-and-extending-the-generated-classes.md).|False|  
|Má vlastní – konstruktor|Pokud `True`, bude k dispozici vlastní konstruktor v zdrojového kódu. Další informace najdete v tématu [přepsání a rozšíření třídy generované](../modeling/overriding-and-extending-the-generated-classes.md).|False|  
|Modifikátor dědičnosti|Popisuje typ dědičnosti zdrojovou třídu kódu, která se generují z prostoru pro tvaru (`none`, `abstract` nebo `sealed`).|Žádné|  
|Základní prostředí obrazce|Základní třída tento tvar.|(žádný)|  
|Název|Název tohoto tvaru.|Aktuální název|  
|Obor názvů|Obor názvů, který je přidružený tento tvar.|Aktuální obor názvů|  
|ToolTip – typ|Jak popisek je definována (pevná, proměnné nebo žádný). Pokud odstraněna, pak hodnota `Fixed Tooltip Text` vlastnost se používá jako popisek; Pokud proměnné, pak popisek je definována v vlastní kód.|žádná|  
|Poznámky|Neformální poznámky, které jsou přidruženy tento tvar.|\<žádné >|  
|Počáteční výšku.|Úvodní výšce tohoto tvaru, v palcích. Pro prostředí tvarů to je výšku pouze v záhlaví části a nebude možné změnit.|1|  
|Počáteční šířka|Počáteční šířka tohoto tvaru, v palcích.|1.5|  
|Barva výplně zveřejněné jako vlastnost<br /><br /> Režim zveřejněné vyplnění přechodu<br /><br /> Zveřejněné obrysovou barvu jako vlastnost<br /><br /> Styl obrysu Dash zveřejněné jako vlastnost<br /><br /> Vystavený Tloušťka obrysu jako vlastnost<br /><br /> Barva textu zpřístupňuje|Pokud `True`, může uživatel nastavit vlastnost stanovené obrazce. Chcete-li tuto možnost nastavíte, klikněte pravým tlačítkem na definici tvar a klikněte na **přidat zveřejněné**.|False|  
|Popis|Používá k dokumentu generovaný návrháře.|\<žádné >|  
|Zobrazovaný název|Název, který se zobrazí v Návrháři vygenerovaný pro tento tvar.|\<žádné >|  
|Opravené Text popisku|Text, který se používá pro pevnou popisek.|\<žádné >|  
|Nápověda – klíčové slovo|Klíčové slovo, které se používá k indexu F1 – Nápověda pro tento tvar.|\<žádné >|  
  
## <a name="see-also"></a>Viz také  
 [Glosář nástroje jazyka domény](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)