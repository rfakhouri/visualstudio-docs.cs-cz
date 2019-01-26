---
title: 'Krok 1: Vytvořte projekt Formulářové aplikace Windows'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 16ac2422-e720-4e3a-b511-bc2a54201a86
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2c8e94f0018cadbfcc26b781637c478fa9768ca8
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55012804"
---
# <a name="step-1-create-a-windows-forms-application-project"></a>Krok 1: Vytvořte projekt Formulářové aplikace Windows
Při vytváření prohlížeče obrázků, prvním krokem je vytvoření projektu aplikace Windows Forms.

 ![odkaz na video](../data-tools/media/playvideo.gif)video verzi tohoto tématu naleznete v tématu [kurz 1: Vytvoření prohlížeče obrázků v jazyce Visual Basic - Video 1](http://go.microsoft.com/fwlink/?LinkId=205209) nebo [kurz 1: Vytvoření prohlížeče obrázků v C# -Video 1](http://go.microsoft.com/fwlink/?LinkId=205199). Tato videa používají starší verzi sady Visual Studio, takže existují mírné rozdíly v některých příkazech nabídek a jiných prvcích uživatelského rozhraní. Nicméně koncepty a postupy fungují podobně jako v aktuální verzi sady Visual Studio.

## <a name="to-create-a-windows-forms-application-project"></a>Vytvoření projektu aplikace Windows Forms

1.  V panelu nabídky zvolte **souboru** > **nový** > **projektu**. Dialogové okno by měl vypadat takto.

     ![Dialogové okno nového projektu](../ide/media/newprojectdialogcallouts.png)
**nový projekt** dialogové okno

2.  Zvolte buď **Visual C#** nebo **jazyka Visual Basic** v **nainstalované šablony** seznamu.

3.  V seznamu šablon vyberte **formulářová aplikace Windows** ikonu. Zadejte název nového formuláře **PictureViewer**a klikněte na tlačítko **OK** tlačítko.

     Visual Studio vytvoří řešení pro vaši aplikaci. Řešení se chová jako kontejner pro všechny projekty a soubory požadované programem. Tyto pojmy budou podrobněji vysvětleny dále v tomto kurzu.

4.  Následující obrázek znázorňuje, co teď byste měli vidět v rozhraní sady Visual Studio.

    > [!NOTE]
    >  Rozložení okna nemusí vypadat přesně jako na tomto obrázku. Přesné rozložení okna závisí na verzi sady Visual Studio, programovací jazyk, který používáte a dalších faktorů. Nicméně byste měli ověřit, že zobrazí všechna tři okna.

     ![Okno integrovaného vývojového prostředí](../ide/media/express_ideoverview_visio.png)
**IDE** okna

     Rozhraní obsahuje tři okna: hlavní okno **Průzkumníka řešení**a **vlastnosti** okna.

     Pokud chybí některé z těchto oken, obnovte výchozí rozložení okna, v řádku nabídek, výběrem **okno** > **resetovat rozložení okna**. Windows můžete zobrazit také pomocí příkazů nabídky. V panelu nabídky zvolte **zobrazení** > **okno vlastností** nebo **Průzkumníka řešení**. Pokud jsou všechny ostatní okna otevřená, zavřete je výběrem **zavřete** (tlačítko v jejich pravém horním rohu x).

5.  Na obrázku jsou znázorněna následující okna (přechod ve směru hodinových ručiček od levého horního rohu):

    -   **Hlavní okno** v tomto okně budete provádět většinu práce, např. práce s formuláři a úpravy kódu. Na obrázku, v okně se zobrazí na formulář v nástrojích **Editor formulářů**. V horní části okna **úvodní stránka** kartu a **Form1.cs [Design]** karta se. (V jazyce Visual Basic, název karty koncovku *.vb* místo *.cs*.)

    -   **Okno Průzkumníka řešení** v tomto okně můžete zobrazit a procházet všechny položky ve vašem řešení. Pokud zvolíte soubor, obsah **vlastnosti** okna změny. Pokud otevřete soubor kódu (který končí na *.cs* ve Vizuálu C# a *.vb* v jazyce Visual Basic), souboru s kódem nebo Návrhář kódu souboru se zobrazí. Návrhář je vizuální povrch, na kterém můžete přidat ovládací prvky jako tlačítka a seznamy. Návrhář formulářů aplikace Visual Studio používá termín **Návrháře formulářů Windows**.

    -   **Okno vlastností** v tomto okně můžete změnit vlastnosti položek, které vyberete v jiných oknech. Například pokud zvolíte Form1, můžete změnit jeho název nastavením **Text** vlastnost a můžete změnit barvu pozadí nastavením **Backcolor** vlastnost.

    > [!NOTE]
    >  Horní řádek v **Průzkumníka řešení** ukazuje **řešení "PictureViewer" (1 projekt)**, což znamená, že Visual Studio vytvořila řešení za vás. Řešení může obsahovat více než jeden projekt, ale prozatím budete pracovat s řešeními, která obsahují pouze jeden projekt.

6.  V panelu nabídky zvolte **souboru** > **Uložit vše**.

     Jako alternativu zvolte **Uložit vše** tlačítko na panelu nástrojů, které ukazuje následující obrázek.

     ![Uložit všechny tlačítka panelu nástrojů](../ide/media/express_iconsaveall.png)
**Uložit vše** tlačítka panelu nástrojů

     Visual Studio automaticky vyplní název složky a název projektu a poté uloží projekt ve vaší složce projekty.

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

-   Přechod k dalšímu kroku výukového programu naleznete v tématu [krok 2: Spusťte svůj program](../ide/step-2-run-your-program.md).

-   K návratu na téma přehledu přejděte [kurz 1: Vytvoření prohlížeče obrázků](../ide/tutorial-1-create-a-picture-viewer.md).
