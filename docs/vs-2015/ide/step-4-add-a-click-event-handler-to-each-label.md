---
title: 'Krok 4: Přidejte k jednotlivým jmenovkám obslužnou rutinu události Click | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 16bdbc7c-4129-411d-bace-f4a3e5375975
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 9f23d0593129cae2732c8b4df14b3f5e2d5a69f7
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60051372"
---
# <a name="step-4-add-a-click-event-handler-to-each-label"></a>Krok 4: Přidání obslužné rutiny události Click ke každému popisku
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Porovnávací hra probíhá takto:  
  
1. Když hráč zvolí některý čtverec se skrytou ikonou, program zobrazí ikonu hráči změnou barvy ikony na černou.  
  
2. Potom hráč zvolí jinou skrytou ikonu.  
  
3. Jestliže se ikony shodují, zůstávají viditelné. Pokud tomu tak není, jsou obě ikony opět skryty.  
  
   Aby program takto fungoval, přidejte obslužnou rutinu události Click, která změní barvu vybraného popisku.  
  
### <a name="to-add-a-click-event-handler-to-each-label"></a>Přidání obslužné rutiny události Click ke každému popisku  
  
1. Otevřete formulář v Návrháři formulářů Windows. V Průzkumníku řešení vyberte soubor Form1.cs nebo Form1.vb. V panelu nabídky zvolte **zobrazení**, **návrháře**.  
  
2. Vyberte první ovládací prvek popisku. Potom podržte klávesu Ctrl a postupně klikněte na každý další popisek, abyste je vybrali. Je nutné vybrat všechny popisky.  
  
3. Zvolte **události** tlačítko na panelu nástrojů v **vlastnosti** okno zobrazení **události** stránku **vlastnosti** okna. Přejděte dolů k položce **klikněte na tlačítko** události a zadejte **výraz label_Click** v poli, jak je znázorněno na následujícím obrázku.  
  
     ![Okno Vlastnosti zobrazující klikněte na událost](../ide/media/express-labelclick.png "Express_labelClick")  
Okno Vlastnosti zobrazující událost Click  
  
4. Poté stiskněte klávesu ENTER. Rozhraní IDE přidá obslužnou rutinu události Click, která se nazývá `label_Click()` kódu a připojí ji k jednotlivým popiskům ve formuláři.  
  
5. Vyplňte zbývající část kódu takto:  
  
     [!code-csharp[VbExpressTutorial4Step2_3_4#4](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial4step2_3_4/cs/form1.cs#4)]
     [!code-vb[VbExpressTutorial4Step2_3_4#4](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial4step2_3_4/vb/form1.vb#4)]  
  
    > [!NOTE]
    >  Pokud zkopírujete a vložíte `label_Click()` blok kódu, spíše než ručního zadání kódu, nezapomeňte nahradit stávající `label_Click()` kódu. Jinak budete mít duplicitní kód bloku.  
  
    > [!NOTE]
    >  Můžete rozpoznat `object sender` v horní části obslužné rutiny události jako stejný jako ten používané [kurz 2: Vytvoření a Timed Math Quiz](../ide/tutorial-2-create-a-timed-math-quiz.md) kurzu. Protože jste připojili různé události Click ovládacího prvku popisku k jedné metodě obslužné rutiny události, volá se stejná metoda bez ohledu na to, který popisek uživatel zvolil. Metoda obslužné rutiny události potřebuje vědět, který popisek byl vybrán, takže použije jméno **odesílatele** k identifikaci ovládacího prvku popisku. První řádek metody dává pokyn programu, že není pouze obecný objekt, ale specificky ovládací prvek popisku a používá název **clickedLabel** pro přístup k vlastnostem a metodám popisku.  
  
     Tato metoda nejprve zkontroluje, jestli **clickedLabel** byl úspěšně převeden (přetypován) z objektu do ovládacího prvku popisku. Pokud neúspěšný, má hodnotu `null` (C#) nebo `Nothing` (Visual Basic), a nechcete provést zbytek kódu v metodě. Dále metoda zkontroluje barvu textu vybraného popisku pomocí popisku **ForeColor** vlastnost. Pokud je barva textu popisku černá, znamená to, že ikona již byla vybrána a metoda je provedena. (To `return` provádí příkaz: Říká programu, že má zastavit spouštění metody.) V opačném případě ikona nebyla vybrána, takže program změní barvu textu popisku na černou.  
  
6. V panelu nabídky zvolte **souboru**, **Uložit vše** rozdělanou práci uložit, a pak na panelu nabídek zvolte **ladění**, **spustit ladění** ke spuštění váš program. Měl by se zobrazit prázdný formulář s modrým pozadím. Vyberte jakékoli buňky ve formuláři. Měla by se zobrazit jedna z ikon. Pokračujte ve výběru různých míst ve formuláři. Ikony by se měly výběrem postupně zobrazovat.  
  
### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat  
  
- Přechod k dalšímu kroku výukového programu naleznete v tématu [krok 5: Přidejte odkazy na jmenovky](../ide/step-5-add-label-references.md).  
  
- Chcete-li vrátit k předchozímu kroku tutoriálu, přečtěte si téma [krok 3: Přiřaďte jednotlivým jmenovkám náhodné ikony](../ide/step-3-assign-a-random-icon-to-each-label.md).
