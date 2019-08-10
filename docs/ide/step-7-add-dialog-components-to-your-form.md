---
title: 'Krok 7: Přidání součástí dialogového okna do formuláře'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: ea98c55e-6213-4893-ba7b-f19d7f119527
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bf6769535082e49d891c7065cc18eb05967dc192
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68925874"
---
# <a name="step-7-add-dialog-components-to-your-form"></a>Krok 7: Přidání komponent dialogových oken do formuláře
Chcete-li programu povolit otevírání souborů obrázků a výběr barvy pozadí, v tomto kroku přidáte <xref:System.Windows.Forms.OpenFileDialog> komponentu <xref:System.Windows.Forms.ColorDialog> a komponentu do formuláře.

Komponenta je jako ovládací prvek v některých způsobech. Pomocí **panelu nástrojů** přidáte komponentu do formuláře a nastavíte její vlastnosti pomocí okna **vlastnosti** . Ale na rozdíl od ovládacího prvku, přidání komponenty do formuláře nepřidá viditelnou položku, kterou může uživatel zobrazit ve formuláři. Místo toho poskytuje určité chování, které lze aktivovat pomocí kódu. Je to komponenta, která otevře dialogové okno **otevřít soubor** .

![odkaz na video](../data-tools/media/playvideo.gif)ve verzi videa tohoto tématu najdete v [kurzu 1: Vytvoření prohlížeče obrázků v Visual Basic-Video 3](http://go.microsoft.com/fwlink/?LinkId=205213) nebo [kurz 1: Vytvoření prohlížeče obrázků ve C# formátu-Video 3](http://go.microsoft.com/fwlink/?LinkId=205202) Tato videa používají starší verzi sady Visual Studio, takže existují mírné rozdíly v některých příkazech nabídky a dalších prvcích uživatelského rozhraní. Koncepty a postupy však fungují podobně v aktuální verzi sady Visual Studio.

## <a name="to-add-dialog-components-to-your-form"></a>Přidání součástí dialogového okna do formuláře

1. Zvolte **Návrhář formulářů** (**Form1.cs [Design]** nebo **Form1. vb [Design]** ) a pak otevřete skupinu **dialogy** v sadě **nástrojů**.

    > [!NOTE]
    > Skupina **dialogová okna** v **sadě nástrojů** obsahuje komponenty, které otevřou spoustu užitečných dialogových oken, které lze použít pro otevírání a ukládání souborů, procházení složek a výběr písma a barev. V tomto projektu použijete dvě komponenty dialogu: OpenFileDialog a ColorDialog.

2. Chcete-li přidat komponentu s názvem **OpenFileDialog1** do formuláře, dvakrát klikněte na položku **OpenFileDialog**. Chcete-li do formuláře přidat komponentu s názvem **colorDialog1** , dvakrát klikněte na položku **ColorDialog** v sadě **nástrojů**. (Použijete ho v dalším kroku kurzu.) Měla by se zobrazit oblast v dolní části **Návrhář formulářů** (pod formulářem **prohlížeče obrázků** ), která má ikonu pro každou ze dvou součástí dialogových oken, které jste přidali, jak je znázorněno na následujícím obrázku.

     ![Komponenty dialogového](../ide/media/express_dialogsadded.png)
okna komponenty dialogu

3. V oblasti v dolní části **Návrhář formulářů**vyberte ikonu **OpenFileDialog1** . Nastavte dvě vlastnosti:

    - Nastavte vlastnost **Filter** na následující (můžete ji zkopírovat a vložit):

        ```
        JPEG Files (*.jpg)|*.jpg|PNG Files (*.png)|*.png|BMP Files (*.bmp)|*.bmp|All files (*.*)|*.*
        ```

    - Nastavte vlastnost **title** na následující: **Vybrat soubor obrázku**

         Nastavení vlastnosti **filtru** určují typy souborů, které se zobrazí v dialogovém okně vyberte soubor **obrázku** .

    > [!NOTE]
    > Pokud chcete zobrazit příklad dialogového okna **otevřít soubor** v jiné aplikaci, otevřete Poznámkový **blok** nebo **Malování**a na panelu nabídek vyberte **soubor** > **otevřít**. Všimněte si, jak jsou v dolní části **soubory typu** rozevírací seznam. Právě jste použili vlastnost **Filter** v komponentě **OpenFileDialog** k nastavení. Všimněte si také, jak jsou vlastnosti nadpisu a **filtru** tučné v okně **vlastnosti** . Integrované vývojové prostředí (IDE) umožňuje zobrazit všechny vlastnosti, které byly změněny z jejich výchozích hodnot.

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

- Pokud chcete přejít na další krok kurzu, přečtěte si [krok 8: Napište kód pro zobrazení obslužné rutiny](../ide/step-8-write-code-for-the-show-a-picture-button-event-handler.md)události tlačítka Zobrazit obrázek.

- Pokud se chcete vrátit k předchozímu kroku kurzu [, přečtěte si krok 6: Pojmenujte své](../ide/step-6-name-your-button-controls.md)ovládací prvky tlačítek.
