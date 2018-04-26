---
title: 'Krok 1: Vytvořte projekt a přidejte do svého formuláře tabulku'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: 1cac4ba4-f3cd-43bd-ad5d-50fc599234e8
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3982370667ba76f15c5fc0bbcd52e5445d7bc9a1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="step-1-create-a-project-and-add-a-table-to-your-form"></a>Krok 1: Vytvořte projekt a přidejte do svého formuláře tabulku
Prvním krokem při vytváření porovnávací hry je vytvořit projekt a přidat tabulku do formuláře. Tabulka pomáhá zarovnat ikony do mřížky 4x4. Nastavením několika vlastností můžete také vylepšit vzhled hrací plochy.  

### <a name="to-create-a-project-and-add-a-table-to-your-form"></a>Vytvoření projektu a přidání tabulky do formuláře  

1.  Na řádku nabídek zvolte **soubor**, **nový**, **projektu**.  

2.  Pokud nepoužíváte Visual Studio Express, je nutné nejprve vybrat programovací jazyk. Z **nainstalovaných šablonách** vyberte buď **Visual C#** nebo **jazyka Visual Basic**.  

3.  V seznamu šablon projektu, zvolte **formulářové aplikace Windows**, název projektu **MatchingGame**a potom zvolte **OK** tlačítko.  

4.  V **vlastnosti** okno, nastavte následující vlastnosti formuláře.  

    1.  Změnit formuláře **Text** vlastnost z **Form1** k **odpovídající hra**. Tento text se zobrazí v horní části herního okna.  

    2.  Nastavte velikost formuláře na šířku 550 pixelů a výšku 550 pixelů. To provedete buď nastavením **velikost** vlastnost **550, 550**, nebo přetažením rohu formuláře, dokud neuvidíte správnou velikost v pravém horním rohu na integrované vývojové prostředí ( IDE).  

5.  Zobrazení panelu výběrem **sada nástrojů** karty na levé straně rozhraní IDE.  

6.  Přetáhněte `TableLayoutPanel` řídit z **kontejnery** kategorii v panelu nástrojů a nastavte následující vlastnosti pro ni.  

    1.  Nastavte **BackColor** vlastnost **hodnotu CornflowerBlue**. Chcete-li to provést, otevřete **BackColor** dialogové okno a vybrat na šipku rozevíracího seznamu vedle položky **BackColor** vlastnost v **vlastnosti** okno.  Pak zvolte **webové** ve **BackColor** dialogové okno zobrazení seznamu názvů dostupnou barvu.  

        > [!NOTE]
        >  Barvy nejsou zobrazeny v abecedním pořadí a položka CornflowerBlue je v dolní části seznamu.  

    2.  Nastavte **ukotvení** vlastnost **vyplnění** výběr rozevírací tlačítko u vlastnosti a zvolením velké prostřední tlačítko. Rozšíříte tak tabulku, aby zahrnovala celý formulář.  

    3.  Nastavte **CellBorderStyle** vlastnost **Inset**. Nastavíte tak vizuální hranice mezi každou buňkou na ploše.  

    4.  Kliknutím na tlačítko trojúhelníku v pravém horním rohu kontejneru TableLayoutPanel zobrazíte nabídku úloh.  

    5.  V nabídce úlohy zvolte **přidat řádek** na přidejte dva další řádky a potom vyberte dvakrát **přidat sloupec** dvakrát Chcete-li přidat další dva sloupce.  

    6.  V nabídce úlohy zvolte **úpravy řádků a sloupců** otevřete **styly řádku a sloupce** okno. Zvolte všechny sloupce, a potom vyberte **procent** možnost tlačítko a pak nastavte šířku každý sloupec na 25 procent celkové šířky. Potom vyberte **řádky** z rozevíracího pole v horní části okna a nastavte výšku každého řádku na 25 procent. Až budete hotoví, vyberte **OK** tlačítko.  

     Váš kontejner TableLayoutPanel by nyní měl být mřížka 4x4, se 16 stejně velkými čtvercovými buňkami. Na místě těchto řádků a sloupců se později zobrazí obrázky ikon.  

7.  Kontejner TableLayoutPanel musí být vybrán v editoru formuláře. Chcete-li to ověřit, měli byste vidět **tableLayoutPanel1** v horní části **vlastnosti** okno. Pokud není zaškrtnuto, zvolte TableLayoutPanel na formuláři, nebo ho vyberte v rozevíracím seznamu v horní části **vlastnosti** okno.  

     Kontejner TableLayoutPanel je vybráno, otevřete panel a přidat **popisek** ovládací prvek (umístěný ve **běžné ovládací prvky** kategorie) do levého horního buňky kontejneru TableLayoutPanel. `Label` Teď by měla být vybraný ovládací prvek v prostředí IDE. Nastavte pro něj následující vlastnosti.  

    1.  Ujistěte popisek **BackColor** je nastavena na **hodnotu CornflowerBlue**.  

    2.  Nastavte **AutoSize** vlastnost **False**.  

    3.  Nastavte **ukotvení** vlastnost **vyplnění**.  

    4.  Nastavte **zarovnání textu** vlastnost **MiddleCenter** výběr rozevírací tlačítko u vlastnosti a poté zvolením střední tlačítko. Ikona se tak zobrazí uprostřed buňky.  

    5.  Vyberte **písma** vlastnost. Tlačítko se třemi tečkami (...) by se zobrazit.  

    6.  Zvolte tlačítko se třemi tečkami a nastavte **písma** hodnotu **Webdings**, **styl písma** k **Bold**a **velikost** k **72**.  

    7.  Nastavte **Text** vlastnost popisku na písmeno **c**.  

         Levá horní buňka v kontejneru TableLayoutPanel by měla nyní obsahovat černé pole zarovnané na střed na modrém pozadí.  

        > [!NOTE]
        >  Písmo Webdings je písmo ikon dodávané s operačním systémem Windows. Ve vaší porovnávací hře musí hráči hledat dvojice ikon, takže toto písmo použijete k zobrazení ikon, které mají být spárovány. Místo vložení **c** v **Text** vlastnost, zkuste zadávání různých písmen, chcete-li zjistit, jaké ikony jsou zobrazeny. Vykřičník je pavouk, velké písmeno N je oko a čárka je čili paprička.  

8.  Zvolte svůj ovládací prvek popisku a zkopírujte jej na další buňku v kontejneru TableLayoutPanel. (Vyberte klávesy Ctrl + C nebo v řádku nabídek zvolte **upravit**, **kopie**.) Potom jej vložte. (Zvolte klávesy Ctrl + V, nebo v řádku nabídek zvolte **upravit**, **vložení**.) Kopie prvního popisku se zobrazí v druhé buňce kontejneru TableLayoutPanel. Vložit jej znovu a ve třetí buňce se zobrazí další popisek. Pokračujte ve vkládání `Label` prvky, dokud nejsou všechny buňky vyplněny.  

    > [!NOTE]
    >  Pokud popisek vložíte příliš často, rozhraní IDE přidá do kontejneru TableLayoutPanel nový řádek tak, aby bylo místo pro přidání nového ovládacího prvku popisku. Akci můžete vrátit zpět. Odebrat nové buňky, zvolte klávesy Ctrl + Z nebo na řádku nabídek zvolte **upravit**, **vrátit zpět**.  

     Rozvržení vašeho formuláře je nyní hotovo. Mělo by vypadat jako na následujícím obrázku.  

     ![Počáteční odpovídající herní formuláře](../ide/media/express_tut4step1.png "Express_Tut4Step1")  
Počáteční formulář porovnávací hry  

### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat  

-   Chcete-li přejít k dalšímu kroku kurzu, přečtěte si téma [krok 2: přidejte náhodný objekt a seznam ikon](../ide/step-2-add-a-random-object-and-a-list-of-icons.md).  

-   Přejděte k tématu Přehled, najdete v části [kurzu 3: vytvoření hry s odpovídajícím](../ide/tutorial-3-create-a-matching-game.md).
