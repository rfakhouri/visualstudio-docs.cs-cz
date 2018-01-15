---
title: "Vlastnosti konektorů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, connectors
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7874e3017c714f41a660f96bedbb126fe121086e
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/13/2018
---
# <a name="properties-of-connectors"></a>Vlastnosti konektorů
Konektory představují vztahy domén v generované návrháře.  
  
 Další informace najdete v tématu [jak definovat jazyka domény](../modeling/how-to-define-a-domain-specific-language.md). Další informace o tom, jak používat tyto vlastnosti najdete v tématu [přizpůsobení a rozšíření jazyka domény](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
 Konektory mít vlastnosti, které jsou uvedeny v následující tabulce.  
  
|Vlastnost|Popis|Výchozí|  
|--------------|-----------------|-------------|  
|Barva|Barva tohoto konektoru.|černé|  
|Přerušovaná čára|Přerušovaná čára řádku pro tento konektor (ucelený, čárku, tečku, DashDot, DashDotDot nebo vlastní).|Plnou|  
|Styl End zdroj|Styl end zdroj pro tento konektor (HollowArrow EmptyArrow, FilledArrow, EmptyDiamond, FilledDiamond nebo None).|Žádné|  
|Cílový End styl|Styl cílový end pro tento konektor (HollowArrow EmptyArrow, FilledArrow, EmptyDiamond, FilledDiamond nebo None).|Žádné|  
|Barva textu|Barva, který se používá pro dekoratéry textu, které jsou přidruženy tento konektor.|černé|  
|Tloušťka|Tloušťka čáry pro tento konektor se měří v palcích.|0.03125|  
|Modifikátor přístupu|Úroveň přístupu třídy (`public` nebo `internal`).|Public|  
|Vlastní atributy|Použít k přidání atributů do zdrojového kódu třídu, která se generují z tohoto konektoru.|\<žádné >|  
|Generuje dvojitou odvozené|Pokud `True`, budou generovány základní třídu a částečné třídy (pro podporu přizpůsobení prostřednictvím přepsání). Další informace najdete v tématu [přepsání a rozšíření třídy generované](../modeling/overriding-and-extending-the-generated-classes.md).|False|  
|Má vlastní – konstruktor|Pokud `True`, bude k dispozici vlastní konstruktor v zdrojového kódu. Další informace najdete v tématu [přepsání a rozšíření třídy generované](../modeling/overriding-and-extending-the-generated-classes.md).|False|  
|Modifikátor dědičnosti|Popisuje typ dědičnosti zdrojovou třídu kódu, která se generují z konektoru (`none`, `abstract` nebo `sealed`).|žádná|  
|Základní konektoru|Základní třída tohoto konektoru.|(žádný)|  
|Název|Název tohoto konektoru.|Aktuální název|  
|Obor názvů|Obor názvů, který je přidružený tento konektor.|Aktuální obor názvů|  
|ToolTip – typ|Jak popisek je definována (pevná, proměnné nebo žádný). Pokud odstraněna, pak hodnota `Fixed Tooltip Text` vlastnost se používá jako popisek; Pokud proměnné, pak popisek je definována v vlastní kód.|\<žádné >|  
|Poznámky|Neformální poznámky, které jsou přidruženy tento konektor.|\<žádné >|  
|Styl směrování|Styl, který se používá pro směrování konektor. A `Rectilinear` konektor umožňuje Pravoúhlá oplátku podle potřeby; `Straight` konektor neexistuje.|Lomené|  
|Barva zveřejněné jako vlastnost<br /><br /> Zveřejněné přerušovaná čára jako vlastnost<br /><br /> Tloušťka zveřejněné jako vlastnost<br /><br /> Barva textu zpřístupňuje|Pokud `True`, může uživatel nastavit vlastnost stanovené obrazce. Chcete-li tuto možnost nastavíte, klikněte pravým tlačítkem na definici tvar a klikněte na **přidat zveřejněné**.|False|  
|Popis|Používá k dokumentu generovaný návrháře.|\<žádné >|  
|Zobrazovaný název|Název, který se zobrazí v Návrháři vygenerovaný pro tento konektor.|\<žádné >|  
|Opravené Text popisku|Text, který se používá pro pevnou popisek.|\<žádné >|  
|Nápověda – klíčové slovo|Klíčové slovo, které se používá k indexu F1 – Nápověda pro tento element.|\<žádné >|  
  
## <a name="see-also"></a>Viz také  
 [Glosář nástroje jazyka domény](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)