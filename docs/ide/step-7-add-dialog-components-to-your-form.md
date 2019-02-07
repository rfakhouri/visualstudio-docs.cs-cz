---
title: 'Krok 7: Přidejte do svého formuláře komponenty dialogových oken'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: ea98c55e-6213-4893-ba7b-f19d7f119527
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 11788ed21d536642bdb3c88c59cea2dad009c9c3
ms.sourcegitcommit: 01334abf36d7e0774329050d34b3a819979c95a2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55853479"
---
# <a name="step-7-add-dialog-components-to-your-form"></a>Krok 7: Přidejte do svého formuláře komponenty dialogových oken
Chcete-li povolit programu otevírání souborů obrázků a výběr barvy pozadí, v tomto kroku přidáte <xref:System.Windows.Forms.OpenFileDialog> komponenty a <xref:System.Windows.Forms.ColorDialog> komponentu do formuláře.

 Komponenta je jako ovládací prvek v některých ohledech. Můžete použít **nástrojů** k přidání komponenty do formuláře a nastavte její vlastnosti pomocí **vlastnosti** okna. Ale na rozdíl od ovládacího prvku, přidání komponenty do formuláře nepřidává viditelnou položku, kterou může uživatel vidět ve formuláři. Místo toho poskytuje určité druhy chování, které můžete aktivovat s kódem. Jedná se o součást, která se otevře **otevřít soubor** dialogové okno.

 ![odkaz na video](../data-tools/media/playvideo.gif)video verzi tohoto tématu naleznete v tématu [kurz 1: Vytvoření prohlížeče obrázků v jazyce Visual Basic - Video 3](http://go.microsoft.com/fwlink/?LinkId=205213) nebo [kurz 1: Vytvoření prohlížeče obrázků v C# – Video 3](http://go.microsoft.com/fwlink/?LinkId=205202). Tato videa používají starší verzi sady Visual Studio, takže existují mírné rozdíly v některých příkazech nabídek a jiných prvcích uživatelského rozhraní. Nicméně koncepty a postupy fungují podobně jako v aktuální verzi sady Visual Studio.

## <a name="to-add-dialog-components-to-your-form"></a>Přidat do svého formuláře komponenty dialogových oken

1.  Zvolte **Návrháře formulářů Windows** (**Form1.cs [Design]** nebo **Form1.vb [Design]**) a pak otevřete **dialogová okna** skupiny  **Panel nástrojů**.

    > [!NOTE]
    >  **Dialogová okna** skupiny **nástrojů** komponentami, které otevírají mnoho užitečných dialogových oken, které je možné použít pro otevírání a ukládání souborů, procházení složek a výběru písma a barvy. V tomto projektu použijete dvě komponenty dialogového okna: OpenFileDialog – a ColorDialog

2.  K přidání komponenty s názvem **openFileDialog1** do formuláře dvakrát klikněte na panel **OpenFileDialog**. K přidání komponenty s názvem **colorDialog1** do formuláře dvakrát klikněte na panel **ColorDialog** v **nástrojů**. (Můžete použít v dalším kroku výukového programu.) Měli byste vidět plochu v dolní části **Návrháře formulářů Windows** (pod **prohlížeče obrázků** formuláře), který má ikonu pro každou z komponent dvou dialogových oken, které jste přidali, jak je znázorněno na následujícím obrázku.

     ![Komponenty dialogového okna](../ide/media/express_dialogsadded.png)
**dialogové okno** komponenty

3.  Zvolte **openFileDialog1** ikonu v oblasti v dolní části **Návrháře formulářů Windows**. Nastavte dvě vlastnosti:

    -   Nastavte **filtr** vlastnost následující (můžete zkopírovat a vložit):

        ```
        JPEG Files (*.jpg)|*.jpg|PNG Files (*.png)|*.png|BMP Files (*.bmp)|*.bmp|All files (*.*)|*.*
        ```

    -   Nastavte **název** vlastnost na následující: **Vyberte soubor s obrázkem**

         **Filtr** nastavení vlastností zadejte druhy typů souborů, které se zobrazí v **vybrat obrázek** dialogové okno souboru.

    > [!NOTE]
    >  Chcete-li zobrazit příklad **otevřít soubor** dialogové okno v jiné aplikaci, otevřete **Poznámkový blok** nebo **Malování**a na panelu nabídek zvolte **souboru**  >  **Otevřít**. Všimněte si, jak je **soubory typu** rozevírací seznam v dolní části. Právě jste použili **filtr** vlastnost v **OpenFileDialog** součásti k tomuto nastavení. Všimněte si také, jak **Title** a **filtr** vlastnosti jsou zobrazeny tučným písmem v **vlastnosti** okna. Rozhraní IDE toto dělá, abyste viděli všechny vlastnosti, které byly změněny z výchozí hodnoty.

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

-   Přechod k dalšímu kroku výukového programu naleznete v tématu [krok 8: Napsat kód pro zobrazení obslužné rutiny události obrázku tlačítka](../ide/step-8-write-code-for-the-show-a-picture-button-event-handler.md).

-   Chcete-li vrátit k předchozímu kroku tutoriálu, přečtěte si téma [krok 6: Pojmenovat vaše tlačítka](../ide/step-6-name-your-button-controls.md).
