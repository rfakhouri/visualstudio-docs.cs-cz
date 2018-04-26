---
title: 'Krok 9: Zrevidujte, okomentujte a otestujte svůj kód'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: f26f79ba-c91b-4164-b87f-679a1b231c09
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 955143c19d2e84da218032c46929015dc0a2c455
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="step-9-review-comment-and-test-your-code"></a>Krok 9: Zrevidujte, okomentujte a otestujte svůj kód
Dále přidejte komentář k vašeho kódu. Komentář je poznámka, která nelze změnit způsob, který se chová program. Umožňuje jednodušší někomu, kdo je čtení kód a co provádí. Přidávání komentářů do kódu je dobré která podporují nahrát do. V jazyce Visual C# dvě lomítka (/ /) označení řádku jako komentář. V jazyce Visual Basic jednoduché uvozovky (') slouží k označení řádku jako komentář. Po přidání komentáře otestujete váš program. Je vhodné spustit a otestovat kód často při práci na projekty, aby bylo možné zachytit a opravili všechny problémy před kód získá složitější. To se označuje jako *iterativnější testování,*.  

 Právě jste vytvořili něco, který funguje, a sice ještě není Hotovo, můžete již načíst obrázek. Než přidejte komentář k kódu a otestovat ji, časově Seznamte se s koncepty kódu, protože se používají tyto koncepty často:  

-   Když dvakrát kliknuli **zobrazit obrázek** tlačítko v Návrháři formulářů Windows, rozhraní IDE automaticky přidalo *metoda* kódu vašeho programu.  

-   Metody jsou, jak můžete organizovat kód: je, jak je váš kód seskupeny dohromady.  

-   Ve většině případů, metodu provádí malý počet akcí v určitém pořadí, například jak vaše `showButton_Click()` metoda zobrazí dialogové okno a potom načte obrázek.  

-   Metoda je tvořen kód *příkazy*, nebo řádků kódu. Metoda si můžete představit jako způsob, jak vytvořit balíček kódu příkazy společně.  

-   Pokud je metoda spuštěna, nebo *názvem*, příkazy v metodě jsou spouštěny v pořadí, jeden po druhém, počínaje první z nich.  

     Následuje příklad příkazu.  

    ```csharp  
    pictureBox1.Load(openFileDialog1.FileName);  
    ```  

    ```vb  
    pictureBox1.Load(openFileDialog1.FileName)  
    ```  

     Příkazy jsou, ujistěte se, co vaše programy provádět akce. V jazyce Visual C# příkaz vždy končí středníkem. V jazyce Visual Basic je konci řádku konec příkazu. (Žádný středník není třeba v jazyce Visual Basic). Předchozí příkaz sděluje vaše `PictureBox` řízení se načíst soubor, který uživatel vybral s **OpenFileDialog** součásti.  

 ![odkaz na video](../data-tools/media/playvideo.gif "PlayVideo")video verzi tohoto tématu naleznete v části [kurzu 1: vytvoření prohlížeče obrázků v jazyce Visual Basic – Video 5](http://go.microsoft.com/fwlink/?LinkId=205216) nebo [kurzu 1: vytvoření prohlížeče obrázků v jazyce C# – Video 5](http://go.microsoft.com/fwlink/?LinkId=205206). Tyto videa pomocí starší verze sady Visual Studio, takže drobné rozdíly v některé příkazy a další prvky uživatelského rozhraní. Však koncepty a postupy fungují podobně jako v aktuální verzi sady Visual Studio.  

### <a name="to-add-comments"></a>K přidání komentářů  

1.  Přidejte následující komentář do vašeho kódu.  

     [!code-vb[VbExpressTutorial1Step9_10#1](../ide/codesnippet/VisualBasic/step-9-review-comment-and-test-your-code_1.vb)]
     [!code-csharp[VbExpressTutorial1Step9_10#1](../ide/codesnippet/CSharp/step-9-review-comment-and-test-your-code_1.cs)]  

    > [!NOTE]
    >  Vaše **showButton** Click tlačítka obslužné rutiny události je nyní dokončena a pracuje. Zahájili jste psaní kódu, počínaje `if` příkaz. `if` Příkaz je, jak zjistit vašeho programu: "Zkontrolujte tuto jednu věc a pokud je hodnota true, proveďte tyto akce." V takovém případě se zjistit vaše program k otevírání **otevřít soubor** dialogové okno, a pokud uživatel vybere soubor a vybere **OK** tlačítko, tento soubor v ovládacím prvku PictureBox.  

    > [!TIP]
    >  Rozhraní IDE je sestaveno snadno můžete napsat kód, a *výstřižky kódu* jsou jedním ze způsobů, které dělá. Fragment je zkratka, která je rozšířena do malé bloku kódu.  
    >   
    >  Zobrazí se všechny dostupné fragmenty kódu. Na řádku nabídek zvolte **nástroje**, **Správce fragmentů kódu**. Visual C# `if` fragment kódu je v **Visual C#** . V jazyce Visual Basic `if` fragmenty kódu jsou v **podmínky a smyčky**, **kódu, které vypadají**. Tento správce můžete procházet existující fragmenty nebo přidat vlastní fragmenty kódu.  
    >   
    >  Pokud chcete aktivovat fragment při psaní kódu, zadejte ho a zvolte klávesy TAB. Mnoho výstřižků se zobrazuje v **IntelliSense** okno, které je důvod, proč zvolit klávesy TAB dvakrát: nejdřív k výběru fragment kódu ze **IntelliSense** okno a potom říct IDE používat fragmentu. (Podporuje technologii IntelliSense `if` fragment kódu, ale ne `ifelse` fragment kódu.)  

2.  Před spuštěním programu, uložte program a vybrat **Uložit vše** tlačítka panelu nástrojů, které se zobrazí takto.  

     ![Uložit všechny tlačítka panelu nástrojů](../ide/media/express_iconsaveall.png "Express_IconSaveAll")  
Tlačítko Uložit vše  

     Můžete taky uložit program na panelu nabídek, zvolte **soubor**, **Uložit vše**. Je osvědčeným postupem uložte včas a často.  

     Když je spuštěn, váš program by měl vypadat jako na následujícím obrázku.  

     ![Obrázek prohlížeči](../ide/media/express_pictureviewerdonerun.png "Express_PictureViewerDoneRun")  
Prohlížeč obrázků  

### <a name="to-test-your-program"></a>K testování aplikace  

1.  Zvolte klávesy F5 nebo zvolte **spustit ladění** tlačítka panelu nástrojů.  

2.  Vyberte **zobrazit obrázek** tlačítko spustit kód, který jste napsali. Nejprve program otevře **otevření souboru** dialogové okno. Ověřte, že filtry zobrazují v **soubory typu** rozevíracím seznamu v dolní části dialogových oken. Pak přejděte do obrázku a otevřete jej. Obvykle můžete najít vzorové obrázky, dodávané s operačním systémem Windows ve vaší **dokumenty** složku, uvnitř **Moje Obrázky\Příklady obrázků** složky.  

    > [!NOTE]
    >  Pokud nevidíte všechny Image v **vyberte soubor s obrázkem** dialogu, ujistěte se, které "všechny soubory (*.\*)" filtru je vybraný v rozevíracím seznamu na pravé straně nižší dialogového okna.  

3.  Načtení obrázku a zobrazí se ve vašem PictureBox. Poté se pokuste změnit velikost formuláře přetažením jeho okrajů. Protože máte vaší PictureBox ukotven uvnitř ovládacího prvku TableLayoutPanel, které je ukotven uvnitř formuláře, vaší oblasti obrázku změní velikost sebe sama tak, aby je širší jako formulář a doplní nejvyšší 90 procent formuláře. To je důvod, proč jste použili kontejnery TableLayoutPanel a FlowLayoutPanel: jejich zachovat formuláře správné velikosti, když uživatel změní jeho velikost.  

     Nyní správné, větší obrázků přejděte přesahuje hranice váš prohlížeč obrázků. V dalším kroku přidáte kód, aby obrázky podle velikosti okna.  

### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat  

-   Chcete-li přejít k dalšímu kroku kurzu, přečtěte si téma [krok 10: psát kód pro přídavná tlačítka a zaškrtávací políčko](../ide/step-10-write-code-for-additional-buttons-and-a-check-box.md).  

-   Chcete-li vrátit k předchozímu kroku kurzu, přečtěte si téma [krok 8: zapište kód pro zobrazení obslužné rutiny události obrázek tlačítka](../ide/step-8-write-code-for-the-show-a-picture-button-event-handler.md).
