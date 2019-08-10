---
title: 'Krok 6: Pojmenování tlačítkových ovládacích prvků'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- csharp
- vb
ms.assetid: 56b3baa3-651e-4ad4-8942-e334c5c57158
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 46ad996f7c3b1eeff4a3eb928442879f0b7275aa
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68925888"
---
# <a name="step-6-name-your-button-controls"></a>Krok 6: Pojmenování tlačítkových ovládacích prvků
Ve formuláři je pouze <xref:System.Windows.Forms.PictureBox> jeden. Po přidání se rozhraní IDE automaticky jmenuje **pictureBox1**. Existuje pouze jeden <xref:System.Windows.Forms.CheckBox>, který má název **checkBox1**. Brzy napíšete kód, který bude odkazovat na zaškrtávací políčko a PictureBox. Vzhledem k tomu, že existuje pouze jeden z těchto ovládacích prvků, budete znát, co to znamená, když ve svém kódu uvidíte **pictureBox1** nebo **checkBox1** .

> [!NOTE]
> V Visual Basic výchozí první písmeno libovolného názvu ovládacího prvku má počáteční zakončení, takže názvy jsou **pictureBox1**, **checkBox1**a tak dále.

Ve formuláři jsou čtyři tlačítka a rozhraní IDE s názvem **Button1**, **Button2**, **Button3**a **Button4**. Pouhým zobrazením jejich aktuálních názvů nevíte, které tlačítko představuje tlačítko **Zavřít** a který je jedním z tlačítek **Zobrazit obrázek** . To je důvod, proč vaše tlačítko ovládá více informativních názvů je užitečné.

![odkaz na video](../data-tools/media/playvideo.gif)ve verzi videa tohoto tématu najdete v [kurzu 1: Vytvoření prohlížeče obrázků v Visual Basic-Video 3](http://go.microsoft.com/fwlink/?LinkId=205213) nebo [kurz 1: Vytvoření prohlížeče obrázků ve C# formátu-Video 3](http://go.microsoft.com/fwlink/?LinkId=205202) Tato videa používají starší verzi sady Visual Studio, takže existují mírné rozdíly v některých příkazech nabídky a dalších prvcích uživatelského rozhraní. Koncepty a postupy však fungují podobně v aktuální verzi sady Visual Studio.

## <a name="to-name-your-button-controls"></a>Chcete-li pojmenovat ovládací prvky tlačítka

1. Ve formuláři klikněte na tlačítko **Zavřít** . (Pokud máte stále vybraná všechna tlačítka, kliknutím na klávesu **ESC** výběr zrušte.) Posuňte se v okně **vlastnosti** , dokud se nezobrazí vlastnost **(název)** . (Vlastnost **(Name)** je blízko horní části, pokud jsou vlastnosti seřazené abecedně.) Změňte název na **closeButton**, jak je znázorněno na následujícím obrázku.

     ![Okno Vlastnosti s oknem](../ide/media/express_setnameproperty.png)
**vlastností** názvu closeButton s názvem **closeButton**

    > [!NOTE]
    > Pokud se pokusíte změnit název tlačítka na **closeButton**s mezerou mezi slovy zavřít a tlačítko, rozhraní IDE zobrazí chybovou zprávu: Hodnota vlastnosti není platná. Mezery (a několik dalších znaků) nejsou povoleny v názvech ovládacích prvků.

2. Přejmenujte další tři tlačítka na **backgroundButton**, **clearButton**a **showButton**. Názvy můžete ověřit tak, že v okně **vlastnosti** zvolíte rozevírací seznam výběr ovládacího prvku. Nové názvy tlačítek se zobrazí.

3. Dvakrát klikněte na tlačítko **Zobrazit obrázek** ve formuláři. Jako alternativu zvolte tlačítko **Zobrazit obrázek** ve formuláři a pak zvolte klávesu **ENTER** . Když to uděláte, IDE otevře další kartu v hlavním okně s názvem **Form1.cs** (**Form1. vb** , pokud používáte Visual Basic). Tato karta zobrazuje soubor kódu za formulářem, jak je znázorněno na následujícím obrázku.

     ![Karta Form1.cs s Visual C&#35; Code](../ide/media/express_showbuttoncode.png)
**Form1.cs** karta s vizuálním C# kódem

4. Zaměřte se na tuto část kódu. (Pokud používáte Visual Basic k zobrazení Visual Basic verze kódu, klikněte na kartu **VB** .)

     [!code-vb[VbExpressTutorial1Step6#1](../ide/codesnippet/VisualBasic/step-6-name-your-button-controls_1.vb)]
     [!code-csharp[VbExpressTutorial1Step6#1](../ide/codesnippet/CSharp/step-6-name-your-button-controls_1.cs)]

     Díváte jste se na kód s `showButton_Click()`názvem. Rozhraní IDE bylo přidáno do kódu formuláře při otevření souboru kódu pro tlačítko **showButton** . V době návrhu při otevření souboru kódu pro ovládací prvek ve formuláři se kód vygeneruje pro ovládací prvek, pokud ještě neexistuje. Tento kód, který se označuje jako *Metoda*, se spouští při spuštění programu a výběru ovládacího prvku – v tomto případě se **zobrazí tlačítko Zobrazit obrázek** .

    > [!NOTE]
    > V tomto kurzu se kód Visual Basic, který se automaticky vygeneroval, zjednodušuje odebráním všeho mezi závorkami, `()`. Kdykoli k tomu dojde, můžete stejný kód odstranit. Program bude pracovat v obou případech. Ve zbývající části kurzů je jakýkoli automaticky generovaný kód zjednodušený, kdykoli je to možné.

5. Zvolte znovu kartu **Návrhář formulářů** (**Form1.cs [Design]** v jazyce Visual C#, **Form1. vb [Design]** v Visual Basic) a pak otevřete soubor kódu pro tlačítko **Vymazat obrázek** pro vytvoření metody v kódu formuláře. Tento postup opakujte pro zbývající dvě tlačítka. V každém okamžiku rozhraní IDE přidá novou metodu do souboru kódu formuláře.

6. Chcete-li přidat další metodu, otevřete soubor kódu pro ovládací prvek **CheckBox** v **Návrhář formulářů** , aby `checkBox1_CheckedChanged()` rozhraní IDE přidalo metodu. Tato metoda je volána vždy, když uživatel vybere nebo zruší zaškrtnutí políčka.

    > [!NOTE]
    > Při práci na programu se často přesouváte mezi editorem kódu a **Návrhář formulářů**. Rozhraní IDE usnadňuje navigaci v projektu. Pomocí **Průzkumník řešení** otevřete **Návrhář formulářů** dvojím kliknutím na *Form1.cs* v nabídce Visual C# nebo *Form1. vb* v Visual Basic nebo na panelu nabídek vyberte možnost**Návrhář** **zobrazení** > .

     Následující příklad ukazuje nový kód, který se zobrazí v editoru kódu.

     [!code-vb[VbExpressTutorial1Step6#2](../ide/codesnippet/VisualBasic/step-6-name-your-button-controls_2.vb)]
     [!code-csharp[VbExpressTutorial1Step6#2](../ide/codesnippet/CSharp/step-6-name-your-button-controls_2.cs)]

     Pět metod, které jste přidali, se nazývají *obslužné rutiny událostí*, protože je program volá vždy, když dojde k události (jako je například uživatel výběr tlačítka nebo výběru pole).

     Při zobrazení kódu pro ovládací prvek v rozhraní IDE v době návrhu, Visual Studio přidá metodu obslužné rutiny události pro ovládací prvek, pokud žádný není. Například když dvakrát kliknete na tlačítko, rozhraní IDE přidá obslužnou rutinu události pro <xref:System.Windows.Forms.Control.Click> událost (která je volána vždy, když uživatel zvolí tlačítko). Když dvakrát kliknete na zaškrtávací políčko, rozhraní IDE přidá obslužnou rutinu události pro <xref:System.Windows.Forms.CheckBox.CheckedChanged> událost (která je volána vždy, když uživatel vybere nebo zruší pole).

     Po přidání obslužné rutiny události pro ovládací prvek se k němu můžete kdykoli vrátit z **Návrhář formulářů** dvojitým kliknutím na ovládací prvek nebo na řádku nabídek, výběrem možnosti **Zobrazit** > **kód**.

     Názvy jsou důležité při sestavování programů a metody (včetně obslužných rutin událostí) můžou mít libovolný název, který chcete. Když přidáte obslužnou rutinu události s rozhraním IDE, vytvoří se název založený na názvu ovládacího prvku a události, která je zpracovávána. Například událost Click pro tlačítko s názvem **showButton** se nazývá `showButton_Click()` metoda obslužné rutiny události. Také se za názvem metody obvykle přidávají otevírací a uzavírací závorky `()` , které označují, že se metody diskutuje. Pokud se rozhodnete, že chcete změnit název proměnné kódu, klikněte pravým tlačítkem myši na proměnnou v kódu a pak > zvolte příkaz refaktor**Rename**. Všechny instance této proměnné v kódu jsou přejmenovány. Další informace viz [přejmenování](../ide/reference/rename.md) refaktoringu.

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

- Pokud chcete přejít na další krok kurzu, přečtěte si [článek krok 7: Přidejte součásti dialogového okna do formuláře](../ide/step-7-add-dialog-components-to-your-form.md).

- Pokud se chcete vrátit k předchozímu kroku kurzu [, přečtěte si krok 5: Přidejte ovládací prvky do formuláře](../ide/step-5-add-controls-to-your-form.md).
