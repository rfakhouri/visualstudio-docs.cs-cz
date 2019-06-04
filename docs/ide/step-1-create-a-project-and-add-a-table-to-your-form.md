---
title: 'Krok 1: Vytvořte projekt a přidejte do svého formuláře tabulku'
ms.date: 05/31/2019
ms.topic: conceptual
ms.prod: visual-studio-windows
ms.technology: vs-ide-general
ms.assetid: 1cac4ba4-f3cd-43bd-ad5d-50fc599234e8
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 64ebd8469eb763af9565609dd680ba1e256ed6c5
ms.sourcegitcommit: aeb1a1135dd789551e15aa5124099a5fe3f0f32b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2019
ms.locfileid: "66501144"
---
# <a name="step-1-create-a-project-and-add-a-table-to-your-form"></a>Krok 1: Vytvořte projekt a přidejte do svého formuláře tabulku

Prvním krokem při vytváření porovnávací hry je vytvořit projekt a přidat tabulku do formuláře. Tabulka pomáhá zarovnat ikony do mřížky 4x4. Nastavením několika vlastností můžete také vylepšit vzhled hrací plochy.

## <a name="to-create-a-project-and-add-a-table-to-your-form"></a>Vytvoření projektu a přidání tabulky do formuláře

::: moniker range="vs-2017"

1. V panelu nabídky zvolte **souboru** > **nový** > **projektu**.

1. Zvolte buď **Visual C#**  nebo **jazyka Visual Basic** na levé straně **nový projekt** dialogové okno a potom vyberte **Windows Desktop**.

1. V seznamu šablon vyberte **aplikace Windows Forms (.NET Framework)** šablony, pojmenujte ho *Porovnávací hra*a klikněte na tlačítko **OK** tlačítko.

    Formulář, který je pojmenován *Form1.cs* nebo *Form1.vb* v závislosti na programovacím jazyce, který jste zvolili.

   > [!NOTE]
   > Pokud se nezobrazí **aplikace Windows Forms (.NET Framework)** šablony, instalace pomocí instalačního programu sady Visual Studio **vývoj desktopových aplikací .NET** pracovního vytížení.<br/><br/>![Úloha vývoj desktopových aplikací .NET v instalačním programu sady Visual Studio](../ide/media/dot-net-desktop-dev-workload.png)<br/><br/> Další informace najdete v tématu [instalace sady Visual Studio](../install/install-visual-studio.md) stránky.

::: moniker-end

::: moniker range="vs-2019"

1. V okně start zvolte **vytvořte nový projekt**.

   ![Zobrazit okno 'vytvořte nový projekt.](../get-started/media/vs-2019/create-new-project-dark-theme.png)

1. Na **vytvořte nový projekt** okno, zadejte nebo zadejte *Windows Forms* do vyhledávacího pole.

1. Zvolte **aplikace Windows Forms (.NET Framework)** šablony a klikněte na tlačítko **Další**.

   ![Výběr šablony jazyka Visual Basic pro aplikace Windows Forms (.NET Framework)](../get-started/visual-basic/media/vs-2019/vb-create-new-project-search-winforms-filtered.png)

   > [!NOTE]
   > Pokud se nezobrazí **aplikace Windows Forms (.NET Framework)** šablony, můžete jej nainstalovat z **vytvořte nový projekt** okna. V **nenašli, co hledáte?** zprávu, zvolte **nainstalovat další nástroje a funkce** odkaz.
   >
   > ![Odkaz "Nainstalovat další nástroje a funkce" z 'Nemůžete najít, co hledáte' zprávy v okně "vytvořit nový projekt.](../get-started/media/vs-2019/not-finding-what-looking-for.png)
   >
   > Dále zvolte v Visual Studio Installer, zvolte **vývoj desktopových aplikací .NET** pracovního vytížení.
   >
   > ![Úlohy .NET core v instalačním programu sady Visual Studio](../ide/media/install-dot-net-desktop-env.png)
   >
   > Po tomto, zvolte **změnit** tlačítko v instalačním programu sady Visual Studio. Můžete být vyzváni k uložte svou práci; Pokud ano, udělejte to. Dále zvolte **pokračovat** instalace zatížení.

1. V **konfigurovat nový projekt** okno, zadejte nebo vložte *Porovnávací hra* v **název projektu** pole. Potom kliknutím na možnost **vytvořit**.

::: moniker-end

## <a name="to-set-properties-for-a-form"></a>Chcete-li nastavit vlastnosti pro formulář

1. V **vlastnosti** okno, nastavte následující vlastnosti formuláře.

   1. Změna formuláře **Text** vlastnost z **Form1** k **Porovnávací hra**. Tento text se zobrazí v horní části herního okna.

   2. Nastavte velikost formuláře na šířku 550 pixelů a výšku 550 pixelů. Uděláte to buď tak, že nastavíte **velikost** vlastnost **550, 550**, nebo tažením rohu formuláře, dokud se nezobrazí správná velikost v pravém horním rohu na integrované vývojové prostředí ( INTEGROVANÉ VÝVOJOVÉ PROSTŘEDÍ).

2. Zobrazit panel nástrojů výběrem **nástrojů** karty na levé straně rozhraní IDE.

3. Přetáhněte <xref:System.Windows.Forms.TableLayoutPanel> ovládacího prvku **kontejnery** kategorie na panelu nástrojů a pak nastavte pro něj následující vlastnosti.

   1. Nastavte **BackColor** vlastnost **CornflowerBlue**. Chcete-li to provést, otevřete **BackColor** dialogové okno kliknutím na šipku rozevíracího seznamu vedle položky **BackColor** vlastnost **vlastnosti** okna.  Poté vyberte položku **webové** kartu **BackColor** dialogové okno k zobrazení seznamu názvů dostupných barev.

      > [!NOTE]
      > Barvy nejsou v abecedním pořadí a **CornflowerBlue** je v dolní části seznamu.

   2. Nastavte **Dock** vlastnost **vyplnit** výběrem rozevírací tlačítko vedle vlastnosti a kliknutím na velké prostřední tlačítko. Rozšíříte tak tabulku, aby zahrnovala celý formulář.

   3. Nastavte **CellBorderStyle** vlastnost **Inset**. Nastavíte tak vizuální hranice mezi každou buňkou na ploše.

   4. Kliknutím na tlačítko trojúhelníku v pravém horním rohu kontejneru TableLayoutPanel zobrazíte nabídku úloh.

   5. V nabídce úloh, zvolte **přidat řádek** dvakrát a přidejte další dva řádky, klikněte na tlačítko **přidat sloupec** dvakrát přidáte další dva sloupce.

   6. V nabídce úloh, zvolte **upravit řádky a sloupce** otevřít **styly sloupců a řádků** okna. Vyberte jednotlivé sloupce, vyberte **procent** přepínač a pak nastavte šířku každého sloupce na 25 procent celkové šířky. Potom vyberte **řádky** z rozevíracího seznamu pole v horní části okna a nastavte výšku každého řádku na 25 procent. Jakmile budete hotovi, zvolte **OK** tlačítko.

      Váš kontejner TableLayoutPanel by nyní měl být mřížka 4x4, se 16 stejně velkými čtvercovými buňkami. Na místě těchto řádků a sloupců se později zobrazí obrázky ikon.

4. Kontejner TableLayoutPanel musí být vybrán v editoru formuláře. Chcete-li to ověřit, měli byste vidět **tableLayoutPanel1** v horní části **vlastnosti** okna. Pokud není vybraná, vyberte TableLayoutPanel ve formuláři nebo jej zvolte v ovládacím prvku rozevíracího seznamu v horní části **vlastnosti** okna.

    Zatímco kontejner TableLayoutPanel vybrán, otevřete sadu nástrojů a přidejte <xref:System.Windows.Forms.Label> ovládacího prvku (umístěný ve **běžné ovládací prvky** kategorie) na levou horní buňky kontejneru TableLayoutPanel. Ovládací prvek popisku by teď měla být zaškrtnutá v integrovaném vývojovém prostředí. Nastavte pro něj následující vlastnosti.

   1. Ujistěte se, že popisku **BackColor** je nastavena na **CornflowerBlue**.

   2. Nastavte **AutoSize** vlastnost **False**.

   3. Nastavte **Dock** vlastnost **vyplnit**.

   4. Nastavte **TextAlign** vlastnost **MiddleCenter** výběrem rozevírací tlačítko vedle vlastnosti a pak kliknutím na prostřední tlačítko. Ikona se tak zobrazí uprostřed buňky.

   5. Zvolte **písmo** vlastnost. Tři tečky ( **...** ) by tlačítko mělo vypadat.

   6. Vyberte tlačítko se třemi tečkami a nastavte hodnotu **písmo** hodnota, která se **Webdings**, **styl písma** k **tučné**a **velikost** k **48**.

   7. Nastavte **Text** vlastnosti tohoto popisku na písmeno **c**.

        Levá horní buňka v kontejneru TableLayoutPanel by měla nyní obsahovat černé pole zarovnané na střed na modrém pozadí.

       > [!NOTE]
       > Písmo Webdings je písmo ikon dodávané s operačním systémem Windows. Ve vaší porovnávací hře musí hráči hledat dvojice ikon, takže toto písmo použijete k zobrazení ikon, které mají být spárovány. Namísto vložení hodnoty **c** v **Text** vlastnost, zkuste zadat různá písmena a zjistit, jaké ikony se zobrazí. Vykřičník je pavouk, velké písmeno N je oko a čárka je čili paprička.

5. Zvolte svůj ovládací prvek popisku a zkopírujte ho na další buňku v kontejneru TableLayoutPanel. (Zvolte **Ctrl**+**C** klíče, nebo na panelu nabídek zvolte **upravit** > **kopírování**.) Potom jej vložte. (Zvolte **Ctrl**+**V** klíče, nebo na panelu nabídek zvolte **upravit** > **vložit**.) Kopie prvního popisku se zobrazí v druhé buňce kontejneru TableLayoutPanel. Vložit jej znovu a jiný popisek se zobrazí ve třetí buňce. Pokračujte ve vkládání ovládací prvky popisku, dokud nejsou vyplněny všechny buňky.

   > [!NOTE]
   > Pokud vložíte příliš často, rozhraní IDE přidá nový řádek do kontejneru TableLayoutPanel, tak, aby měl místo pro přidání nového ovládacího prvku popisku. Akci můžete vrátit zpět. Chcete-li novou buňku odstranit, zvolte **Ctrl**+**Z** klíče, nebo na panelu nabídek zvolte **upravit** > **zpět**.

    Rozvržení vašeho formuláře je nyní hotovo. Mělo by vypadat jako na následujícím obrázku.

    ![Počáteční formulář porovnávací hry](../ide/media/express_tut4step1.png)<br/>   Počáteční formulář porovnávací hry

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

- Přechod k dalšímu kroku výukového programu naleznete v tématu [krok 2: Přidejte náhodný objekt a seznam ikon](../ide/step-2-add-a-random-object-and-a-list-of-icons.md).

- K návratu na téma přehledu přejděte [Tutorial 3: Vytvořit odpovídající her](../ide/tutorial-3-create-a-matching-game.md).
