---
title: 'Krok 5: Přidání ovládacích prvků do formuláře'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: dc2746f4-0b5c-4674-9ef7-f40f94150f52
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e69c75b00ddb98148e9985820e577031ead0a275
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68918820"
---
# <a name="step-5-add-controls-to-your-form"></a>Krok 5: Přidání ovládacích prvků do formuláře
V tomto kroku přidáte ovládací prvky, například <xref:System.Windows.Forms.PictureBox> ovládací prvek <xref:System.Windows.Forms.CheckBox> a ovládací prvek, do formuláře. Pak přidáte <xref:System.Windows.Forms.Button> ovládací prvky do formuláře.

![odkaz na video](../data-tools/media/playvideo.gif)ve verzi videa tohoto tématu najdete v [kurzu 1: Vytvoření prohlížeče obrázků ve Visual Basic – video 2](http://go.microsoft.com/fwlink/?LinkId=205211) nebo [kurz 1: Vytvoření prohlížeče obrázků ve C# videu 2.](http://go.microsoft.com/fwlink/?LinkId=205200) Tato videa používají starší verzi sady Visual Studio, takže existují mírné rozdíly v některých příkazech nabídky a dalších prvcích uživatelského rozhraní. Koncepty a postupy však fungují podobně v aktuální verzi sady Visual Studio.

## <a name="to-add-controls-to-your-form"></a>Přidání ovládacích prvků do formuláře

1. Přejít na kartu **panel nástrojů** (umístěný na levé straně integrovaného vývojového prostředí sady Visual Studio) a rozbalte skupinu **běžné ovládací prvky** . Tím se zobrazí nejběžnější ovládací prvky, které vidíte ve formulářích.

2. Vyberte ovládací prvek **TableLayoutPanel** ve formuláři. Chcete-li ověřit, zda je kontejner TableLayoutPanel vybrán, ujistěte se, že se jeho název zobrazuje v rozevíracím seznamu v horní části okna **vlastnosti** . Pomocí rozevíracího seznamu v horní části okna **vlastnosti** můžete také zvolit ovládací prvky formuláře. Výběr ovládacího prvku tímto způsobem může být často snazší než volba nemalého ovládacího prvku pomocí myši.

3. Dvojím kliknutím na položku **PictureBox** přidáte ovládací prvek PictureBox do formuláře. Vzhledem k tomu, že kontejner TableLayoutPanel je ukotven pro vyplnění formuláře, rozhraní IDE přidá ovládací prvek PictureBox do první prázdné buňky (levý horní roh).

4. Zvolte nový ovládací prvek **PictureBox** , který chcete vybrat, a pak zvolte černý trojúhelník na novém ovládacím prvku PictureBox pro zobrazení seznamu úkolů, jak je znázorněno na následujícím obrázku.

     ![Úlohy PictureBox](../ide/media/express_pictureboxtasks.png)<br/>***PictureBox – ovládací prvek*** *úkoly*

    > [!NOTE]
    > Pokud omylem přidáte nesprávný typ ovládacího prvku do kontejneru TableLayoutPanel, můžete jej odstranit. Klikněte na ovládací prvek pravým tlačítkem myši a potom v místní nabídce vyberte možnost **Odstranit** . Ovládací prvky můžete odebrat také z formuláře pomocí panelu nabídek. Na panelu nabídek vyberte možnost **Upravit** > **zpět**nebo **Upravit** > **Odstranit**.

5. Vyberte odkaz **Dock v nadřazeném kontejneru** . Tím se automaticky nastaví vlastnost PictureBox **Dock** na **Fill**. Chcete-li se podívat, zvolte ovládací prvek **PictureBox** , který chcete vybrat, přejděte do okna **vlastnosti** a ujistěte se, že vlastnost **Dock** je nastavena na hodnotu **Fill**.

6. Nastavte, aby PictureBox rozspan oba sloupce změnou jeho vlastnosti **jeho ColumnSpan** . Vyberte ovládací prvek **PictureBox** a nastavte jeho vlastnost **jeho ColumnSpan** na hodnotu **2**. Také, pokud je PictureBox prázdné, chcete zobrazit prázdný rámeček. Nastavte jeho vlastnost **BorderStyle** na **Fixed3D**.

    > [!NOTE]
    > Pokud nevidíte vlastnost **jeho ColumnSpan** ovládacího prvku PictureBox, je možné, že byl ovládací prvek PictureBox přidán do formuláře namísto kontejneru TableLayoutPanel. Chcete-li tento problém opravit, zvolte **PictureBox**, odstraňte jej, zvolte **kontejner TableLayoutPanel**a pak přidejte nový PictureBox.

7. Zvolte **kontejner TableLayoutPanel** ve formuláři a poté přidejte ovládací prvek CheckBox do formuláře. Dvojitým kliknutím na položku **CheckBox** v **sadě nástrojů** přidáte nový ovládací prvek CheckBox do další volné buňky v tabulce. Vzhledem k tomu, že PictureBox zabírá první dvě buňky v kontejneru TableLayoutPanel, ovládací prvek CheckBox se přidá do levé dolní buňky. Vyberte vlastnost **text** a zadejte slovo Roztáhnout,jak je znázorněno na následujícím obrázku.

     ![Ovládací prvek TextBox s vlastností Stretch](../ide/media/express_pictureviewercheckbox.png)<br/>***Textové pole*** *řízení s* ***Roztáhnout*** *vlastnost*

8. Zvolte **kontejner TableLayoutPanel** ve formuláři a potom přejděte do skupiny **kontejnery** v sadě **nástrojů** (kde jste získali svůj ovládací prvek TableLayoutPanel) a dvakrát klikněte na položku **FlowLayoutPanel** a přidejte nový ovládací prvek do poslední buňky v PictureBox (vpravo dole). Poté ukotvěte FlowLayoutPanel v kontejneru TableLayoutPanel (buď výběrem možnosti **Dock v nadřazeném kontejneru** v seznamu úkolů černého trojúhelníku FlowLayoutPanel, nebo nastavením vlastnosti **Dock** prvku FlowLayoutPanel na **vyplnit**).

    > [!NOTE]
    > A <xref:System.Windows.Forms.FlowLayoutPanel> je kontejner, který uspořádá další ovládací prvky v úhledných řádcích v daném pořadí. Když změníte velikost kontejneru FlowLayoutPanel, pokud má místo pro rozložení všech ovládacích prvků na jednom řádku, provede to. V opačném případě je uspořádá na řádcích, jeden nad druhou. K uložení čtyř tlačítek použijete FlowLayoutPanel. Pokud jsou tlačítka při přidání uspořádána po sobě, před přidáním tlačítek se ujistěte, že je vybráno FlowLayoutPanel. Ačkoliv bylo uvedeno dříve, že každá buňka může obsahovat pouze jeden ovládací prvek, pravá dolní buňka kontejneru TableLayoutPanel má čtyři ovládací prvky tlačítka. Důvodem je to, že ovládací prvek lze umístit do buňky, která obsahuje jiné ovládací prvky. Tento druh ovládacího prvku se nazývá kontejner a FlowLayoutPanel je kontejner.

## <a name="to-add-buttons"></a>Přidání tlačítek

1. Vyberte nový FlowLayoutPanel, který jste přidali. Přejděte na **běžné ovládací prvky** v **sadě nástrojů** a dvojitým kliknutím na položku **tlačítka** přidejte ovládací prvek tlačítko s názvem **Button1** do kontejneru FlowLayoutPanel. Opakováním přidejte další tlačítko. Rozhraní IDE zjistí, že již existuje tlačítko s názvem **Button1** a volá další **Button2**.

2. Obvykle přidáte další tlačítka pomocí **sady nástrojů**. Tentokrát zvolte možnost **Button2**a potom v řádku nabídek zvolte možnost **Upravit** > **kopii** (nebo stiskněte klávesu **CTRL**+**C**). Na panelu nabídek zvolte možnost **Upravit** > **vložení** (nebo stiskněte klávesu **CTRL**+**V**) a vložte kopii tlačítka. Nyní jej vložte znovu. Integrované vývojové prostředí (IDE) teď přidalo **Button3** a **Button4** do kontejneru FlowLayoutPanel.

    > [!NOTE]
    > Můžete zkopírovat a vložit libovolný ovládací prvek. Rozhraní IDE názvy a umístí nové ovládací prvky logickým způsobem. Pokud ovládací prvek vložíte do kontejneru, rozhraní IDE zvolí další logický prostor pro umístění.

3. Vyberte první tlačítko a nastavte jeho vlastnost **text** tak, aby **zobrazovala obrázek**. Potom nastavte vlastnosti **textu** dalších tří tlačítek pro **vymazání obrázku**, **Nastavení barvy pozadí**a **zavření**.

4. Dalším krokem je změnit velikost tlačítek a uspořádat je tak, aby se zarovnaly na pravé straně panelu. Vyberte **FlowLayoutPanel** a podívejte se na jeho vlastnost **FlowDirection** . Změňte ji tak, aby byla nastavená na **RightToLeft**. Jakmile to uděláte, tlačítka by se měla zarovnat do pravé strany buňky a obrátit jejich pořadí tak, aby tlačítko **Zobrazit obrázek** bylo na pravé straně.

    > [!NOTE]
    > Pokud jsou tlačítka stále v nesprávném pořadí, můžete přetáhnout tlačítka kolem FlowLayoutPanel a změnit jejich uspořádání v libovolném pořadí. Můžete zvolit tlačítko a přetáhnout ho doleva nebo doprava.

5. Kliknutím na tlačítko **Zavřít** jej vyberte. Podržte stisknutou klávesu **CTRL** a vyberte další tři tlačítka, aby byly všechny vybrány. Když jsou vybrána všechna tlačítka, přejděte do okna **vlastnosti** a posuňte se k vlastnosti **AutoSize** . Tato vlastnost oznamuje tlačítku, aby se automaticky změnila velikost tak, aby odpovídala veškerému jeho textu. Nastavte na **hodnotu true**. Tlačítka by měla být teď správně velikostná a musí být ve správném pořadí. (Pokud jsou vybrána všechna čtyři tlačítka, můžete změnit všechny čtyři vlastnosti **AutoSize** současně.) Následující obrázek znázorňuje čtyři tlačítka.

     ![Prohlížeč obrázků se čtyřmi tlačítky](../ide/media/express_autosize.png)<br/>***Prohlížeč obrázků*** *se čtyřmi tlačítky*

6. Nyní spusťte program znovu, aby se zobrazila vaše nově rozložená forma. Výběr tlačítek a zaškrtávací políčko ještě nic nedělá, ale bude brzy fungovat.

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

- Pokud chcete přejít na další krok kurzu, přečtěte si [krok 6: Pojmenujte své](../ide/step-6-name-your-button-controls.md)ovládací prvky tlačítek.

- Pokud se chcete vrátit k předchozímu kroku kurzu [, přečtěte si krok 4: Rozložte formulář pomocí ovládacího prvku](../ide/step-4-lay-out-your-form-with-a-tablelayoutpanel-control.md)TableLayoutPanel.
