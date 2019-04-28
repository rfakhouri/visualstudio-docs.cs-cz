---
title: 'Krok 5: Přidejte do svého formuláře ovládací prvky'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: dc2746f4-0b5c-4674-9ef7-f40f94150f52
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4f1662f484d8738c381f704732389537b0ac3ad5
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63431481"
---
# <a name="step-5-add-controls-to-your-form"></a>Krok 5: Přidejte do svého formuláře ovládací prvky
V tomto kroku přidáte ovládací prvky, například <xref:System.Windows.Forms.PictureBox> ovládacího prvku a <xref:System.Windows.Forms.CheckBox> ovládací prvek do formuláře. Potom přidáte <xref:System.Windows.Forms.Button> ovládací prvky do formuláře.

 ![odkaz na video](../data-tools/media/playvideo.gif)video verzi tohoto tématu naleznete v tématu [kurz 1: Vytvoření prohlížeče obrázků v jazyce Visual Basic - Video 2](http://go.microsoft.com/fwlink/?LinkId=205211) nebo [kurz 1: Vytvoření prohlížeče obrázků v C# -2 videa](http://go.microsoft.com/fwlink/?LinkId=205200). Tato videa používají starší verzi sady Visual Studio, takže existují mírné rozdíly v některých příkazech nabídek a jiných prvcích uživatelského rozhraní. Nicméně koncepty a postupy fungují podobně jako v aktuální verzi sady Visual Studio.

## <a name="to-add-controls-to-your-form"></a>Chcete-li přidat ovládací prvky do formuláře

1. Přejděte na **nástrojů** karty (umístěné na levé straně rozhraní IDE sady Visual Studio) a rozbalte **běžné ovládací prvky** skupiny. Zobrazí nejběžnější ovládací prvky, které vidíte ve formulářích.

2. Zvolte **TableLayoutPanel** ovládací prvek na formuláři. Pokud chcete ověřit, že je vybrán kontejner TableLayoutPanel, ujistěte se, že jeho název zobrazuje v rozevíracím seznamu v horní části **vlastnosti** okna. Můžete také vybrat ovládací prvky formuláře pomocí rozevíracího seznamu v horní části **vlastnosti** okna. Výběr ovládacího prvku tímto způsobem může často být jednodušší než volba prvku tiny pomocí myši.

3. Dvakrát klikněte **PictureBox** položky pro přidání ovládacího prvku PictureBox do formuláře. Protože kontejner TableLayoutPanel je ukotven k vyplnění formuláře, rozhraní IDE přidá ovládací prvek PictureBox do první prázdné buňky (levý horní roh).

4. Zvolte nový **PictureBox** ovládací prvek a vyberte ji a pak zvolte na černý trojúhelník na novém ovládacím prvku PictureBox k zobrazení jeho seznamu úloh, jak je znázorněno na následujícím obrázku.

     ![Úlohy třídy PictureBox](../ide/media/express_pictureboxtasks.png)
**PictureBox** úlohy

    > [!NOTE]
    > Pokud omylem přidáte nesprávný typ ovládacího prvku do vašeho kontejneru TableLayoutPanel, můžete ho odstranit. Klikněte pravým tlačítkem na ovládací prvek a klikněte na tlačítko **odstranit** v kontextové nabídce. Můžete také odebrat ovládací prvky z formuláře pomocí panelu nabídek. V panelu nabídky zvolte **upravit** > **zpět**, nebo **upravit** > **odstranit**.

5. Zvolte **ukotvit v nadřazeném kontejneru** odkaz. Tím se automaticky nastaví ovládací prvek PictureBox **Dock** vlastnost **vyplnit**. Tento údaj zobrazíte, zvolte **PictureBox** vyberte ovládací prvek, přejděte na **vlastnosti** okna, a ujistěte se, že **Dock** je nastavena na **vyplnit**.

6. Nechejte PictureBox roztáhnout oba sloupce změnou jeho **ColumnSpan** vlastnost. Zvolte **PictureBox** ovládací prvek a nastavit jeho **ColumnSpan** vlastnost **2**. Také když je PictureBox prázdný, budete chtít zobrazit prázdný rámeček. Nastavte jeho **BorderStyle** vlastnost **Fixed3D**.

    > [!NOTE]
    > Pokud se nezobrazí **ColumnSpan** vlastnost pro váš ovládací prvek PictureBox, pak je pravděpodobné, že ovládací prvek PictureBox byl přidán do formuláře, nikoli do TableLayoutPanel. Problém odstranit, zvolte **PictureBox**, odstraňte ji, zvolte **TableLayoutPanel**, a pak přidejte nový prvek PictureBox.

7. Zvolte **TableLayoutPanel** ve formuláři a potom přidejte ovládací prvek CheckBox do formuláře. Dvakrát klikněte **zaškrtávací políčko** položky v **nástrojů** přidat nový ovládací prvek CheckBox do další volné buňky v tabulce. Protože PictureBox zabírá v kontejneru TableLayoutPanel první dvě buňky, ovládací prvek CheckBox je přidán do levé dolní buňky. Zvolte **Text** vlastnost a zadejte hledané klíčové slovo **Stretch**, jak je znázorněno na následujícím obrázku.

     ![TextBox – ovládací prvek s vlastností Stretch](../ide/media/express_pictureviewercheckbox.png)
**TextBox** ovládacím prvkem **Stretch** vlastnost

8. Zvolte **TableLayoutPanel** na formuláři a potom přejděte na **kontejnery** ve **nástrojů** (kde jste získali váš ovládací prvek) a dvakrát klikněte na panel **FlowLayoutPanel** položka k přidání nového ovládacího prvku do poslední buňky v ovládacím prvku PictureBox (vpravo dole). Potom ukotvěte FlowLayoutPanel v TableLayoutPanel (výběrem **ukotvit v nadřazeném kontejneru** v seznamu úloh černého trojúhelníku panelu FlowLayoutPanel nebo nastavením panelu FlowLayoutPanel **ukotvit** Vlastnost **vyplnit**).

    > [!NOTE]
    > A <xref:System.Windows.Forms.FlowLayoutPanel> je kontejner, který uspořádá jiné ovládací prvky do úhledných řádků v pořadí. Když změníte velikost FlowLayoutPanel, pokud má místo k rozložení všech ovládacích prvků v jediném řádku, udělá to. V opačném případě je uspořádá na řádcích, jednoho nad druhým. Použijete FlowLayoutPanel k podržení čtyř tlačítek. Pokud jsou tlačítka uspořádány, jeden v druhém při přidání, ujistěte se, že je vybraná FlowLayoutPanel před přidáním tlačítek. I když bylo uvedeno dříve, že každá buňka může obsahovat pouze jeden ovládací prvek, pravém dolním rohu buňky kontejneru TableLayoutPanel má čtyři ovládací prvky tlačítka. Je to proto, že do buňky obsahující další ovládací prvky můžete umístit ovládací prvek. Tento druh ovládacího prvku se nazývá kontejner a FlowLayoutPanel je kontejner.

## <a name="to-add-buttons"></a>Přidat tlačítka

1. Vyberte nový FlowLayoutPanel, který jste přidali. Přejděte na **běžné ovládací prvky** v **nástrojů** a dvakrát klikněte **tlačítko** položky pro přidání ovládacího tlačítka nazvaného **button1** k vaší FlowLayoutPanel. Opakujte k přidání dalšího tlačítka. Rozhraní IDE zjistí, že je již tlačítko nazvané **button1** a další nazve **button2**.

2. Obvykle přidáte další tlačítka pomocí **nástrojů**. Tentokrát vyberte možnost **button2**a pak na panelu nabídek zvolte **upravit** > **kopírování** (nebo stiskněte klávesu **Ctrl** + **C**). V panelu nabídky zvolte **upravit** > **vložte** (nebo stiskněte klávesu **Ctrl**+**V**) k vložení kopie vašeho tlačítka. Nyní jej vložte znovu. IDE nyní přidalo **button3** a **button4** do FlowLayoutPanel.

    > [!NOTE]
    > Můžete zkopírovat a vložit libovolný ovládací prvek. Rozhraní IDE pojmenuje a umístí nové ovládací prvky logickým způsobem. Pokud vložíte ovládací prvek do kontejneru, rozhraní IDE zvolí další logický prostor pro umístění.

3. Vyberte první tlačítko a nastavte jeho **Text** vlastnost **zobrazit obrázek**. Nastavte **Text** vlastnosti dalších tří tlačítek na **Vymazat obrázek**, **nastavit barvu pozadí**, a **Zavřít**.

4. Dalším krokem je změnit velikost tlačítek a uspořádat je tak, aby jejich zarovnání bylo k pravé straně panelu. Zvolte **FlowLayoutPanel** a podívejte se na jeho **FlowDirection** vlastnost. Změňte ji tak, že je nastavena na **RightToLeft**. Jakmile provedete, tlačítka by měl vlastní vyrovnání v rámci na pravou stranu buňky a jejich pořadí se obrátit tak, aby **zobrazit obrázek** je tlačítko na pravé straně.

    > [!NOTE]
    > Pokud jsou tlačítka stále v nesprávném pořadí, můžete přetáhnout tlačítka kolem kontejneru FlowLayoutPanel k změně jejich uspořádání v libovolném pořadí. Můžete zvolit tlačítko a přetáhnout je doleva nebo doprava.

5. Zvolte **Zavřít** tlačítko a vyberte ji. Podržte stisknutou klávesu **Ctrl** klíče a vyberte další tři tlačítka tak, aby byly všechny vybrány. Zatímco jsou všechna tlačítka vybrána, přejděte **vlastnosti** okno a posouvejte nahoru až **AutoSize** vlastnost. Tato vlastnost říká tlačítku, že automaticky změní velikost sebe sama na vhodnou všechen text. Nastavte ho na **true**. Tlačítka by měla být nyní správně velká a být ve správném pořadí. (Dokud jsou vybrány všechna čtyři tlačítka, můžete změnit všechny čtyři **AutoSize** vlastnosti ve stejnou dobu.) Následující obrázek znázorňuje čtyři tlačítka.

     ![Prohlížeč obrázků se čtyřmi tlačítky](../ide/media/express_autosize.png)
**prohlížeče obrázků** se čtyřmi tlačítky

6. Nyní spusťte váš program znovu, abyste viděli váš nově rozložený formulář. Volba tlačítek a zaškrtávacího políčka ještě nic neumí, ale bude brzy fungovat.

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

- Přechod k dalšímu kroku výukového programu naleznete v tématu [krok 6: Pojmenovat vaše tlačítka](../ide/step-6-name-your-button-controls.md).

- Chcete-li vrátit k předchozímu kroku tutoriálu, přečtěte si téma [krok 4: Rozvrhněte svůj formulář pomocí ovládacího prvku TableLayoutPanel](../ide/step-4-lay-out-your-form-with-a-tablelayoutpanel-control.md).
