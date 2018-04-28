---
title: 'Krok 4: Přidejte k jednotlivým jmenovkám obslužnou rutinu události kliknutí'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: 16bdbc7c-4129-411d-bace-f4a3e5375975
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 79c1e6818686a944ac38637a705832f54ca51103
ms.sourcegitcommit: 04a717340b4ab4efc82945fbb25dfe58add2ee4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/28/2018
---
# <a name="step-4-add-a-click-event-handler-to-each-label"></a>Krok 4: Přidejte k jednotlivým jmenovkám obslužnou rutinu události kliknutí
Porovnávací hra probíhá takto:  

1.  Když hráč zvolí některý čtverec se skrytou ikonou, program zobrazí ikonu hráči změnou barvy ikony na černou.  

2.  Potom hráč zvolí jinou skrytou ikonu.  

3.  Jestliže se ikony shodují, zůstávají viditelné. Pokud tomu tak není, jsou obě ikony opět skryty.  
  
 Aby program fungoval, přidáte <xref:System.Windows.Forms.Control.Click> obslužné rutiny události, které změní barvu popisku, který je vybrán.  
  
## <a name="to-add-a-click-event-handler-to-each-label"></a>Chcete-li přidat k jednotlivým jmenovkám obslužnou rutinu události kliknutí  
  
1.  Otevřete formulář v **Návrhář formulářů Windows**. V **Průzkumníku řešení**, zvolte *Form1.cs* nebo *Form1.vb*. Na řádku nabídek zvolte **zobrazení** > **Návrhář**.  
  
2.  Vyberte první ovládací prvek popisku. Potom, podržte klávesu **Ctrl** klíče při každé z ostatních popisků a vybrat je zvolíte. Je nutné vybrat všechny popisky.  
  
3.  Zvolte **události** tlačítka na panelu nástrojů v **vlastnosti** okno zobrazení **události** stránku **vlastnosti** okno. Přejděte dolů k položce **klikněte na tlačítko** události a zadejte **label_Click** v poli, jak je znázorněno na následujícím obrázku.  

     ![Vlastnosti – okno zobrazení klikněte na událost](../ide/media/express_labelclick.png "Express_labelClick")  
**Vlastnosti** okno zobrazující **klikněte na tlačítko** událostí  
  
4.  Vyberte **Enter** klíč. Přidá rozhraní IDE `Click` volána obslužná rutina události `label_Click()` pomocí kódu a zachytí všechny popisky ve formuláři.  
  
5.  Vyplňte zbývající část kódu takto:  

     [!code-csharp[VbExpressTutorial4Step2_3_4#4](../ide/codesnippet/CSharp/step-4-add-a-click-event-handler-to-each-label_1.cs)]
     [!code-vb[VbExpressTutorial4Step2_3_4#4](../ide/codesnippet/VisualBasic/step-4-add-a-click-event-handler-to-each-label_1.vb)]  

    > [!NOTE]
    >  Pokud je kopírujete a vkládáte `label_Click()` blok kódu a místo zadávání kódu ručně, nezapomeňte nahradit existující `label_Click()` kódu. Jinak budete mít duplicitní kód bloku.  

    > [!NOTE]
    >  Můžete rozpoznat `object sender` v horní části obslužné rutiny události jako stejný jako ten, používány [kurzu 2: vytvoření matematického kvízu](../ide/tutorial-2-create-a-timed-math-quiz.md) kurzu. Protože připojili jste si jiný popisek – ovládací prvek klikněte na události na metodu jedna událost obslužné rutiny, stejné metoda je volána, bez ohledu na to, které popisek uživatel vybere. Metoda obslužné rutiny události musí znát, popisek, který jste vybrali, takže používá název `sender` k identifikaci ovládací prvek popisek. První řádek metody program informuje, že není právě generického objektu, ale specificky ovládací prvek popisek a tak používá název `clickedLabel` pro přístup k vlastnosti a metody popisku.  
  
     Tato metoda nejprve ověří, zda `clickedLabel` byl úspěšně převeden (cast) z objektu do ovládacího prvku popisek. Pokud úspěšné, má hodnotu `null` (C#) nebo `Nothing` (Visual Basic), a vy nechcete provést zbytek kód v metodě. V dalším kroku zkontroluje tato metoda vybraný štítek barvy pomocí jeho **ForeColor** vlastnost. Pokud je barva textu popisku černá, znamená to, že ikona již byla vybrána a metoda je provedena. (Který co je `return` nemá příkaz: obsahuje informace pro program, který chcete zastavit provádění metody.) V opačném případě ikona nebyla vybrána, takže program změní barvu textu popisku na černou.  
  
6.  Na řádku nabídek zvolte **soubor** > **Uložit vše** rozdělanou práci uložit, a potom na panelu nabídek vyberte **ladění** > **Start Ladění** váš program spustit. Měl by se zobrazit prázdný formulář s modrým pozadím. Vyberte jakékoli buňky ve formuláři. Měla by se zobrazit jedna z ikon. Pokračujte ve výběru různých míst ve formuláři. Ikony by se měly výběrem postupně zobrazovat.  
  
## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat  
  
-   Chcete-li přejít k dalšímu kroku kurzu, přečtěte si téma [krok 5: Přidejte odkazy na jmenovky](../ide/step-5-add-label-references.md).  
  
-   Chcete-li vrátit k předchozímu kroku kurzu, přečtěte si téma [krok 3: přiřaďte jednotlivým jmenovkám náhodné ikony](../ide/step-3-assign-a-random-icon-to-each-label.md).
