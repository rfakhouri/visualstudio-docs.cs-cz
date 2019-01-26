---
title: 'Krok 4: Rozvrhněte svůj formulář pomocí ovládacího prvku TableLayoutPanel'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 61acde79-e115-4bad-bb06-1fbe37717a3e
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: eda2189af9fd564c6240909e44db91f297b46b5a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54985965"
---
# <a name="step-4-lay-out-your-form-with-a-tablelayoutpanel-control"></a>Krok 4: Rozvrhněte svůj formulář pomocí ovládacího prvku TableLayoutPanel
V tomto kroku přidáte <xref:System.Windows.Forms.TableLayoutPanel> ovládací prvek do formuláře. TableLayoutPanel pomáhá správně Zarovnat ovládací prvky ve formuláři, který přidáte později.

 ![odkaz na video](../data-tools/media/playvideo.gif)video verzi tohoto tématu naleznete v tématu [kurz 1: Vytvoření prohlížeče obrázků v jazyce Visual Basic - Video 2](http://go.microsoft.com/fwlink/?LinkId=205211) nebo [kurz 1: Vytvoření prohlížeče obrázků v C# -2 videa](http://go.microsoft.com/fwlink/?LinkId=205200). Tato videa používají starší verzi sady Visual Studio, takže existují mírné rozdíly v některých příkazech nabídek a jiných prvcích uživatelského rozhraní. Nicméně koncepty a postupy fungují podobně jako v aktuální verzi sady Visual Studio.

## <a name="to-lay-out-your-form-with-a-tablelayoutpanel-control"></a>Chcete-li Rozvrhněte svůj formulář pomocí ovládacího prvku TableLayoutPanel

1.  Na levé straně rozhraní IDE sady Visual Studio, vyhledejte **nástrojů** kartu. Zvolte **nástrojů** kartu a **nástrojů** se zobrazí. (Nebo v řádku nabídek zvolte **zobrazení** > **nástrojů**.)

2.  Výběrem symbolu malého trojúhelníku vedle **kontejnery** skupiny a otevře se, jak je znázorněno na následujícím obrázku.

     ![Skupina zásobníků](../ide/media/express_toolbox.png)
**kontejnery** skupiny

3.  Ovládací prvky jako tlačítka a zaškrtávací políčka, popisky můžete přidat do formuláře. Poklepejte na ovládací prvek TableLayoutPanel ve **nástrojů**. (Nebo, můžete přetáhnout ovládací prvek z panelu nástrojů do formuláře). Když toto provedete, rozhraní IDE přidá do svého formuláře ovládací prvek TableLayoutPanel, jak je znázorněno na následujícím obrázku.

     ![TableLayoutPanel – ovládací prvek](../ide/media/express_formtablelayout.png)
**TableLayoutPanel** ovládacího prvku

    > [!NOTE]
    >  Po přidání vašeho kontejneru TableLayoutPanel, pokud se zobrazí okno uvnitř formuláře s názvem **úlohy kontejneru TableLayoutPanel**, klikněte kamkoli do formuláře, abyste jej zavřeli. Později v tomto kurzu se dozvíte další informace o tomto okně.

     Všimněte si, že jak **nástrojů** rozšíří na pokrytí formuláře po výběru jeho karty a ukončí se po klikněte kamkoli mimo něj. To je funkce automatického skrytí rozhraní IDE. Chcete-li ho nebo vypnout pro kterékoliv okno výběrem ikony připínáčku v pravém horním rohu okna k přepnutí automatického schovávání a zamknutí na místě. Takto se zobrazí ikona připínáčku.

     ![Ikoně připínáčku](../ide/media/express_pushpintoolbox.png)
**připínáčku** ikonu

4.  Ujistěte se, že je vybrán kontejner TableLayoutPanel, zvolte ji. Můžete ověřit, jaké ovládací prvek je vybrán, pohlédnutím na rozevírací seznam v horní části **vlastnosti** okna, jak je znázorněno na následujícím obrázku.

     ![Okno Vlastnosti zobrazující ovládací prvek TableLayoutPanel](../ide/media/express_controlspropwin.png)
**vlastnosti** okno zobrazující **TableLayoutPanel** ovládacího prvku

5.  Zvolte **Alphabetical** tlačítko na panelu nástrojů **vlastnosti** okno. To způsobí, že seznam vlastností v **vlastnosti** okno k zobrazení v abecedním pořadí, které vám usnadní vyhledání vlastnosti v tomto kurzu.

6.  Selektor ovládacího prvku je rozevírací seznam v horní části **vlastnosti** okna. V tomto příkladu ukazuje, že ovládací prvek s názvem `tableLayoutPanel1` zaškrtnuto. Můžete vybrat ovládací prvky podle buď výběrem oblasti v **Návrháře formulářů Windows** nebo výběrem ze selektoru ovládacího prvku. Teď, když kontejner TableLayoutPanel vybrán, vyhledejte **Dock** vlastnost a zvolte **Dock**, musí být nastavená na **žádný**. Všimněte si, že na šipku rozevíracího seznamu se zobrazí vedle hodnoty. Klikněte na šipku a potom vyberte **vyplnit** tlačítko (velké tlačítko uprostřed), jak je znázorněno na následujícím obrázku.

     ![Okno Vlastnosti s výplně vybrané](../ide/media/express_docktable.png)
**vlastnosti** okno s **vyplnit** vybrané

     *Ukotvení* ve Visual Studiu odkazuje na když okno je připojen k jinému oknu nebo oblasti v rozhraní IDE. Například **vlastnosti** okno může být neukotveno – to znamená, Nepřipojeno a volně plovoucí v aplikaci Visual Studio – nebo ho lze ukotvit oproti **Průzkumníku řešení**.

7.  Poté, co nastavíte kontejneru TableLayoutPanel **Dock** vlastnost **vyplnit**, panel vyplní celý formulář. Pokud změníte velikost formuláře znovu, kontejner TableLayoutPanel zůstane ukotvený a změní velikost sebe sama na vhodnou.

    > [!NOTE]
    >  TableLayoutPanel funguje jako tabulka v aplikaci Microsoft Office Word: Má řádky a sloupce a jednotlivé buňky může zahrnovat více řádků a sloupců. Každá buňka může obsahovat jeden ovládací prvek (například tlačítko, zaškrtávací políčko nebo jmenovku). Váš kontejner TableLayoutPanel bude mít <xref:System.Windows.Forms.PictureBox> prvek rozložený přes celý horní řádek, <xref:System.Windows.Forms.CheckBox> ovládacího prvku v jeho levé dolní buňky a čtyři <xref:System.Windows.Forms.Button> ovládacích prvků v jejich pravém dolním rohu buňky.

8.  V současné době kontejner TableLayoutPanel má dva stejně velké řádky a dva stejně velké sloupce. Budete muset změnit jejich velikost, takže horní řádek a sloupec vpravo jsou oba mnohem větší. V **Návrháře formulářů Windows**, vyberte kontejner TableLayoutPanel. V pravém horním rohu je malé černé trojúhelníkové tlačítko, které se zobrazí takto.

     ![Trojúhelníkové tlačítko](../ide/media/express_iconblacktriangle.gif)
**trojúhelník** tlačítko

     Toto tlačítko znamená, že ovládací prvek má úkoly, které vám pomohou automaticky nastavit jeho vlastnosti.

9. Vyberte trojúhelník k zobrazení seznamu úloh ovládacího prvku, jak je znázorněno na následujícím obrázku.

     ![Úlohy třídy TableLayoutPanel](../ide/media/express_tablepanel.png)
**TableLayoutPanel** úlohy

10. Zvolte **upravit řádky a sloupce** úkol, který zobrazí **styly sloupců a řádků** okna. Zvolte **Sloupec1**a změňte jeho velikost na 15 procent zkontrolujte, zda **procent** tlačítko je vybraná a zadávání **15** v **procent** pole. (To <xref:System.Windows.Forms.NumericUpDown> ovládací prvek, který použijete v pozdějších kurzech.) Zvolte **Column2** a nastavte ho na 85 procent. Neklikejte **OK** tlačítko, protože okno se zavře. (Ale pokud tak učiníte, můžete znovu otevřít pomocí seznam úkolů.)

     ![Styly sloupců a řádků v kontejneru TableLayoutPanel](../ide/media/vs_tablelayoutpanel_setup.png)
**TableLayoutPanel** styly sloupců a řádků

11. Z **zobrazit** rozevíracího seznamu v horní části okna vyberte **řádků**. Nastavte **Row1** až 90 procent a **Row2** na 10 procent.

12. Zvolte **OK** tlačítko. Váš kontejner TableLayoutPanel by nyní mít velký horní řádek, malý dolní řádek, malý levý sloupec a velký pravý sloupec. Můžete změnit velikost řádků a sloupců v kontejneru TableLayoutPanel výběrem **tableLayoutPanel1** ve formuláři a přetažením ohraničení jeho řádku a sloupce.

     ![Form1 se změněnou velikostí TableLayoutPanel](../ide/media/vs_formafterlayoutpanel.png)
**Form1** se změněnou velikostí **kontejner TableLayoutPanel**

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

-   Přechod k dalšímu kroku výukového programu naleznete v tématu [krok 5: Přidejte do svého formuláře ovládací prvky](../ide/step-5-add-controls-to-your-form.md).

-   Chcete-li vrátit k předchozímu kroku tutoriálu, přečtěte si téma [krok 3: Nastavte vlastnosti svého formuláře](../ide/step-3-set-your-form-properties.md).
