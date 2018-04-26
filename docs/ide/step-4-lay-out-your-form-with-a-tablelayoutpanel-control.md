---
title: 'Krok 4: Rozvrhněte svůj formulář pomocí ovládacího prvku TableLayoutPanel'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: 61acde79-e115-4bad-bb06-1fbe37717a3e
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 983bbd00eb3ae24ef0b3c3ed932e469dbf138a2e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="step-4-lay-out-your-form-with-a-tablelayoutpanel-control"></a>Krok 4: Rozvrhněte svůj formulář pomocí ovládacího prvku TableLayoutPanel
V tomto kroku přidáte `TableLayoutPanel` ovládacího prvku do svého formuláře. Kontejner TableLayoutPanel pomáhá správně zarovnání ovládacích prvků ve formuláři, který bude přidat později.  

 ![odkaz na video](../data-tools/media/playvideo.gif "PlayVideo")video verzi tohoto tématu naleznete v části [kurzu 1: vytvoření prohlížeče obrázků v jazyce Visual Basic – Video 2](http://go.microsoft.com/fwlink/?LinkId=205211) nebo [kurzu 1: vytvoření prohlížeče obrázků v jazyce C# – Video 2](http://go.microsoft.com/fwlink/?LinkId=205200). Tyto videa pomocí starší verze sady Visual Studio, takže drobné rozdíly v některé příkazy a další prvky uživatelského rozhraní. Však koncepty a postupy fungují podobně jako v aktuální verzi sady Visual Studio.  

### <a name="to-lay-out-your-form-with-a-tablelayoutpanel-control"></a>Chcete-li Rozvrhněte svůj formulář pomocí ovládacího prvku TableLayoutPanel  

1.  Na levé straně Visual Studio IDE, vyhledejte **sada nástrojů** kartě. Vyberte **sada nástrojů** kartě a sady nástrojů se zobrazí. (Nebo na řádku nabídek zvolte **zobrazení**, **sada nástrojů**.)  

2.  Zvolte symbol malý trojúhelník vedle **kontejnery** skupiny a otevře se, jak je znázorněno na následujícím obrázku.  

     ![Skupiny kontejnerů](../ide/media/express_toolbox.png "Express_Toolbox")  
Skupiny kontejnerů  

3.  Ovládací prvky jako tlačítka, zaškrtněte políčka a popisky můžete přidat do svého formuláře. Dvakrát klikněte `TableLayoutPanel` ovládací prvek panelu nástrojů. (Nebo, můžete přetáhnout ovládací prvek z panelu nástrojů na formuláři). Pokud to uděláte, rozhraní IDE přidá `TableLayoutPanel` řízení do svého formuláře, jak je znázorněno na následujícím obrázku.  

     ![TableLayoutPanel – ovládací prvek](../ide/media/express_formtablelayout.png "Express_FormTableLayout")  
TableLayoutPanel – ovládací prvek  

    > [!NOTE]
    >  Po přidání TableLayoutPanel, pokud se zobrazí okno uvnitř formuláře s nadpis **TableLayoutPanel úlohy**, zvolte kamkoli do formuláře a tím ho zavřete. Později v tomto kurzu se dozvíte další informace o toto okno.  

     Všimněte si, jak panel nástrojů rozšíří na pokrytí formuláře, když zvolíte jeho kartě a zavře po volbě kamkoli mimo. To je funkce automatického skrytí IDE. Můžete tuto možnost zapnout nebo vypnout pro některý z windows tak, že zvolíte ikonu připínáčku v pravém horním rohu okna přepnout automaticky skrýt a zamknutí na místě. Takto se zobrazí ikona připínáčku.  

     ![Ikonu připínáčku](../ide/media/express_pushpintoolbox.png "Express_PushpinToolbox")  
Ikona Připínáček  

4.  Ujistěte se, **TableLayoutPanel** je vybrána ji výběrem. Můžete ověřit, jaké ovládací prvek vybrán pohledem na rozevírací seznam v horní části **vlastnosti** okno, jak je znázorněno na následujícím obrázku.  

     ![Vlastnosti – okno zobrazující TableLayoutPanel – ovládací prvek](../ide/media/express_controlspropwin.png "Express_ControlsPropWin")  
Okno Vlastnosti zobrazující TableLayoutPanel – ovládací prvek  

5.  Vyberte **podle abecedy** tlačítka na panelu nástrojů v **vlastnosti** okno. To způsobí, že seznam vlastností ve **vlastnosti** okna zobrazte v abecedním pořadí, které se snadněji najít vlastnosti v tomto kurzu.  

6.  Selektor ovládacího prvku je rozevírací seznam v horní části **vlastnosti** okno. V tomto příkladu se zobrazí, že ovládací prvek označuje `tableLayoutPanel1` je vybrána. Ovládací prvky můžete vybrat tak, že zvolíte oblast v Návrháři formulářů nebo tak, že zvolíte Selektor ovládacího prvku. Teď, když `TableLayoutPanel` je vybrána, Najít **ukotvení** vlastnost a zvolte **ukotvení**, který by měl být nastaven na **žádné**. Všimněte si, že se zobrazí šipku rozevíracího seznamu vedle hodnota. Vyberte šipku a pak vyberte **vyplnění** (tlačítko velké uprostřed), jak je znázorněno na následujícím obrázku.  

     ![Vlastnosti – okno s výplně vybrané](../ide/media/express_docktable.png "Express_DockTable")  
Vlastnosti – okno s výplně vybrané  

     *Ukotvení* v sadě Visual Studio odkazuje po připojení k jiné okno nebo oblast v prostředí IDE časového období. Například okno Vlastnosti může být ukotven – to znamená, odpojit a volně umístěný v sadě Visual Studio – nebo může být ukotveno proti **Průzkumníku řešení**.  

7.  Po nastavení kontejneru TableLayoutPanel **ukotvení** vlastnost **vyplnění**, panelu doplní k celému formuláři. Pokud změníte velikost formuláře znovu, kontejner TableLayoutPanel zůstane ukotvený a změní, aby se vešel do.  

    > [!NOTE]
    >  Ovládacího prvku TableLayoutPanel funguje jako tabulku aplikace Microsoft Office Word: má řádků a sloupců a jednotlivých buněk může mít rozsah více řádků a sloupců. Každá buňka může obsahovat jeden ovládací prvek (např. tlačítka, představuje zaškrtávací políčko nebo štítek). Bude mít vaše TableLayoutPanel `PictureBox` řízení rozložení celý horní řádek, `CheckBox` ovládacího prvku v jeho levé dolní buňky a čtyřmi `Button` ovládacích prvků v pravém dolním buňky.  

8.  V současné době kontejner TableLayoutPanel má dva rovná velikosti řádků a sloupců dva stejně velké. Budete muset změnit jejich velikost, takže horním řádku a v pravém sloupci jsou oba mnohem větší. V Návrháři formulářů Windows vyberte kontejner TableLayoutPanel. V pravém horním rohu je malý černý trojúhelník tlačítko, které se zobrazí takto.  

     ![Tlačítko trojúhelníček](../ide/media/express_iconblacktriangle.gif "Express_IconBlackTriangle")  
Tlačítko trojúhelníček  

     Toto tlačítko znamená, že má ovládací prvek úlohy, které vám pomohou automaticky nastavit jeho vlastnosti.  

9. Zvolte trojúhelníček k zobrazení seznamu úloh ovládacího prvku, jak je znázorněno na následujícím obrázku.  

     ![TableLayoutPanel – úlohy](../ide/media/express_tablepanel.png "Express_TablePanel")  
TableLayoutPanel – úlohy  

10. Vyberte **úpravy řádků a sloupců** úlohy zobrazíte **styly řádku a sloupce** okno. Zvolte **Column1**a změňte jeho velikost na 15 procent tím, že je, že **procent** tlačítko je vybrané a vstup `15` v **procent** pole. (To je `NumericUpDown` řízení, které budete používat v pozdějších kurzech.) Zvolte **Column2** a nastavte ji na 85 procent. Nevolte **OK** tlačítko ještě, protože okno se zavře. (Ale pokud tak učiníte, můžete ho znovu otevřít pomocí seznamu úkolů.)  

     ![TableLayoutPanel – styly řádků a sloupců](../ide/media/vs_tablelayoutpanel_setup.png "VS_TableLayoutPanel_Setup")  
TableLayoutPanel – styly řádků a sloupců  

11. Z **zobrazit** rozevírací seznam v horní části okna vyberte **řádky**. Nastavit **Row1** až 90 procent a **Row2** až 10 procent.  

12. Vyberte **OK** tlačítko. Vaše TableLayoutPanel teď měli mít velký horní řádek, malý dolní řádek, malé levém sloupci a velké pravém sloupci. Můžete změnit velikost řádků a sloupců v kontejneru TableLayoutPanel výběr tableLayoutPanel1 ve formuláři a přetažením jeho ohraničení řádků a sloupců.  

     ![Form1 se změněnou velikostí TableLayoutPanel](../ide/media/vs_formafterlayoutpanel.png "VS_FormAfterLayoutPanel")  
Form1 se změněnou velikostí TableLayoutPanel  

### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat  

-   Chcete-li přejít k dalšímu kroku kurzu, přečtěte si téma [krok 5: Přidání ovládacích prvků na vaše formulář](../ide/step-5-add-controls-to-your-form.md).  

-   Chcete-li vrátit k předchozímu kroku kurzu, přečtěte si téma [krok 3: Nastavte si vlastnosti formuláře](../ide/step-3-set-your-form-properties.md).
