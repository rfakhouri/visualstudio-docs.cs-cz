---
title: 'Krok 1: Vytvořte projekt Formulářové aplikace Windows'
ms.date: 03/23/2019
ms.prod: visual-studio-windows
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 16ac2422-e720-4e3a-b511-bc2a54201a86
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7f529d737816406b3a4f6aa9921a8dc6b902d2fb
ms.sourcegitcommit: b14b7a938a2aba9fcce4d5e813aadf2040b0dcda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/29/2019
ms.locfileid: "58647359"
---
# <a name="step-1-create-a-windows-forms-application-project"></a>Krok 1: Vytvořte projekt Formulářové aplikace Windows

Při vytváření prohlížeče obrázků, prvním krokem je vytvoření projektu aplikace Windows Forms.

 > [!TIP]
 > ![odkaz na video](../data-tools/media/playvideo.gif)video verzi tohoto tématu naleznete v tématu [kurz 1: Vytvoření prohlížeče obrázků v jazyce Visual Basic - Video 1](http://go.microsoft.com/fwlink/?LinkId=205209) nebo [kurz 1: Vytvoření prohlížeče obrázků v C# -Video 1](http://go.microsoft.com/fwlink/?LinkId=205199). Tato videa používají starší verzi sady Visual Studio, takže existují mírné rozdíly v některých příkazech nabídek a jiných prvcích uživatelského rozhraní. Nicméně koncepty a postupy fungují podobně jako v aktuální verzi sady Visual Studio.

::: moniker range="vs-2017"

## <a name="open-visual-studio-2017"></a>Open Visual Studio 2017

1. V panelu nabídky zvolte **souboru** > **nový** > **projektu**. Dialogové okno by měl vypadat takto.

     ![Dialogové okno nového projektu](../ide/media/newprojectdialogcallouts.png)<br/>
***Nový projekt** dialogové okno*

2. Zvolte buď **Visual C#**  nebo **jazyka Visual Basic** na levé straně **nový projekt** dialogové okno.

3. V seznamu šablon vyberte **aplikace Windows Forms (.NET Framework)**. Zadejte název nového formuláře **PictureViewer**a klikněte na tlačítko **OK** tlačítko.

    >[!NOTE]
    >Pokud se nezobrazí **aplikace Windows Forms (.NET Framework)** šablony, instalace pomocí instalačního programu sady Visual Studio **vývoj desktopových aplikací .NET** pracovního vytížení.<br/><br/>![Úloha vývoj desktopových aplikací .NET v instalačním programu sady Visual Studio](../ide/media/dot-net-desktop-dev-workload.png)<br/><br/> Další informace najdete v tématu [instalace sady Visual Studio](../install/install-visual-studio.md) stránky.

::: moniker-end

::: moniker range="vs-2019"

## <a name="open-visual-studio-2019"></a>Open Visual Studio 2019

1. V okně start zvolte **vytvořte nový projekt**.

   ![Zobrazit okno 'vytvořte nový projekt.](../get-started/media/vs-2019/create-new-project-dark-theme.png)

1. Na **vytvořte nový projekt** okno, zadejte nebo zadejte *Windows Forms* do vyhledávacího pole. Dále zvolte **jazyka Visual Basic** od jazyka seznamu a klikněte na tlačítko **Windows** ze seznamu platformy. 

   Po použití filtrů jazyka a libovolné platformy, zvolte **aplikace Windows Forms (.NET Framework)** šablony a klikněte na tlačítko **Další**.

   ![Výběr šablony jazyka Visual Basic pro aplikace Windows Forms (.NET Framework)](../get-started/visual-basic/media/vs-2019/vb-create-new-project-search-winforms-filtered.png)

   > [!NOTE]
   > Pokud se nezobrazí **aplikace Windows Forms (.NET Framework)** šablony, můžete jej nainstalovat z **vytvořte nový projekt** okna. V **nenašli, co hledáte?** zprávu, zvolte **nainstalovat další nástroje a funkce** odkaz.
   >
   > ![Odkaz "Nainstalovat další nástroje a funkce" z 'Nemůžete najít, co hledáte' zprávy v okně "vytvořit nový projekt.](../get-started/media/vs-2019/not-finding-what-looking-for.png) 
   > 
   > Dále zvolte v Visual Studio Installer, zvolte **vývoj desktopových aplikací .NET** pracovního vytížení.
   > 
   > ![Úlohy .NET core v instalačním programu sady Visual Studio](../ide/media/install-dot-net-desktop-env.png)
   >
   > Po tomto, zvolte **změnit** tlačítko v instalačním programu sady Visual Studio. Můžete být vyzváni k uložte svou práci; Pokud ano, udělejte to. Dále zvolte **pokračovat** instalace zatížení. 

1. V **konfigurovat nový projekt** okno, zadejte nebo vložte *PictureViewer* v **název projektu** pole. Potom kliknutím na možnost **vytvořit**.

::: moniker-end

Visual Studio vytvoří řešení pro vaši aplikaci. Řešení se chová jako kontejner pro všechny projekty a soubory požadované programem. Tyto pojmy budou podrobněji vysvětleny dále v tomto kurzu.

## <a name="about-the-windows-forms-application-project"></a>Informace o projektu aplikace Windows Forms

1. Vývojové prostředí obsahuje tři okna: hlavní okno **Průzkumníka řešení**a **vlastnosti** okna.

     Pokud chybí některé z těchto oken, obnovte výchozí rozložení okna, v řádku nabídek, výběrem **okno** > **resetovat rozložení okna**. Windows můžete zobrazit také pomocí příkazů nabídky. V panelu nabídky zvolte **zobrazení** > **okno vlastností** nebo **Průzkumníka řešení**. Pokud jsou všechny ostatní okna otevřená, zavřete je výběrem **zavřete** (tlačítko v jejich pravém horním rohu x).

    ::: moniker range="vs-2017"

    - **Hlavní okno** v tomto okně budete provádět většinu práce, např. práce s formuláři a úpravy kódu. V okně se zobrazí na formulář v nástrojích **Editor formulářů**. V horní části okna **úvodní stránka** kartu a **Form1.cs [Design]** karta se. (V jazyce Visual Basic, název karty koncovku *.vb* místo *.cs*.)

    ::: moniker-end

    ::: moniker range=">=vs-2019"

    - **Hlavní okno** v tomto okně budete provádět většinu práce, např. práce s formuláři a úpravy kódu. V okně se zobrazí na formulář v nástrojích **Editor formulářů**.

    ::: moniker-end

    - **Okno Průzkumníka řešení** v tomto okně můžete zobrazit a procházet všechny položky ve vašem řešení. Pokud zvolíte soubor, obsah **vlastnosti** okna změny. Pokud otevřete soubor kódu (který končí na *.cs* ve Vizuálu C# a *.vb* v jazyce Visual Basic), souboru s kódem nebo Návrhář kódu souboru se zobrazí. Návrhář je vizuální povrch, na kterém můžete přidat ovládací prvky jako tlačítka a seznamy. Návrhář formulářů aplikace Visual Studio používá termín **Návrháře formulářů Windows**.

    - **Okno vlastností** v tomto okně můžete změnit vlastnosti položek, které vyberete v jiných oknech. Například pokud zvolíte Form1, můžete změnit jeho název nastavením **Text** vlastnost a můžete změnit barvu pozadí nastavením **Backcolor** vlastnost.

    > [!NOTE]
    > Horní řádek v **Průzkumníka řešení** ukazuje **řešení "PictureViewer" (1 projekt)**, což znamená, že Visual Studio vytvořila řešení za vás. Řešení může obsahovat více než jeden projekt, ale prozatím budete pracovat s řešeními, která obsahují pouze jeden projekt.

1. V panelu nabídky zvolte **souboru** > **Uložit vše**.

     Jako alternativu zvolte **Uložit vše** tlačítko na panelu nástrojů, které ukazuje následující obrázek.

     ![Uložit všechny tlačítka panelu nástrojů](../ide/media/express_iconsaveall.png)<br/>
     ***Uložit vše** tlačítka panelu nástrojů*

     Visual Studio automaticky vyplní název složky a název projektu a poté uloží projekt ve vaší složce projekty.

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

- Přechod k dalšímu kroku výukového programu naleznete v tématu [krok 2: Spusťte svůj program](../ide/step-2-run-your-program.md).

- K návratu na téma přehledu přejděte [kurz 1: Vytvoření prohlížeče obrázků](../ide/tutorial-1-create-a-picture-viewer.md).

## <a name="see-also"></a>Viz také:

- [Vytvoření nového formuláře Windows](/dotnet/framework/winforms/creating-a-new-windows-form/)