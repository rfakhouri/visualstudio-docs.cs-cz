---
title: 'Kurz: Začínáme s C# a ASP.NET Core'
titleSuffix: ''
description: Zjistěte, jak vytvořit webovou aplikaci ASP.NET Core v sadě Visual Studio s C#, krok za krokem.
ms.custom: seodec18, get-started
ms.date: 03/23/2019
ms.technology: vs-ide-general
ms.prod: visual-studio-windows
ms.topic: tutorial
ms.devlang: CSharp
author: TerryGLee
ms.author: tglee
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: cb45386795077289e14e19ec9ad7e0071521db22
ms.sourcegitcommit: 8d453b345c72339c37b489a140dad00b244e6ba4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/26/2019
ms.locfileid: "58475900"
---
# <a name="tutorial-get-started-with-c-and-aspnet-core-in-visual-studio"></a>Kurz: Začínáme s C# a ASP.NET Core v sadě Visual Studio

V tomto kurzu o vývoji C# s využitím ASP.NET Core pomocí sady Visual Studio budete vytvoření webové aplikace v C# ASP.NET Core, provést změny, prozkoumat některé funkce integrovaného vývojového prostředí a pak spusťte aplikaci.

## <a name="before-you-begin"></a>Před zahájením

### <a name="install-visual-studio"></a>Instalace sady Visual Studio

::: moniker range="vs-2017"

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) stránku a nainstalovat zdarma.

::: moniker-end

::: moniker range="vs-2019"

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+rc) stránku a nainstalovat zdarma.

::: moniker-end

### <a name="update-visual-studio"></a>Aktualizace sady Visual Studio

Pokud jste již nainstalovali aplikaci Visual Studio, ujistěte se, že používáte nejnovější verzi. Další informace o tom, jak aktualizovat vaši instalaci, najdete v článku [aktualizovat na nejnovější verzi aplikace Visual Studio](../../install/update-visual-studio.md) stránky.

### <a name="choose-your-theme-optional"></a>Zvolte motiv (volitelné)

V tomto kurzu zahrnuje snímky obrazovky, použít tmavý motiv. Pokud nepoužíváte tmavý motiv, ale chtěli, najdete v článku [přizpůsobit IDE sady Visual Studio a Editor](../../ide/quickstart-personalize-the-ide.md) stránku a zjistěte, jak.

## <a name="create-a-project"></a>Vytvoření projektu

Nejprve vytvoříte projekt ASP.NET Core. Typ projektu obsahuje všechny soubory šablony, které budete potřebovat plně funkčním webem, než jste přidali ještě nic!

::: moniker range="vs-2017"

1. Otevřete Visual Studio 2017.

2. V horní nabídce zvolte **souboru** > **nový** > **projektu**.

3. V **nový projekt** dialogové okno v levém podokně rozbalte **Visual C#**, rozbalte **webové**a klikněte na tlačítko **.NET Core**. V prostředním podokně vyberte **webové aplikace ASP.NET Core**. Pojmenujte jej *MyCoreApp* a zvolte **OK**.

   ![Šablona projektu webové aplikace ASP.NET Core v dialogovém okně Nový projekt v integrovaném vývojovém prostředí sady Visual Studio](media/csharp-aspnet-choose-template-name-razor-mycoreapp-file.png)

### <a name="add-a-workload-optional"></a>Přidat úlohu (volitelné)

Pokud se nezobrazí **webové aplikace ASP.NET Core** šablony projektu, můžete ho získat tak, že přidáte **vývoj pro ASP.NET a web** pracovního vytížení. Přidejte tuto úlohu v jednom z následujících způsobů, v závislosti na tom, které jsou na vašem počítači nainstalovaná aktualizace sady Visual Studio 2017.

#### <a name="option-1-use-the-new-project-dialog-box"></a>Option 1: Pomocí dialogového okna Nový projekt

1. Vyberte **otevřít instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno. (V závislosti na nastavení zobrazení může být potřeba stránku posunout, aby ji.)

   ![Vyberte odkaz otevřít instalační program Visual Studio z dialogového okna Nový projekt](../media/open-visual-studio-installer-mycoreapp.png)

1. Spustí se instalační program pro Visual Studio. Zvolte **vývoj pro ASP.NET a web** úlohy a klikněte na tlačítko **změnit**.

   ![Úlohy pro vývoj pro různé platformy .NET core v instalačním programu sady Visual Studio](../media/tutorial-aspnet-workload.png)

   (Může mít ukončit sadu Visual Studio, abyste mohli pokračovat v instalaci nové úlohy.)

#### <a name="option-2-use-the-tools-menu-bar"></a>Option 2: Pomocí nabídky panelu nástrojů

1. Zrušit z celkového počtu **nový projekt** dialogové okno. Potom v horní nabídce vyberte **nástroje** > **stažení nástrojů a funkcí**.

1. Spustí se instalační program pro Visual Studio. Zvolte **vývoj pro ASP.NET a web** úlohy a klikněte na tlačítko **změnit**.

   (Může mít ukončit sadu Visual Studio, abyste mohli pokračovat v instalaci nové úlohy.)

### <a name="add-a-project-template"></a>Přidat šablonu projektu

1. V **nová webová aplikace ASP.NET Core** dialogového okna zvolte **webovou aplikaci** šablony projektu.

1. Ověřte, že **ASP.NET Core 2.1** se zobrazí v horní nabídce rozevíracího seznamu. Potom kliknutím na možnost **OK**.

   ![Dialogové okno nové webové aplikace ASP.NET Core](media/new-project-csharp-aspnet-razor-web-app.png)

   > [!NOTE]
   > Pokud nevidíte **ASP.NET Core 2.1** nebo později z hlavní nabídky rozevíracího seznamu, ujistěte se, že používáte nejnovější verzi sady Visual Studio. Další informace o tom, jak aktualizovat vaši instalaci, najdete v článku [aktualizovat na nejnovější verzi aplikace Visual Studio](../../install/update-visual-studio.md) stránky.

::: moniker-end

::: moniker range="vs-2019"

1. V okně start zvolte **vytvořte nový projekt**.

   ![Zobrazit okno 'vytvořte nový projekt.](../../get-started/media/vs-2019/create-new-project-dark-theme.png)

1. Na **vytvořte nový projekt** okno, zadejte nebo zadejte *ASP.NET* do vyhledávacího pole. Dále zvolte **C#** od jazyka seznamu a klikněte na tlačítko **Windows** ze seznamu platformy. 

   Po použití filtrů jazyka a libovolné platformy, zvolte **webové aplikace ASP.NET Core** šablony a klikněte na tlačítko **Další**.

   ![Zvolte C# šablony pro webové aplikace ASP.NET Core](./media/vs-2019/csharp-create-new-project-search-aspnet-core-filtered.png)

   > [!NOTE]
   > Pokud se nezobrazí **webové aplikace ASP.NET Core** šablony, můžete jej nainstalovat z **vytvořte nový projekt** okna. V **nenašli, co hledáte?** zprávu, zvolte **nainstalovat další nástroje a funkce** odkaz.
   >
   > ![Odkaz "Nainstalovat další nástroje a funkce" z 'Nemůžete najít, co hledáte' zprávy v okně "vytvořit nový projekt.](../../get-started/media/vs-2019/not-finding-what-looking-for.png) 
   > 
   > Pak ve Visual Studio Installer, zvolte **vývoj pro ASP.NET a web** pracovního vytížení.
   >
   > ![Úlohy pro vývoj pro různé platformy .NET core v instalačním programu sady Visual Studio](../../get-started/media/aspnet-core-web-dev-workload.png)
   >
   > Po tomto, zvolte **změnit** tlačítko v instalačním programu sady Visual Studio. Můžete být vyzváni k uložte svou práci; Pokud ano, udělejte to. Dále zvolte **pokračovat** instalace zatížení. Pak se vraťte ke kroku 2 v tomto "[vytvořte projekt](#create-a-project)" postup.

1. V **konfigurovat nový projekt** okno, zadejte nebo vložte *MyCoreApp* v **název projektu** pole. Potom kliknutím na možnost **vytvořit**.

   ![v okně 'Konfigurovat nový projekt' pojmenujte svůj projekt "MyCoreApp.](./media/vs-2019/csharp-name-your-aspnet-mycoreapp-project.png)

1. V **vytvořit novou webovou aplikaci ASP.NET Core** okna, ověřte, že **ASP.NET Core 2.1** nebo novějším se zobrazí v horní nabídce rozevíracího seznamu. Potom kliknutím na možnost **webovou aplikaci**, který obsahuje příklad stránky Razor. Dále zvolte **vytvořit**.

   ![V okně "vytvořit novou webovou aplikaci ASP.NET Core.](./media/vs-2019/csharp-create-aspnet-core-razor-pages-app.png)

   Visual Studio otevře nový projekt.

::: moniker-end

### <a name="about-your-solution"></a>Informace o řešení

Toto řešení následuje **stránky Razor** vzoru návrhu. Se liší od [Model-View-Controller (MVC)](/aspnet/core/tutorials/first-mvc-app/start-mvc?view=aspnetcore-2.1&tabs=aspnetcore2x) návrh vzoru v dané jeho zjednodušené zahrnout samotný kód modelu a kontroler v rámci stránky Razor.

## <a name="tour-your-solution"></a>Prohlédnete si vašich řešení

 1. Šablona projektu vytvoří řešení pomocí jednoho projektu ASP.NET Core, který je pojmenován _MyCoreApp_. Zvolte **Průzkumníka řešení** kartu a zobrazit jeho obsah.

    ![Průzkumníka řešení ASP.NET v sadě Visual Studio pro stránky Razor řešení s názvem MyCoreApp](media/csharp-aspnet-razor-solution-explorer-mycoreapp.png)

 1. Rozbalte **stránky** složky a potom rozbalte *About.cshtml*.

     ![About.cshtml souboru v Průzkumníku řešení v sadě Visual Studio](media/csharp-aspnet-razor-solution-explorer-aboutcshtml.png)

 1. Zobrazení **About.cshtml** souboru v editoru kódu.

     ![Zobrazení About.cshtml souboru v editoru kódu sady Visual Studio](media/csharp-aspnet-razor-aboutcshtml-mycoreapp-code.png)

 1. Zvolte **About.cshtml.cs** souboru.

     ![Zvolte soubor About.cshtml.cs v editoru kódu sady Visual Studio](media/csharp-aspnet-razor-solution-explorer-aboutcshtmlcs.png)

 1. Zobrazení **About.cshtml.cs** souboru v editoru kódu.

     ![Zobrazení About.cshtml souboru v editoru kódu sady Visual Studio](media/csharp-aspnet-razor-aboutcshtmlcs-mycoreapp-code.png)

 1. Obsahuje projekt **wwwroot** složku, která je kořenový adresář pro váš web. Rozbalte složky a zobrazit jeho obsah.

     ![složky Wwwroot v Průzkumníku řešení v sadě Visual Studio](media/csharp-aspnet-razor-solution-explorer-wwwroot.png)

    Můžete vložit obsah statického webu&mdash;jako jsou šablony stylů CSS, obrázky a knihovny JavaScript&mdash;přímo v cestách kamkoli chcete.

 1. Projekt také obsahuje konfigurační soubory, které Správa webové aplikace za běhu. Výchozí aplikace [konfigurace](/aspnet/core/fundamentals/configuration) je uložen v *appsettings.json*. Tato nastavení však můžete přepsat pomocí *appsettings. Development.JSON*. Rozbalte **appsettings.json** soubor zobrazíte **appsettings. Development.JSON** souboru.

     ![Konfigurační soubory v Průzkumníku řešení v sadě Visual Studio](media/csharp-aspnet-razor-solution-explorer-appsettingsjson.png)

## <a name="run-debug-and-make-changes"></a>Spouštět, ladit a provést změny

1. Zvolte **služby IIS Express** tlačítko v integrovaném vývojovém prostředí pro sestavení a spuštění aplikace v režimu ladění. (Nebo stisknout **F5**, nebo zvolte **ladění** > **spustit ladění** z řádku nabídek.)

     ![Vyberte tlačítko služby IIS Express v sadě Visual Studio](media/csharp-aspnet-razor-iisexpress.png)

     > [!NOTE]
     > Pokud se zobrazí chybová zpráva s upozorněním **nelze se připojit k webovému serveru služby IIS Express**, zavřete sadu Visual Studio a otevřete jej pomocí **spustit jako správce** možnost v nabídce klikněte pravým tlačítkem nebo kontext. Spusťte aplikaci znovu.
     >
     > Může se také zobrazit zprávu s dotazem, jestli chcete přijmout certifikát SSL služby IIS Express. Chcete-li zobrazit kód ve webovém prohlížeči, zvolte **Ano**a klikněte na tlačítko **Ano** Pokud obdržíte zprávu s upozorněním zabezpečení zpracování. 

1. Visual Studio otevře okno prohlížeče. Pak zobrazí **Domů**, **o**, a **kontakt** stránky v panelu nabídek. (Pokud ho nevidíte, vyberte položku "hamburgerové" nabídky si je chcete zobrazit.)

    ![Vyberte položku "hamburgerové" nabídky na řádku nabídek ve vaší webové aplikaci](media/csharp-aspnet-razor-browser-page.png)

     > [!TIP]
     > Pokud váš projekt je otevřen v okně prohlížeče se nedá upravit kód v editoru kódu sady Visual Studio. 

1. Zvolte **o** z řádku nabídek.

   ![Vyberte o v řádku nabídek okna prohlížeče pro vaši aplikaci](media/csharp-aspnet-razor-browser-page-about-menu.png)

   Mimo jiné **o** text, který je nastavena v vykreslí stránku v prohlížeči *About.cshtml* souboru.

   ![Zobrazit text na stránce o](media/csharp-aspnet-razor-browser-page-about.png)

1. Nechte okno prohlížeče otevřít a vrátí do sady Visual Studio.

1. V sadě Visual Studio, zvolte **About.cshtml**. Odstraňte slovo _Další_ a místo něj přidat slova _souborů a adresářů_.

    ![Změní celý text v souboru About.cshtml](media/csharp-aspnet-razor-aboutcshtml-mycoreapp-code-changed.png)

1. Zvolte **About.cshtml.cs**. Potom Vyčistit `using` direktivy v horní části souboru s použitím následující klávesovou zkratku:

   Vybrat kteroukoli z šedě `using` direktivy a [rychlé akce](../../ide/quick-actions.md) žárovka se zobrazí pod blikajícím kurzorem nebo na levém okraji. Zvolte žárovku a pak zvolte **odebrat nepotřebné direktivy using**.

   ![V souboru About.cshtml.cs odebrat nepotřebné direktivy using](media/csharp-aspnet-razor-remove-unnecessary-usings.png)

     Visual Studio odstraní nadbytečné `using` direktivy ze souboru.

1. Vedle `OnGet()` metodu, změňte obsah následujícím kódem:

     ```csharp
     public void OnGet()
     {
         string directory = Environment.CurrentDirectory;
     Message = String.Format("Your directory is {0}.", directory);
     }
    ```
1. Všimněte si, že dvě podtržení vlnovkou Microsoft.VSTS.Common **prostředí** a **řetězec**. Podtržení vlnovkou zobrazeny, protože tyto typy nejsou v oboru.

   ![Chyby označené podtržení vlnovkou v OnGet – metoda](media/csharp-aspnet-razor-add-new-on-get-method.png)

    Otevřít **seznam chyb** nástrojů se zobrazí stejné chyby uvedeny zde. (Pokud se nezobrazí **seznam chyb** nástrojů, zvolte **zobrazení** > **seznam chyb** v horní nabídce.)

   ![Seznam chyb v sadě Visual Studio](media/csharp-aspnet-razor-error-list.png)

1. Opravíme to. V editoru kódu umístěte ukazatel myši buď řádku, který obsahuje chybu a pak zvolte žárovky rychlé akce na levém okraji. Zvolte z rozevírací nabídky **pomocí systému;** případné chyby opravte a přidejte tuto direktivu do horní části souboru.

   ![Přidat "použití systému;" – direktiva](media/csharp-aspnet-razor-add-usings.png)

1. Stisknutím klávesy **Ctrl**+**S** uložte provedené změny a aktualizovat aplikace ve webovém prohlížeči.

1. V horní části stránky na webu společnosti, zvolte **o** zobrazíte změny.

   ![Zobrazit aktualizovaný o stránku, která obsahuje změny, které jste provedli](media/csharp-aspnet-razor-browser-page-about-changed.png)

1. Zavřete webový prohlížeč, stiskněte klávesu **Shift**+**F5** zastavení režimu ladění, a pak zavřete sadu Visual Studio.

## <a name="quick-answers-faq"></a>Rychlé odpovědi – nejčastější dotazy

Tady je rychlý – nejčastější dotazy ke zvýraznění některých klíčových koncepcí.

### <a name="what-is-c"></a>Co je C#?

[C#](/dotnet/csharp/getting-started/introduction-to-the-csharp-language-and-the-net-framework) je typově bezpečný a objektově orientovaný programovací jazyk, který bude robustní a snadno osvojitelná.

### <a name="what-is-aspnet-core"></a>Co je ASP.NET Core?

ASP.NET Core je open source a multiplatformní rozhraní pro vytváření aplikací připojených k Internetu, jako jsou webové aplikace a služby. Aplikace ASP.NET Core můžete spustit na .NET Core nebo .NET Framework. Můžete vyvíjet a spouštět multiplatformní aplikace ASP.NET Core ve Windows, Mac a Linux. ASP.NET Core je open source v [Githubu](https://github.com/aspnet/home).

### <a name="what-is-visual-studio"></a>Co je sada Visual Studio?

Visual Studio je integrované vývojové sady nástrojů podporujících produktivitu pro vývojáře. Si ho představit jako program, který můžete použít k vytvoření aplikací a aplikací.

## <a name="next-steps"></a>Další kroky

Blahopřejeme k dokončení tohoto kurzu! Doufáme, že jste se dozvěděli ještě něco o jazyce C#, ASP.NET Core a integrovaném vývojovém prostředí sady Visual Studio. Další informace o vytváření webové aplikace nebo webu pomocí jazyka C# a technologie ASP.NET, pokračujte v následujících kurzech:

> [!div class="nextstepaction"]
> [Vytvoření webové aplikace stránky Razor pomocí ASP.NET Core](/aspnet/core/tutorials/razor-pages/?view=aspnetcore-2.1)

## <a name="see-also"></a>Viz také:

[Publikování webové aplikace do služby Azure App Service pomocí sady Visual Studio](../../deployment/quickstart-deploy-to-azure.md)
