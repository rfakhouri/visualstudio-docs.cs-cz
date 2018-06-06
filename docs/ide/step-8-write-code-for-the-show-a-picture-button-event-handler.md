---
title: 'Krok 8: Zapište kód pro zobrazení obslužné rutiny události obrázku tlačítka'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: 07f4ec00-cda4-42f4-98bb-37edc7167de7
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dc9bc3e5b0c3a61e911f7e49395f940ac07e2548
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34748601"
---
# <a name="step-8-write-code-for-the-show-a-picture-button-event-handler"></a>Krok 8: Zapište kód pro zobrazení obslužné rutiny události obrázku tlačítka
V tomto kroku provedete **zobrazit obrázek** tlačítko funkční následujícím způsobem:

-   Když uživatel vybere toto tlačítko, otevře se program <xref:System.Windows.Forms.OpenFileDialog> pole.

-   Pokud uživatel otevře soubor s obrázkem, program zobrazí tento obrázek v <xref:System.Windows.Forms.PictureBox>.

 Prostředí IDE má výkonný nástroj zvaný technologie IntelliSense, které vám pomůže psát kód. Při zadávání kódu rozhraní IDE otevře pole s navrhovaným dokončením pro částečné slova, která zadáte. Pokusí se zjistit, co chcete udělat dále a automaticky přejde na poslední položku, kterou vyberete ze seznamu. Můžete použít nahoru nebo dolů šipky přesunout v seznamu, nebo můžete pokračovat v psaní písmena tím zúžíte počet voleb. Až uvidíte volba chcete, vyberte **kartě** klíč ji vyberte. Nebo můžete návrhy ignorovat, pokud nejsou potřebné.

 ![odkaz na video](../data-tools/media/playvideo.gif)video verzi tohoto tématu naleznete v části [kurzu 1: vytvoření prohlížeče obrázků v jazyce Visual Basic – Video 4](http://go.microsoft.com/fwlink/?LinkId=205215) nebo [kurzu 1: vytvoření prohlížeče obrázků v jazyce C# - Video 4](http://go.microsoft.com/fwlink/?LinkId=205203). Tyto videa pomocí starší verze sady Visual Studio, takže drobné rozdíly v některé příkazy a další prvky uživatelského rozhraní. Však koncepty a postupy fungují podobně jako v aktuální verzi sady Visual Studio.

## <a name="to-write-code-for-the-show-a-picture-button-event-handler"></a>Napsat kód pro zobrazení obslužné rutiny události obrázku tlačítka

1.  Přejděte na **Návrhář formulářů Windows** a dvakrát klikněte na **zobrazit obrázek** tlačítko. Prostředí IDE okamžitě přejde na designer kódu a přesune kurzor tak, aby byl uvnitř `showButton_Click()` metoda, kterou jste přidali dříve.

2.  Typ `i` na prázdný řádek mezi složenými závorkami dvě `{ }`. (V jazyku Visual Basic, zadejte na prázdný řádek mezi `Private Sub...` a `End Sub`.) **IntelliSense** otevře okno, jak je znázorněno na následujícím obrázku.

     ![IntelliSense s Visual C&#35; kód](../ide/media/express_ifintellisense.png)
**IntelliSense** s kódem jazyka Visual C#

3.  **IntelliSense** okno by mělo zvýrazňovat slova `if`. (Pokud není, zadejte jedno malé písmeno `f`, a budou.) Všimněte si, jak malým *popisek* vedle pole **IntelliSense** s popisem, zobrazí se okno **fragment kódu pro Pokud příkaz**. (V jazyce Visual Basic popisek také uvádí, že to je fragment, ale poněkud liší mělo.) Chcete použít tento fragment, takže zvolte **kartě** klíč vložení `if` do vašeho kódu. Zvolte **kartě** klíč znovu pro použití `if` fragment kódu. (Pokud jste zvolili jinde a **IntelliSense** okno smazán, smažte vše přes `i` a ještě jednou a **IntelliSense** znovu otevře se okno.)

     ![Visual C&#35; kód](../ide/media/express_highlighttrue.png) kód jazyka Visual C#

4.  Pak zadejte další kód otevřete pomocí IntelliSense **otevřít soubor** dialogové okno. Pokud se uživatel rozhodl **OK** tlačítko PictureBox načte soubor, který uživatel vybral. Následující kroky ukazují, jak zadejte kód a i když je to mnoho kroků, je několika stisknutí kláves:

    1.  Začněte s vybraný text **true** v tomto fragmentu kódu. Typ `op` k jeho přepsání. (V jazyce Visual Basic spustit s počáteční velkým písmenem, takže zadejte `Op`.)

    2.  **IntelliSense** otevře okno a zobrazí **openFileDialog1**. Vyberte **kartě** klíč ji vyberte. (V jazyce Visual Basic začíná počáteční velkým písmenem, takže uvidíte **OpenFileDialog1**. Ujistěte se, že **OpenFileDialog1** je vybrána.)

         Další informace o `OpenFileDialog`, najdete v části [OpenFileDialog](http://msdn.microsoft.com/library/system.windows.forms.openfiledialog.aspx).

    3.  Zadejte tečku (`.`) (mnoho programátorů toto tečku.) Vzhledem k tomu, že jste zadali tečku ihned po **openFileDialog1**, **IntelliSense** okno otevře, zadá všechny **OpenFileDialog** vlastnosti a metody komponenty. Jedná se o stejné vlastnosti, které se zobrazují v **vlastnosti** okno když zvolíte v **Návrhář formulářů Windows**. Můžete také metody, které informují komponentu například (otevřete dialogové okno).

        > [!NOTE]
        >  **IntelliSense** můžete okno zobrazit vlastnosti a metody. Pokud chcete zjistit, co je zobrazeno, podívejte se na ikonu na levé straně jednotlivé položky **IntelliSense** okno. Zobrazí obrázek bloku vedle jednotlivých metod a obrázku klíče (nebo klíč) vedle každou vlastnost. Je také ikona blesku vedle jednotlivých událostí. Tyto obrázky se zobrazí následujícím způsobem.

         ![Ikona metoda](../ide/media/express_iconmethod.png)
**metoda** ikonu

         ![Ikona vlastnost](../ide/media/express_iconproperty.png)
**vlastnost** ikonu

         ![Ikona událostí](../ide/media/express_iconevent.png)
**událostí** ikonu

    4.  Spustit na typ `ShowDialog` (malá a velká písmena je důležitá pro technologii IntelliSense). `ShowDialog()` Metoda zobrazí **otevření souboru** dialogové okno. Po zdůraznily okno **ShowDialog**, vyberte **kartě** klíč. Můžete také zvýrazněte "ShowDialog" a zvolte **F1** klíč k získání nápovědy pro ni.

         Další informace o `ShowDialog()` metodu, najdete v části [ShowDialog – metoda](http://msdn.microsoft.com/library/c7ykbedk.aspx).

    5.  Při použití metody v ovládacím prvku nebo součást (označují jako *volání metody*), je nutné přidat závorky. Zadejte proto otvírání a zavírání závorkách ihned po "g" v `ShowDialog`: `()` by měl nyní vypadat jako "openFileDialog1.ShowDialog()".

        > [!NOTE]
        >  Metody jsou důležitou součástí žádné program a uvedených v tomto kurzu má několik způsobů použití metody. Můžete volat metodu komponenty Chcete-li určit, aby něco udělat, jako jste volali **OpenFileDialog** součásti `ShowDialog()` metoda. Můžete vytvořit vlastní metody, aby váš program provádět akce, jako je ta, vytváříte nyní, volá se `showButton_Click()` metodu, která otevře dialogové okno a obrázek, když uživatel vybere tlačítko.

    6.  Visual C# přidejte mezeru a poté přidejte dva symboly rovná se (`==`). V jazyce Visual Basic přidají mezeru a pak použít jeden symbol rovná se (`=`). (Visual C# a Visual Basic použít odlišné operátory rovnosti.)

    7.  Přidejte další místo. Jakmile to uděláte, jiné **IntelliSense** otevře se okno. Spustit na typ `DialogResult` a zvolte **kartě** klíč ho přidejte.

        > [!NOTE]
        >  Při psaní kódu pro volání metody, někdy vrací hodnotu. V takovém případě **OpenFileDialog** součásti <xref:System.Windows.Forms.CommonDialog.ShowDialog> metoda vrátí <xref:System.Windows.Forms.DialogResult> hodnotu. DialogResult je speciální hodnotu, která se dozvíte, co se stalo v dialogovém okně. **OpenFileDialog** součást může mít za následek výběr uživatele **OK** nebo **zrušit**, takže jeho `ShowDialog()` metoda vrací buď `DialogResult.OK` nebo `DialogResult.Cancel`.

    8.  Zadejte tečku k otevření hodnotu DialogResult **IntelliSense** okno. Zadejte písmeno `O` a zvolte **kartě** klíč vložení **OK**.

         Další informace o DialogResult najdete v tématu [DialogResult](http://msdn.microsoft.com/library/system.windows.forms.dialogresult.aspx).

        > [!NOTE]
        >  První řádek kódu by měla být kompletní. Visual C# by mělo být následující.
        >
        >  `if (openFileDialog1.ShowDialog() == DialogResult.OK)`
        >
        >  V jazyce Visual Basic musí být následující.
        >
        >  `If OpenFileDialog1.ShowDialog() = DialogResult.OK Then`

    9. Teď můžete přidáte další řádek kódu. Můžete ji zadat (nebo zkopírujte a vložte jej), ale zvažte použití technologie IntelliSense ho přidejte. Čím více se seznámíte se s IntelliSense, tím rychleji můžete napsat vlastní kód. Váš koncový `showButton_Click()` metoda vypadá jako následující. (Vyberte **VB** chcete zobrazit verzi kód jazyka Visual Basic.)

         [!code-csharp[VbExpressTutorial1Step8#1](../ide/codesnippet/CSharp/step-8-write-code-for-the-show-a-picture-button-event-handler_1.cs)]
         [!code-vb[VbExpressTutorial1Step8#1](../ide/codesnippet/VisualBasic/step-8-write-code-for-the-show-a-picture-button-event-handler_1.vb)]

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

-   Chcete-li přejít k dalšímu kroku kurzu, přečtěte si téma [krok 9: Zkontrolujte, okomentujte a otestujte svůj kód](../ide/step-9-review-comment-and-test-your-code.md).

-   Chcete-li vrátit k předchozímu kroku kurzu, přečtěte si téma [krok 7: přidejte do svého formuláře komponenty dialogových oken](../ide/step-7-add-dialog-components-to-your-form.md).
