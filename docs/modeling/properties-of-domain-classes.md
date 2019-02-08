---
title: Vlastnosti tříd domény
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, domain class
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fb66a0d497c86091f689f119e57a5230f125e8de
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55938121"
---
# <a name="properties-of-domain-classes"></a>Vlastnosti tříd domény
Doménové třídy mají vlastnosti v následující tabulce. Informace o třídách domény najdete v tématu [porozumění modelům, třídám a vztahům](../modeling/understanding-models-classes-and-relationships.md). Další informace o tom, jak pomocí těchto vlastností najdete v tématu [přizpůsobení a rozšíření jazyka specifického pro doménu](../modeling/customizing-and-extending-a-domain-specific-language.md).

|Vlastnost|Popis|Výchozí|
|-|-|-|
|Modifikátor přístupu|Úroveň přístupu doménové třídy (`public` nebo `internal`).|`public`|
|Vlastní atributy|Použít k přidání atributů do třídy zdrojový kód, který je generován z této třídy domény.|\<žádné >|
|Generuje Double odvozené|Pokud `True`, se vygeneruje základní třídu a částečné třídy (pro podporu přizpůsobení pomocí přepisů). Další informace najdete v tématu [přepisování a rozšiřování třídy generované v](../modeling/overriding-and-extending-the-generated-classes.md).|`False`|
|Má vlastní konstruktor|Pokud `True`, poskytneme vám vlastního konstruktoru ve zdrojovém kódu. Další informace najdete v tématu [přepisování a rozšiřování třídy generované v](../modeling/overriding-and-extending-the-generated-classes.md).|`False`|
|Modifikátor dědičnosti|Popisuje druh dědičnosti třídy zdrojový kód, který je generován z doménové třídy (`none`, `abstract` nebo `sealed`).|`none`|
|Základní třída|Pokud je toto doménová třída odvozena, název základní třídy.|\<žádné >|
|Název|Název třídy této domény.|Aktuální název|
|Obor názvů|Obor názvů této doménové třídy.|Aktuální obor názvů|
|Poznámky|Neformální poznámky, které jsou přidružené k této doménové třídě.|\<žádné >|
|Popis|Popis, který se používá k dokumentu uživatelského rozhraní vygenerovaného návrháře.|\<žádné >|
|Zobrazovaný název|Název, který se zobrazí ve vygenerovaném návrháři u této doménové třídě.|\<žádné >|
|Klíčové slovo nápovědy|Nepovinné klíčové slovo, je použít k indexování nápovědy klávesy F1 pro tuto doménovou třídu.|\<žádné >|

## <a name="see-also"></a>Viz také

- [Glosář nástrojů jazyka specifického pro doménu](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)