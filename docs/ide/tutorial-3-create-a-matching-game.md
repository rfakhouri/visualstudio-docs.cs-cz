---
title: 'Kurz 3: Vytvoření odpovídající hry'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: 525815c8-2845-45e8-be96-100d1f144725
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dd560c6a3675617741f35f40d1fe23a70b482349
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="tutorial-3-create-a-matching-game"></a>Kurz 3: Vytvoření odpovídající hry
V tomto tutoriálu vytvoříte porovnávací hru, ve které hráč musí porovnat dvojice skrytých ikon. Získáte informace o následujících postupech:  

-   Ukládání objektů, např. ikony, `List` objektu.  

-   Použití `foreach` smyčky v jazyce Visual C# nebo `For Each` v jazyce Visual Basic k iteraci v rámci položky v seznamu.  

-   Udržování přehledu o stavu formuláře pomocí referenčních proměnných  

-   Sestavení obslužné rutiny události pro reakci na události, které lze použít s více objekty  

-   Vytvoření časovače, který odpočítává a po spuštění přesně jednou aktivuje událost  

 Po absolvování tohoto tutoriálu váš program bude vypadat jako na následujícím obrázku.  

 ![Herní, který vytvoříte v tomto kurzu](../ide/media/express_finishedgame.png "Express_FinishedGame")  
Hra, kterou vytvoříte v tomto tutoriálu  

 Si můžete stáhnout dokončené verzi příkladu [kurz ukázka dokončení odpovídající hra](http://code.msdn.microsoft.com/Complete-Matching-Game-4cffddba).  

> [!NOTE]
>  V tomto tutoriálu je zahrnut jazyk Visual C# i jazyk Visual Basic, takže se zaměřte na informace, které jsou specifické pro vámi používaný programovací jazyk.  

 Pokud si nevíte rady nebo máte otázky k programování, můžete zveřejnit svůj dotaz na jednom z diskuzních fór MSDN. V tématu [jazyka Visual Basic fórum](http://social.msdn.microsoft.com/Forums/home?forum=vbgeneral) a [Visual C# fórum](http://social.msdn.microsoft.com/Forums/home?forum=csharpgeneral). K dispozici jsou také užitečné bezplatné video výukové materiály. Další informace o programování v jazyce Visual Basic, najdete v části [základy jazyka Visual Basic: vývoj pro začátečníky absolutní](http://channel9.msdn.com/Series/Visual-Basic-Development-for-Absolute-Beginners). Další informace o programování v jazyce Visual C#, najdete v části [Základy C#: vývoj pro začátečníky absolutní](http://channel9.msdn.com/Series/C-Sharp-Fundamentals-Development-for-Absolute-Beginners).  

## <a name="related-topics"></a>Související témata  

|Název|Popis|  
|-----------|-----------------|  
|[Krok 1: Vytvořte projekt a přidejte do svého formuláře tabulku](../ide/step-1-create-a-project-and-add-a-table-to-your-form.md)|Začněte vytvořením projektu a přidávání `TableLayoutPanel` řízení zachovat ovládací prvky zarovnán správně.|  
|[Krok 2: Přidejte náhodný objekt a seznam ikon](../ide/step-2-add-a-random-object-and-a-list-of-icons.md)|Přidat `Random` objektu a `List` objekt k vytvoření seznamu ikon.|  
|[Krok 3: Přiřaďte jednotlivým jmenovkám náhodné ikony](../ide/step-3-assign-a-random-icon-to-each-label.md)|Přiřadit náhodně na ikony `Label` ovládací prvky, tak, aby každá hra se liší.|  
|[Krok 4: Přidejte k jednotlivým jmenovkám obslužnou rutinu události kliknutí](../ide/step-4-add-a-click-event-handler-to-each-label.md)|Přidejte obslužnou rutinu události Click, která změní barvu popisku, na který jste klikli.|  
|[Krok 5: Přidejte odkazy na jmenovky](../ide/step-5-add-label-references.md)|Přidejte referenční proměnné k udržení přehledu o tom, na jaké popisky jste klikli.|  
|[Krok 6: Přidejte časovač](../ide/step-6-add-a-timer.md)|Přidejte do formuláře časovač pro sledování času, který ve hře uběhl.|  
|[Krok 7: Uchovejte páry ve viditelném stavu](../ide/step-7-keep-pairs-visible.md)|Ponechte dvojice ikon viditelné, pokud je vybrána odpovídající dvojice.|  
|[Krok 8: Přidejte metodu k ověření, zda hráč vyhrál](../ide/step-8-add-a-method-to-verify-whether-the-player-won.md)|Přidat `CheckForWinner()` metodu k ověření, zda hráč vyhrál.|  
|[Krok 9: Vyzkoušejte jiné funkce](../ide/step-9-try-other-features.md)|Zkuste další funkce, jako je například změna ikon a barev, přidání mřížky a přidání zvuků. Zkuste zvětšit hrací plochu a nastavit časovač.|
