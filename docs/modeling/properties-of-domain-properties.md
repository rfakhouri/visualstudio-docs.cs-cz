---
title: Vlastnosti vlastností domény
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, domain properties
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: e675d0c4cb7826fb0ddc56dc4491be5d126f3410
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="properties-of-domain-properties"></a>Vlastnosti vlastností domény
A *vlastnost domain* je funkce prvku modelu, který uchovává hodnotu. Například `Person` domény třída může mít vlastnosti `Name` a `BirthDate`. V definici DSL vlastnosti domény jsou uvedeny v poli Třída domény v diagramu a v části domény třídy v Průzkumníku DSL. Další informace najdete v tématu [jak definovat jazyka domény](../modeling/how-to-define-a-domain-specific-language.md).

> [!NOTE]
>  Slovo "vlastnost" se dvěma způsoby. A *vlastnost domain* je funkce, která můžete definovat na třídě domény. Naopak mít mnoho prvků DSL *vlastnosti*, které jsou uvedeny v **vlastnosti** okno v definici DSL. Například každá vlastnost domény má sadu vlastností, které jsou popsané v tomto tématu.

 V době běhu, když uživatel vytvoří instancí třídy domény, hodnoty vlastnosti domény se zobrazí v okně vlastností a mohou být zobrazeny na obrazce.

 Většina vlastnosti domény jsou implementované jako běžné vlastnosti CLR. Z programovací hlediska, mají vlastnosti domény rozšířenější funkce než normální program vlastnosti:

-   Můžete definovat pravidla a události, které monitorují stav vlastnost. Další informace najdete v tématu [reakce na a šíření změny](../modeling/responding-to-and-propagating-changes.md).

-   Transakce Zabraňte nekonzistentní stav. Další informace najdete v tématu [navigace a aktualizace modelu v programovém kódu](../modeling/navigating-and-updating-a-model-in-program-code.md).

 Vyberete-li v diagramu nebo v Průzkumníku DSL vlastnost Domain, zobrazí se následující položky v okně Vlastnosti. Další informace o tom, jak používat tyto položky najdete v tématu [přizpůsobení a rozšíření jazyka domény](../modeling/customizing-and-extending-a-domain-specific-language.md).

|Vlastnost|Popis|Výchozí hodnota|
|--------------|-----------------|-------------------|
|**Popis**|Popis, který se používá k dokumentu uživatelské rozhraní (UI) generovaný návrháře.|\<žádné >|
|**Zobrazovaný název**|Název, který se zobrazí v Návrháři vygenerovaný pro tuto vlastnost domény. Může obsahovat mezery nebo interpunkční znaménka, například "skladbu Title".|\<žádné >|
|**Element název zprostředkovatele**|Tuto možnost lze použít pouze v případě, že jste nastavili `Is Element Name` k `true`. Můžete napsat kód, který poskytuje název pro nového elementu třídy domény, přepsání výchozího nastavení.<br /><br /> V souboru kódu v projektu DSL, vytvořte třídu, která je odvozená od <xref:Microsoft.VisualStudio.Modeling.ElementNameProvider>.<br /><br /> Potom v Průzkumníku DSL, klikněte pravým tlačítkem na kořenovém DSL a klikněte na tlačítko Přidat externí typ. Zadejte název vaší třídy.<br /><br /> Vyberte tuto vlastnost domény znovu a v rozevíracím seznamu vyberte název třídy.|\<žádné >|
|**Metoda getter – modifikátor přístupu**|Úroveň přístupu třídy domény (`public` nebo `internal`). Tato volba určuje obor, ve které program kódu přístup k vlastnosti.|`public`|
|**Nápověda – klíčové slovo**|Volitelné klíčové slovo, které se používá k indexu F1 – Nápověda pro tuto vlastnost domény.|\<žádné >|
|**Se procházet**|Pokud `True`, vlastnost domain se zobrazí uživateli v okně vlastností, pokud tato DSL modely jsou otevřené.<br /><br /> Pokud `False`, vlastnost domain skryt v uživatelském rozhraní.<br /><br /> Pokud chcete, aby vlastnost domain viditelné, ale jen pro čtení, nastavte **je jen pro čtení uživatelského rozhraní**.|`True`|
|**Je název elementu**|Pokud `True`, zobrazí se tato vlastnost domény jako název elementu jeho modelu v Průzkumníku DSL.<br /><br /> Nové prvky modelu obdrží jedinečný výchozí hodnotu pro tuto vlastnost. Pokud chcete řídit způsob, jakým jsou tyto hodnoty vygeneruje, nastavte **Element název zprostředkovatele**.|`False`|
|**Je uživatelské rozhraní jen pro čtení**|Pokud `True`, hodnota vlastnosti domény nelze změnit pomocí uživatelského rozhraní. Může být nastavena stále programy a se nebude zobrazovat v okně Vlastnosti.<br /><br /> Pokud chcete skrýt vlastnost domény od uživatele, nastavte **je Procházet**. Pokud chcete řídit přístup programy, nastavte **– modifikátor přístupu Setter**.|`False`|
|**Typ**|Druh vlastnosti domény (`Normal`, `Calculated`, nebo `CustomStorage`). Další informace najdete v tématu [vypočítaná a vlastní vlastnosti úložiště](../modeling/calculated-and-custom-storage-properties.md).|`Normal`|
|**Jméno**|Název této vlastnosti domény. Musí být platný identifikátor, například **SongTitle**.|\<žádné >|
|**Poznámky**|Neformální poznámky, které jsou spojeny s touto vlastností domény.|\<žádné >|
|**Metoda setter – modifikátor přístupu**|Modifikátor přístupu pro nastavovací metoda. Tato volba určuje obor, v programu, který kód můžete nastavit vlastnost.|`public`|
|**Typ**|Typ vlastnosti. Pokud chcete přidat do seznamu dostupných typů, klikněte pravým tlačítkem na kořenovém DSL v Průzkumníku DSL a klikněte na **přidat externí typ**.|`String`|

## <a name="see-also"></a>Viz také

- [Glosář nástroje jazyka domény](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)