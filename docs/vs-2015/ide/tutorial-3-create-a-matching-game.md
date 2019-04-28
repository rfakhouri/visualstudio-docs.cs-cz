---
title: 'Kurz 3: Vytvořit odpovídající her | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 525815c8-2845-45e8-be96-100d1f144725
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: a7887df8a9dd012f1ec812f8bca38c1025ffe8a9
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63443236"
---
# <a name="tutorial-3-create-a-matching-game"></a>Kurz 3: Vytvoření hry s hledáním shody
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V tomto tutoriálu vytvoříte porovnávací hru, ve které hráč musí porovnat dvojice skrytých ikon. Získáte informace o následujících postupech:  
  
- Store objektů, například ikon, v `List` objektu.  
  
- Použití `foreach` smyčky v jazyce Visual C# nebo `For Each` smyčky v jazyce Visual Basic k iterování položek v seznamu.  
  
- Udržování přehledu o stavu formuláře pomocí referenčních proměnných  
  
- Sestavení obslužné rutiny události pro reakci na události, které lze použít s více objekty  
  
- Vytvoření časovače, který odpočítává a po spuštění přesně jednou aktivuje událost  
  
  Po absolvování tohoto tutoriálu váš program bude vypadat jako na následujícím obrázku.  
  
  ![Hra, kterou vytvoříte v tomto kurzu](../ide/media/express-finishedgame.png "Express_FinishedGame")  
  Hra, kterou vytvoříte v tomto tutoriálu  
  
  Chcete-li stáhnout úplnou verzi vzorku, přečtěte si téma [ukázkový kurz pro dokončení Porovnávací hra](http://code.msdn.microsoft.com/Complete-Matching-Game-4cffddba).  
  
> [!NOTE]
> V tomto tutoriálu je zahrnut jazyk Visual C# i jazyk Visual Basic, takže se zaměřte na informace, které jsou specifické pro vámi používaný programovací jazyk.  
  
 Pokud si nevíte rady nebo máte otázky k programování, můžete zveřejnit svůj dotaz na jednom z diskuzních fór MSDN. Zobrazit [fórum Visual Basic](http://social.msdn.microsoft.com/Forums/home?forum=vbgeneral) a [fórum Visual C#](http://social.msdn.microsoft.com/Forums/home?forum=csharpgeneral). K dispozici jsou také užitečné bezplatné video výukové materiály. Další informace o programování v jazyce Visual Basic najdete v tématu [základy jazyka Visual Basic: Vývoj pro naprosté začátečníky](http://channel9.msdn.com/Series/Visual-Basic-Development-for-Absolute-Beginners). Další informace o programování v jazyce Visual C#, naleznete v tématu [ C# základní informace: Vývoj pro naprosté začátečníky](http://channel9.msdn.com/Series/C-Sharp-Fundamentals-Development-for-Absolute-Beginners).  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Krok 1: Vytvoření projektu a přidání tabulky do formuláře](../ide/step-1-create-a-project-and-add-a-table-to-your-form.md)|Začněte vytvořením projektu a přidání `TableLayoutPanel` ovládacího prvku, aby ovládací prvky byly správně zarovnány.|  
|[Krok 2: Přidání náhodného objektu a seznamu ikon](../ide/step-2-add-a-random-object-and-a-list-of-icons.md)|Přidat `Random` objektu a `List` objekt k vytvoření seznamu ikon.|  
|[Krok 3: Přiřazení náhodné ikony každému popisku](../ide/step-3-assign-a-random-icon-to-each-label.md)|Náhodně přiřaďte ikony `Label` ovládací prvky, aby každé hra se liší.|  
|[Krok 4: Přidání obslužné rutiny události Click ke každému popisku](../ide/step-4-add-a-click-event-handler-to-each-label.md)|Přidejte obslužnou rutinu události Click, která změní barvu popisku, na který jste klikli.|  
|[Krok 5: Přidání odkazů popisků](../ide/step-5-add-label-references.md)|Přidejte referenční proměnné k udržení přehledu o tom, na jaké popisky jste klikli.|  
|[Krok 6: Přidání časovače](../ide/step-6-add-a-timer.md)|Přidejte do formuláře časovač pro sledování času, který ve hře uběhl.|  
|[Krok 7: Zachování dvojic ve viditelném stavu](../ide/step-7-keep-pairs-visible.md)|Ponechte dvojice ikon viditelné, pokud je vybrána odpovídající dvojice.|  
|[Krok 8: Přidání metody k ověření, jestli hráč vyhrál](../ide/step-8-add-a-method-to-verify-whether-the-player-won.md)|Přidat `CheckForWinner()` metodu k ověření, zda hráč zvítězil.|  
|[Krok 9: Vyzkoušení dalších funkcí](../ide/step-9-try-other-features.md)|Zkuste další funkce, jako je například změna ikon a barev, přidání mřížky a přidání zvuků. Zkuste zvětšit hrací plochu a nastavit časovač.|
