---
title: 'Krok 6: Pojmenujte své ovládací prvky tlačítek'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 56b3baa3-651e-4ad4-8942-e334c5c57158
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0920a624f726aa4fd6f44d0181be75a45e0b7b92
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60070638"
---
# <a name="step-6-name-your-button-controls"></a>Krok 6: Pojmenujte své ovládací prvky tlačítek
Existuje pouze jeden <xref:System.Windows.Forms.PictureBox> na formuláři. Při přidávání jej rozhraní IDE automaticky pojmenuje **pictureBox1**. Existuje pouze jeden <xref:System.Windows.Forms.CheckBox>, který se nazývá **checkBox1**. Brzy napíšete kód a tento kód bude odkazovat na ovládací prvek CheckBox a PictureBox. Protože se nachází pouze jednu roli od každého z těchto ovládacích prvků, budete vědět, co znamenají, až se zobrazí **pictureBox1** nebo **checkBox1** ve vašem kódu.

> [!NOTE]
>  V jazyce Visual Basic je výchozí první písmeno ovládacího prvku je počáteční velkým písmenem, takže názvy jsou **PictureBox1**, **CheckBox1**, a tak dále.

 Existují čtyři tlačítka na formuláři a rozhraní IDE je pojmenovalo **button1**, **button2**, **button3**, a **button4**. Jen pohlédnutím na jejich názvy nevíte, které tlačítko je **Zavřít** tlačítko a který je **zobrazit obrázek** tlačítko. To je důvod, proč poskytuje své ovládací prvky tlačítek informativnějších názvů je užitečné.

 ![odkaz na video](../data-tools/media/playvideo.gif)video verzi tohoto tématu naleznete v tématu [kurz 1: Vytvoření prohlížeče obrázků v jazyce Visual Basic - Video 3](http://go.microsoft.com/fwlink/?LinkId=205213) nebo [kurz 1: Vytvoření prohlížeče obrázků v C# – Video 3](http://go.microsoft.com/fwlink/?LinkId=205202). Tato videa používají starší verzi sady Visual Studio, takže existují mírné rozdíly v některých příkazech nabídek a jiných prvcích uživatelského rozhraní. Nicméně koncepty a postupy fungují podobně jako v aktuální verzi sady Visual Studio.

## <a name="to-name-your-button-controls"></a>Pojmenujte své ovládací prvky tlačítek

1. Ve formuláři, zvolte **Zavřít** tlačítko. (Pokud stále máte všechna tlačítka vybrána, vyberte **Esc** klíč zrušení výběru.) Posouvejte **vlastnosti** okna, dokud se nezobrazí **(název)** vlastnost. ( **(Název)** vlastnost je blízko horní, pokud jsou vlastnosti v abecedním pořadí.) Změňte název na **closeButton**, jak je znázorněno na následujícím obrázku.

     ![Okno Vlastnosti s názvem closeButton](../ide/media/express_setnameproperty.png)
**vlastnosti** okno s **closeButton** název

    > [!NOTE]
    >  Pokud se pokusíte změnit název tlačítka na **closeButton**, s mezerou mezi slovy, zavřít a tlačítko, rozhraní IDE zobrazí chybovou zprávu: "Hodnota vlastnosti není platná." Mezery (a několik jiných znaků) nejsou povoleny v názvech ovládacích prvků.

2. Přejmenujte další tři tlačítka na **backgroundButton**, **tlacitkoVymazat**, a **showButton**. Názvy můžete ověřit výběrem ovládacího prvku selektoru rozevíracího seznamu v **vlastnosti** okna. Nové názvy tlačítek se zobrazí.

3. Dvakrát klikněte **zobrazit obrázek** tlačítko na formuláři. Jako alternativu zvolte **zobrazit obrázek** tlačítko na formuláři a klikněte na tlačítko **Enter** klíč. Když použijete, rozhraní IDE otevře další kartu v hlavním okně volá **Form1.cs** (**Form1.vb** Pokud používáte jazyk Visual Basic). Tato karta zobrazuje soubor kódu za formulářem, jak je znázorněno na následujícím obrázku.

     ![Karta Form1.cs s Visual C&#35; kód](../ide/media/express_showbuttoncode.png)
**Form1.cs** kartu s Vizuálem C# kódu

4. Zaměřte se na tuto část kódu. (Zvolte **VB** kartě níže, pokud používáte jazyk Visual Basic k zobrazení verze kódu jazyka Visual Basic.)

     [!code-vb[VbExpressTutorial1Step6#1](../ide/codesnippet/VisualBasic/step-6-name-your-button-controls_1.vb)]
     [!code-csharp[VbExpressTutorial1Step6#1](../ide/codesnippet/CSharp/step-6-name-your-button-controls_1.cs)]

     Díváte se na kód nazvaný `showButton_Click()`. Rozhraní IDE toto přidal do kódu formuláře při otevření souboru kódu **showButton** tlačítko. V době návrhu když otevřete soubor kódu pro ovládací prvek ve formuláři, kód je generován pro ovládací prvek Pokud ještě neexistuje. Tento kód se označuje jako *metoda*, spustí při spuštění programu a zvolte ovládacího prvku – v takovém případě **zobrazit obrázek** tlačítko.

    > [!NOTE]
    >  V tomto kurzu kódu jazyka Visual Basic, který je automaticky generován byl zjednodušen odebráním všeho mezi závorkami, `()`. Pokaždé, když se v takovém případě můžete odebrat stejný kód. Váš program bude fungovat v obou případech. Pro zbývající část kurzů je všechen automaticky generovaný kód zjednodušen, kdykoli je to možné.

5. Zvolte **Návrháře formulářů Windows** kartu znovu (**Form1.cs [Design]** ve Vizuálu C#, **Form1.vb [Design]** v jazyce Visual Basic) a pak otevřete soubor kódu  **Vymazat obrázek** tlačítko pro vytvoření metody pro něj v kódu formuláře. Tento postup opakujte pro zbývající dvě tlačítka. Pokaždé, když, rozhraní IDE přidá novou metodu do souboru kódu formuláře.

6. Pokud chcete přidat další metodu, otevřete soubor kódu pro **zaškrtávací políčko** v ovládacím prvku **Návrháře formulářů Windows** , takže rozhraní IDE přidat `checkBox1_CheckedChanged()` metoda. Tato metoda je volána pokaždé, když uživatel vybere nebo zruší zaškrtávací políčko.

    > [!NOTE]
    >  Při práci na programu se často přesouváte mezi editoru kódu a **Návrháře formulářů Windows**. Rozhraní IDE usnadňuje navigaci v projektu. Použití **Průzkumníka řešení** otevřete **Návrháře formulářů Windows** dvojitým kliknutím *Form1.cs* ve Vizuálu C# nebo *Form1.vb* v V jazyce Visual Basic nebo na panelu nabídek zvolte položky **zobrazení** > **návrháře**.

     Následující znázorňuje nový kód, na který se zobrazí v editoru kódu.

     [!code-vb[VbExpressTutorial1Step6#2](../ide/codesnippet/VisualBasic/step-6-name-your-button-controls_2.vb)]
     [!code-csharp[VbExpressTutorial1Step6#2](../ide/codesnippet/CSharp/step-6-name-your-button-controls_2.cs)]

     Pět metod, které jste přidali, se nazývají *obslužné rutiny událostí*, protože je program volá vždy, když se stane, událost (podobně jako uživatel vybírá tlačítko nebo pole).

     Při zobrazení kódu pro ovládací prvek v integrovaném vývojovém prostředí v době návrhu, Visual Studio přidá metodu obslužné rutiny události pro ovládací prvek, pokud není k dispozici. Například když dvakrát kliknete na tlačítko, rozhraní IDE přidá obslužnou rutinu události pro jeho <xref:System.Windows.Forms.Control.Click> událost (která je volána pokaždé, když uživatel vybere tlačítko). Když dvakrát kliknete na zaškrtávací políčko, rozhraní IDE přidá obslužnou rutinu události pro jeho <xref:System.Windows.Forms.CheckBox.CheckedChanged> událost (která je volána pokaždé, když uživatel vybere nebo zruší pole).

     Po přidání obslužné rutiny události pro ovládací prvek, můžete k němu můžete vrátit kdykoli z **Návrháře formulářů Windows** poklepání ovládací prvek, nebo v řádku nabídek, výběrem **zobrazení**  >  **Kód**.

     Názvy jsou důležité při vytváření programů a metody (včetně obslužné rutiny události) mohou mít libovolný název, který chcete. Při přidání obslužné rutiny události pomocí rozhraní IDE vytvoří název založený na názvu ovládacího prvku a události zpracovávanou na. Například událost Click pro tlačítko s názvem **showButton** je volána `showButton_Click()` metoda obslužné rutiny události. Také otevírací a zavírací závorky `()` jsou obvykle přidány po názvu metody k označení, že metody byly diskutovány. Pokud se rozhodnete, kterou chcete změnit název proměnné kódu, klikněte pravým tlačítkem myši proměnnou kódu a klikněte na tlačítko **Refaktorovat** > **přejmenovat**. Všechny výskyty této proměnné v kódu budou přejmenovány. Zobrazit [refaktoring pro přejmenování](../ide/reference/rename.md) Další informace.

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

- Přechod k dalšímu kroku výukového programu naleznete v tématu [krok 7: Přidejte do svého formuláře komponenty dialogových oken](../ide/step-7-add-dialog-components-to-your-form.md).

- Chcete-li vrátit k předchozímu kroku tutoriálu, přečtěte si téma [krok 5: Přidejte do svého formuláře ovládací prvky](../ide/step-5-add-controls-to-your-form.md).
