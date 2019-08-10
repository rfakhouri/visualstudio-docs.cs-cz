---
title: 'Krok 4: Rozvržení formuláře pomocí ovládacího prvku TableLayoutPanel'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 61acde79-e115-4bad-bb06-1fbe37717a3e
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 269fa26b89ab1ca9165efa8eb8971731f078ec60
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68925935"
---
# <a name="step-4-lay-out-your-form-with-a-tablelayoutpanel-control"></a>Krok 4: Rozvržení formuláře pomocí ovládacího prvku TableLayoutPanel
V tomto kroku přidáte <xref:System.Windows.Forms.TableLayoutPanel> ovládací prvek do formuláře. Kontejner TableLayoutPanel pomáhá správně zarovnat ovládací prvky ve formuláři, který budete přidávat později.

![odkaz na video](../data-tools/media/playvideo.gif)ve verzi videa tohoto tématu najdete v [kurzu 1: Vytvoření prohlížeče obrázků ve Visual Basic – video 2](http://go.microsoft.com/fwlink/?LinkId=205211) nebo [kurz 1: Vytvoření prohlížeče obrázků ve C# videu 2.](http://go.microsoft.com/fwlink/?LinkId=205200) Tato videa používají starší verzi sady Visual Studio, takže existují mírné rozdíly v některých příkazech nabídky a dalších prvcích uživatelského rozhraní. Koncepty a postupy však fungují podobně v aktuální verzi sady Visual Studio.

## <a name="to-lay-out-your-form-with-a-tablelayoutpanel-control"></a>Rozložení formuláře pomocí ovládacího prvku TableLayoutPanel

1. Na levé straně integrovaného vývojového prostředí sady Visual Studio Najděte kartu **panel nástrojů** . Vyberte kartu **panel nástrojů** a zobrazí se **panel nástrojů** . (Nebo, na panelu nabídek, klikněte na tlačítko **Zobrazit** > **sadu nástrojů**.)

2. Vyberte symbol malého trojúhelníku vedle skupiny **kontejnery** a otevřete ho tak, jak je znázorněno na následujícím obrázku.

     ![Skupina kontejnerů skupiny](../ide/media/express_toolbox.png)
kontejnerů

3. Do formuláře můžete přidat ovládací prvky, jako jsou tlačítka, zaškrtávací políčka a popisky. Dvakrát klikněte na ovládací prvek TableLayoutPanel v **sadě nástrojů**. (Nebo můžete přetáhnout ovládací prvek z panelu nástrojů do formuláře.) Když to uděláte, rozhraní IDE přidá ovládací prvek TableLayoutPanel do formuláře, jak je znázorněno na následujícím obrázku.

     ![TableLayoutPanel –](../ide/media/express_formtablelayout.png)
ovládací prvek**TableLayoutPanel** ovládacího prvku

    > [!NOTE]
    > Po přidání kontejneru TableLayoutPanel, pokud se zobrazí okno v rámci formuláře s názvem **úlohy TableLayoutPanel**, vyberte libovolné místo ve formuláři a zavřete ho. Další informace o tomto okně se dozvíte později v tomto kurzu.

     Všimněte si, jak se **Sada nástrojů** rozšíří na pokrytí formuláře, když zvolíte jeho kartu a po výběru kamkoli mimo ni se zavře. To je funkce automatického skrývání rozhraní IDE. Můžete ji zapnout nebo vypnout pro kterékoli z oken tak, že vyberete ikonu připínáčku v pravém horním rohu okna a vypnete automatické skrývání a zamknete ho. Ikona připínáček se zobrazí takto.

     ![Ikona](../ide/media/express_pushpintoolbox.png)
připínáčku ikona**připínáčku**

4. Ujistěte se, že je kontejner TableLayoutPanel vybrán výběrem. Vybraný ovládací prvek můžete ověřit tak, že prohlížíte rozevírací seznam v horní části okna **vlastnosti** , jak je znázorněno na následujícím obrázku.

     ![Okno Vlastnosti zobrazení okna](../ide/media/express_controlspropwin.png)
**vlastností** ovládacího prvku TableLayoutPanel zobrazení ovládacího prvku **TableLayoutPanel**

5. Na panelu nástrojů v okně **vlastnosti** vyberte tlačítko **Abecední** . To způsobí, že se seznam vlastností v okně **vlastnosti** zobrazí v abecedním pořadí, což usnadňuje hledání vlastností v tomto kurzu.

6. Selektor ovládacího prvku je rozevírací seznam v horní části okna **vlastnosti** . V tomto příkladu ukazuje, že je vybrán ovládací prvek `tableLayoutPanel1` s názvem. Ovládací prvky můžete vybrat buď výběrem oblasti v **Návrhář formulářů** , nebo výběrem z voliče ovládacího prvku. Teď, když je vybraný kontejner TableLayoutPanel, Najděte vlastnost **Dock** a vyberte **Dock**, která by měla být nastavená na **none**. Všimněte si, že se vedle hodnoty zobrazí šipka rozevíracího seznamu. Zvolte šipku a potom vyberte tlačítko **vyplnit** (velké tlačítko uprostřed), jak je znázorněno na následujícím obrázku.

     ![Okno Vlastnosti s vybraným](../ide/media/express_docktable.png)
oknem**vlastností** Fill s vybraným nástrojem **Fill**

     *Ukotvení* v aplikaci Visual Studio odkazuje na to, kdy je okno připojeno k jinému oknu nebo oblasti v rozhraní IDE. Například může být okno **vlastnosti** neukotvené – tj. nepřipojené a bezplatné v rámci sady Visual Studio, nebo může být ukotveno proti **Průzkumník řešení**.

7. Jakmile nastavíte vlastnost **Dock** kontejneru TableLayoutPanel na hodnotu **Fill**, panel vyplní celý formulář. Pokud změníte velikost formuláře znovu, kontejner TableLayoutPanel zůstane ukotvený a mění se tak, aby odpovídal.

    > [!NOTE]
    > TableLayoutPanel funguje jako tabulka v systém Microsoft Office Word: Má řádky a sloupce a jednotlivá buňka může zahrnovat více řádků a sloupců. Každá buňka může obsahovat jeden ovládací prvek (například tlačítko, zaškrtávací políčko nebo popisek). Váš kontejner TableLayoutPanel bude mít <xref:System.Windows.Forms.PictureBox> ovládací prvek rozložený do celého horního <xref:System.Windows.Forms.CheckBox> řádku, ovládacího prvku v jeho levé dolní buňce a <xref:System.Windows.Forms.Button> čtyřmi ovládacími prvky v jeho pravé dolní buňce.

8. V současné době má kontejner TableLayoutPanel dva řádky stejné velikosti a dva sloupce se stejnou velikostí. Je potřeba změnit jejich velikost, aby horní řádek a pravý sloupec byly mnohem větší. V **Návrhář formulářů**vyberte kontejner TableLayoutPanel. V pravém horním rohu je malé černé trojúhelníkové tlačítko, které se zobrazí takto.

     ![Trojúhelníkové](../ide/media/express_iconblacktriangle.gif)
tlačítko tlačítka**trojúhelníku**

     Toto tlačítko indikuje, že ovládací prvek obsahuje úlohy, které vám pomůžou nastavit jeho vlastnosti automaticky.

9. Vyberte trojúhelník pro zobrazení seznamu úkolů ovládacího prvku, jak je znázorněno na následujícím obrázku.

     ![Úlohy TableLayoutPanel](../ide/media/express_tablepanel.png)
úlohy**TableLayoutPanel**

10. Vyberte úlohu **Upravit řádky a sloupce** , aby se zobrazilo okno **styly sloupců a řádků** . Vyberte **sloupec Sloupec1**a nastavte jeho velikost na 15 procent, a to tak, že vyberete tlačítko **procento** a do pole **procenta** zadáte **15** . (To <xref:System.Windows.Forms.NumericUpDown> je ovládací prvek, který budete používat v pozdějším kurzu.) Vyberte hodnotu **Sloupec2** a nastavte ji na 85 procent. Nevybírejte ještě tlačítko **OK** , protože okno se zavře. (Pokud to ale uděláte, můžete ho znovu otevřít pomocí seznamu úkolů.)

     ![Styly sloupců a řádků TableLayoutPanel ve sloupcích a sloupcích TableLayoutPanel ](../ide/media/vs_tablelayoutpanel_setup.png)


11. V rozevíracím seznamu **Zobrazit** v horní části okna vyberte možnost **řádky**. Nastavte **řádek1** na 90 procent a **řádek2** na 10 procent.

12. Zvolte **OK** tlačítko. Váš kontejner TableLayoutPanel by teď měl mít velký horní řádek, malý dolní řádek, malý levý sloupec a velký pravý sloupec. Můžete změnit velikost řádků a sloupců v kontejneru TableLayoutPanel výběrem **tableLayoutPanel1** ve formuláři a následným přetažením ohraničení jeho řádku a sloupce.

     ![Form1 se změněnou velikostí kontejneru](../ide/media/vs_formafterlayoutpanel.png)
TableLayoutPanel**Form1** se změněnou velikostí **TableLayoutPanel**

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

- Pokud chcete přejít na další krok kurzu, přečtěte si [krok 5: Přidejte ovládací prvky do formuláře](../ide/step-5-add-controls-to-your-form.md).

- Pokud se chcete vrátit k předchozímu kroku kurzu [, podívejte se na krok 3: Nastavte vlastnosti](../ide/step-3-set-your-form-properties.md)formuláře.
