---
title: Vlastnosti tříd domény
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, domain class
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 5d880ac873766c59adfa53e9e61a6ad13520c135
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31949020"
---
# <a name="properties-of-domain-classes"></a>Vlastnosti tříd domény
Třídy domény mají vlastnosti v následující tabulce. Informace o třídách domény najdete v tématu [Principy modely, třídy a vztahy](../modeling/understanding-models-classes-and-relationships.md). Další informace o tom, jak používat tyto vlastnosti najdete v tématu [přizpůsobení a rozšíření jazyka domény](../modeling/customizing-and-extending-a-domain-specific-language.md).

|Vlastnost|Popis|Výchozí|
|--------------|-----------------|-------------|
|Modifikátor přístupu|Úroveň přístupu třídy domény (`public` nebo `internal`).|`public`|
|Vlastní atributy|Použít k přidání atributů do zdrojového kódu třídu, která se generují z této třídy domény.|\<žádné >|
|Generuje dvojitou odvozené|Pokud `True`, budou generovány základní třídu a částečné třídy (pro podporu přizpůsobení prostřednictvím přepsání). Další informace najdete v tématu [přepsání a rozšíření třídy generované](../modeling/overriding-and-extending-the-generated-classes.md).|`False`|
|Má vlastní – konstruktor|Pokud `True`, bude k dispozici vlastní konstruktor v zdrojového kódu. Další informace najdete v tématu [přepsání a rozšíření třídy generované](../modeling/overriding-and-extending-the-generated-classes.md).|`False`|
|Modifikátor dědičnosti|Popisuje typ dědičnost třídy zdrojového kódu, která se generují z domény – třída (`none`, `abstract` nebo `sealed`).|`none`|
|Base – třída|Pokud je tato třída domény odvozený, název základní třídy.|\<žádné >|
|Název|Název třídy této domény.|Aktuální název|
|Obor názvů|Obor názvů, třídy této domény.|Aktuální obor názvů|
|Poznámky|Neformální poznámky, které jsou spojeny s touto třídou domény.|\<žádné >|
|Popis|Popis, který se používá k dokumentu uživatelského rozhraní vygenerovaný návrháře.|\<žádné >|
|Zobrazovaný název|Název, který se zobrazí v Návrháři vygenerovaný pro tuto třídu domény.|\<žádné >|
|Nápověda – klíčové slovo|Volitelné klíčové slovo, které se používá k indexu F1 – Nápověda pro tuto třídu domény.|\<žádné >|

## <a name="see-also"></a>Viz také

- [Glosář nástroje jazyka domény](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)