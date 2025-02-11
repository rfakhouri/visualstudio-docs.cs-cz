---
title: 'Kurz: Začínáme s C# a ASP.NET Core'
titleSuffix: ''
description: Naučte se, jak vytvořit webovou aplikaci ASP.NET Core v aplikaci Visual C#Studio s nástrojem, krok za krokem.
ms.custom: seodec18, get-started
ms.date: 05/29/2019
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
ms.openlocfilehash: ac544f033e8b021b7ef0a6253fbd0cb65b4450f5
ms.sourcegitcommit: 44e9b1d9230fcbbd081ee81be9d4be8a485d8502
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2019
ms.locfileid: "70180482"
---
# <a name="tutorial-get-started-with-c-and-aspnet-core-in-visual-studio"></a>Kurz: Začínáme s C# a ASP.NET Core v aplikaci Visual Studio

V tomto kurzu pro C# vývoj s ASP.NET Core pomocí sady Visual Studio vytvoříte webovou aplikaci C# ASP.NET Core, provedete její změny, prozkoumáte některé funkce rozhraní IDE a pak aplikaci spustíte.

## <a name="before-you-begin"></a>Před zahájením

### <a name="install-visual-studio"></a>Instalace sady Visual Studio

::: moniker range="vs-2017"

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) stránku a nainstalovat zdarma.

::: moniker-end

::: moniker range="vs-2019"

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads) stránku a nainstalovat zdarma.

::: moniker-end

### <a name="update-visual-studio"></a>Aktualizace sady Visual Studio

Pokud jste již nainstalovali aplikaci Visual Studio, ujistěte se, že používáte nejnovější verzi. Další informace o tom, jak aktualizovat instalaci, najdete na stránce o [aktualizaci sady Visual Studio na nejnovější verzi](../../install/update-visual-studio.md) .

### <a name="choose-your-theme-optional"></a>Zvolte motiv (volitelné)

Tento kurz obsahuje snímky obrazovky, které používají tmavý motiv. Pokud nepoužíváte tmavý motiv, ale chtěli, najdete v článku [přizpůsobit IDE sady Visual Studio a Editor](../../ide/quickstart-personalize-the-ide.md) stránku a zjistěte, jak.

## <a name="create-a-project"></a>Vytvoření projektu

Nejprve vytvoříte projekt ASP.NET Core. Typ projektu se dodává se všemi soubory šablon, které budete potřebovat pro plně funkční web, než dokonce cokoli přidáte!

::: moniker range="vs-2017"

1. Otevřete Visual Studio 2017.

2. V horním řádku nabídek vyberte **soubor** > **Nový** > **projekt**.

3. V dialogovém okně **Nový projekt** v levém podokně rozbalte položku **vizuál C#** , rozbalte položku **Web**a potom zvolte možnost **.NET Core**. V prostředním podokně vyberte **webové aplikace ASP.NET Core**. Pak název souboru *MyCoreApp* a zvolte **OK**.

   ![Šablona projektu webové aplikace ASP.NET Core v dialogovém okně Nový projekt v integrovaném vývojovém prostředí sady Visual Studio](media/csharp-aspnet-choose-template-name-razor-mycoreapp-file.png)

### <a name="add-a-workload-optional"></a>Přidat úlohu (volitelné)

Pokud nevidíte šablonu projektu **ASP.NET Core webové aplikace** , můžete ji získat přidáním úlohy **vývoje pro ASP.NET a web** . Tuto úlohu můžete přidat jedním ze dvou způsobů, v závislosti na tom, které aktualizace sady Visual Studio 2017 jsou nainstalovány na vašem počítači.

#### <a name="option-1-use-the-new-project-dialog-box"></a>Možnost 1: Použití dialogového okna Nový projekt

1. V levém podokně dialogového okna **Nový projekt** vyberte odkaz **otevřít instalační program pro Visual Studio** . (V závislosti na nastavení zobrazení může být potřeba stránku posunout, aby ji.)

   ![Vyberte odkaz otevřít Instalační program pro Visual Studio z dialogového okna Nový projekt.](../media/open-visual-studio-installer-mycoreapp.png)

1. Spustí se instalační program pro Visual Studio. Zvolte **vývoj pro ASP.NET a web** úlohy a klikněte na tlačítko **změnit**.

   ![Úlohy vývoje .NET Core pro různé platformy v Instalační program pro Visual Studio](../media/tutorial-aspnet-workload.png)

   (Může mít ukončit sadu Visual Studio, abyste mohli pokračovat v instalaci nové úlohy.)

#### <a name="option-2-use-the-tools-menu-bar"></a>Možnost 2: Použití panelu nabídek nástrojů

1. Zruší se dialogové okno **Nový projekt** . Pak na horním panelu nabídek zvolte **nástroje** > **získat nástroje a funkce**.

1. Spustí se instalační program pro Visual Studio. Zvolte **vývoj pro ASP.NET a web** úlohy a klikněte na tlačítko **změnit**.

   (Může mít ukončit sadu Visual Studio, abyste mohli pokračovat v instalaci nové úlohy.)

### <a name="add-a-project-template"></a>Přidání šablony projektu

1. V dialogovém okně **Nová webová aplikace ASP.NET Core** vyberte šablonu projektu **Webová aplikace** .

1. Ověřte, že se v horní rozevírací nabídce zobrazuje **ASP.NET Core 2,1** . Pak klikněte na **tlačítko OK**.

   ![Dialogové okno Nová webová aplikace ASP.NET Core](media/new-project-csharp-aspnet-razor-web-app.png)

   > [!NOTE]
   > Pokud v horní rozevírací nabídce nevidíte **ASP.NET Core 2,1** , ujistěte se, že používáte nejnovější verzi sady Visual Studio. Další informace o tom, jak aktualizovat instalaci, najdete na stránce o [aktualizaci sady Visual Studio na nejnovější verzi](../../install/update-visual-studio.md) .

::: moniker-end

::: moniker range="vs-2019"

1. V okně Start vyberte možnost **vytvořit nový projekt**.

   ![Zobrazit okno vytvořit nový projekt](../../get-started/media/vs-2019/create-new-project-dark-theme.png)

1. V okně **vytvořit nový projekt** zadejte nebo do vyhledávacího pole zadejte *ASP.NET* . Dále zvolte **C#** ze seznamu jazyk a v seznamu platforma zvolte možnost **Windows** .

   Po použití filtrů jazyků a platforem zvolte šablonu **ASP.NET Core webové aplikace** a klikněte na tlačítko **Další**.

   ![Zvolit C# šablonu pro ASP.NET Core webovou aplikaci](./media/vs-2019/csharp-create-new-project-search-aspnet-core-filtered.png)

   > [!NOTE]
   > Pokud nevidíte šablonu **ASP.NET Core webové aplikace** , můžete ji nainstalovat z okna **vytvořit nový projekt** . V části **nenajít, co hledáte?** klikněte na odkaz **instalovat další nástroje a funkce** .
   >
   > ![Odkaz pro instalaci dalších nástrojů a funkcí v okně vytvořit nový projekt v části nenajít, co hledáte?](../../get-started/media/vs-2019/not-finding-what-looking-for.png)
   >
   > Pak v Instalační program pro Visual Studio zvolte úlohu **vývoje ASP.NET a web** .
   >
   > ![Úlohy vývoje .NET Core pro různé platformy v Instalační program pro Visual Studio](../../get-started/media/aspnet-core-web-dev-workload.png)
   >
   > Potom klikněte na tlačítko **Upravit** v instalační program pro Visual Studio. Pokud budete vyzváni k uložení práce, udělejte to. V dalším kroku vyberte **pokračovat** a nainstalujte úlohu. Pak se vraťte ke kroku 2 v tomto postupu "[Vytvoření projektu](#create-a-project)".

1. V okně **Konfigurovat nový projekt** zadejte nebo zadejte *MyCoreApp* do pole **název projektu** . Pak zvolte **vytvořit**.

   ![v okně Konfigurovat nový projekt pojmenujte projekt ' MyCoreApp '.](./media/vs-2019/csharp-name-your-aspnet-mycoreapp-project.png)

1. V okně **vytvořit novou webovou aplikaci ASP.NET Core** ověřte, zda se v horní rozevírací nabídce zobrazí **ASP.NET Core 2,1** . Pak zvolte **Webová aplikace**, která obsahuje například Razor Pages. Pak vyberte **vytvořit**.

   ![Okno vytvořit novou ASP.NET Core webovou aplikaci](./media/vs-2019/csharp-create-aspnet-core-razor-pages-app.png)

   Visual Studio otevře nový projekt.

::: moniker-end

### <a name="about-your-solution"></a>O řešení

Toto řešení se řídí vzorem návrhu **stránky Razor** . Je jiný než vzor návrhu [MVC (Model-View-Controller)](/aspnet/core/tutorials/first-mvc-app/start-mvc?view=aspnetcore-2.1&tabs=aspnetcore2x) v tom, že je zjednodušený tak, aby zahrnoval model a kód kontroleru v rámci samotné stránky Razor.

## <a name="tour-your-solution"></a>Projděte si řešení

 1. Šablona projektu vytvoří řešení s jedním ASP.NET Core projektem s názvem _MyCoreApp_. Kliknutím na kartu **Průzkumník řešení** zobrazíte její obsah.

    ![ASP.NET Průzkumník řešení v aplikaci Visual Studio pro Razor Pages řešení s názvem MyCoreApp](media/csharp-aspnet-razor-solution-explorer-mycoreapp.png)

 1. Rozbalte složku **stránky** a poté rozbalte položku *o. cshtml*.

     ![Soubor About. cshtml v Průzkumník řešení v aplikaci Visual Studio](media/csharp-aspnet-razor-solution-explorer-aboutcshtml.png)

 1. Prohlédněte si soubor **About. cshtml** v editoru kódu.

     ![Zobrazení souboru About. cshtml v editoru kódu sady Visual Studio](media/csharp-aspnet-razor-aboutcshtml-mycoreapp-code.png)

 1. Vyberte soubor **About.cshtml.cs** .

     ![Zvolit soubor About.cshtml.cs v editoru kódu sady Visual Studio](media/csharp-aspnet-razor-solution-explorer-aboutcshtmlcs.png)

 1. Zobrazit soubor **About.cshtml.cs** v editoru kódu.

     ![Zobrazení souboru About. cshtml v editoru kódu sady Visual Studio](media/csharp-aspnet-razor-aboutcshtmlcs-mycoreapp-code.png)

 1. Projekt obsahuje složku **wwwroot** , která je kořenem vašeho webu. Rozbalte složku pro zobrazení jejího obsahu.

     ![Složka wwwroot v Průzkumník řešení v aplikaci Visual Studio](media/csharp-aspnet-razor-solution-explorer-wwwroot.png)

    Statický obsah&mdash;webu, jako jsou CSS, obrázky a knihovny&mdash;JavaScriptu, můžete umístit přímo do cest, kde je chcete.

 1. Projekt také obsahuje konfigurační soubory, které spravují webovou aplikaci za běhu. Výchozí [Konfigurace](/aspnet/core/fundamentals/configuration) aplikace je uložena v souboru *appSettings. JSON*. Tato nastavení však můžete přepsat pomocí *appSettings. Vývoj. JSON*. Rozbalením souboru **appSettings. JSON** zobrazíte **appSettings. Soubor Development. JSON** .

     ![Konfigurační soubory v Průzkumník řešení v aplikaci Visual Studio](media/csharp-aspnet-razor-solution-explorer-appsettingsjson.png)

## <a name="run-debug-and-make-changes"></a>Spuštění, ladění a provádění změn

1. Kliknutím na tlačítko **IIS Express** v integrovaném vývojovém prostředí sestavíte a spustíte aplikaci v režimu ladění. (Nebo stiskněte klávesu **F5**nebo zvolte **ladění** > **Spustit ladění** z řádku nabídek.)

     ![Výběr tlačítka IIS Express v aplikaci Visual Studio](media/csharp-aspnet-razor-iisexpress.png)

     > [!NOTE]
     > Pokud se zobrazí chybová zpráva s oznámením, že se **nelze připojit k webovému serveru ' IIS Express '** , ukončete aplikaci Visual Studio a pak ji otevřete pomocí možnosti **Spustit jako správce** v nabídce nebo v místní nabídce klikněte pravým tlačítkem myši. Spusťte aplikaci znovu.
     >
     > Může se také zobrazit zpráva s dotazem, zda chcete přijmout certifikát IIS SSL Express. Chcete-li zobrazit kód ve webovém prohlížeči, zvolte možnost **Ano**a zvolte možnost **Ano** , pokud se zobrazí zpráva s upozorněním na následné zabezpečení.

1. Visual Studio spustí okno prohlížeče. V řádku nabídek byste pak měli vidět stránky **Domů**, **o produktu**a **kontakt** . (Pokud to neuděláte, vyberte položku nabídky "hamburgerovou" "a zobrazte si je.)

    ![Vyberte položku nabídky "hamburgerovou" "z řádku nabídek ve vaší webové aplikaci.](media/csharp-aspnet-razor-browser-page.png)

1. V řádku nabídek vyberte **o** .

   ![Výběr informací o v panelu nabídek okna prohlížeče pro vaši aplikaci](media/csharp-aspnet-razor-browser-page-about-menu.png)

   Mimo jiné se stránka **About** v prohlížeči vykresluje text, který je nastaven v souboru *About. cshtml* .

   ![Zobrazení textu na stránce o produktu](media/csharp-aspnet-razor-browser-page-about.png)

1. Vraťte se do sady Visual Studio a stisknutím **SHIFT + F5** zastavte režim ladění. Tím se také zavře projekt v okně prohlížeče.

1. V aplikaci Visual Studio, vyberte **o. cshtml**. Pak odstraňte slovo _Další_ a místo na svém místě přidejte slovo _soubor a adresář_.

    ![Změna textu v souboru About. cshtml](media/csharp-aspnet-razor-aboutcshtml-mycoreapp-code-changed.png)

1. Vyberte **About.cshtml.cs**. Pak v horní části souboru `using` vyčistěte direktivy pomocí následujícího zástupce:

   Vyberte některou z šedých direktiv-out `using` a žárovku s [rychlými akcemi](../../ide/quick-actions.md) se zobrazí hned pod blikajícím kurzorem nebo na levém okraji. Zvolte žárovku a pak zvolte **odebrat nepotřebné**direktivy using.

   ![Odebrat nepotřebné direktivy using v souboru About.cshtml.cs](media/csharp-aspnet-razor-remove-unnecessary-usings.png)

     Visual Studio odstraní nepotřebné `using` direktivy ze souboru.

1. Dále v `OnGet()` metodě změňte tělo na následující kód:

     ```csharp
     public void OnGet()
     {
         string directory = Environment.CurrentDirectory;
     Message = String.Format("Your directory is {0}.", directory);
     }
    ```

1. Všimněte si, že v části **prostředí** a **řetězec**se zobrazí dvě podtržení vlnovkou. Podtržení vlnovkou se zobrazí, protože tyto typy nejsou v oboru.

   ![Chyby označené podtrženými vlnovkami v metodě OnGet](media/csharp-aspnet-razor-add-new-on-get-method.png)

    Otevřete panel nástrojů **Seznam chyb** pro zobrazení stejných chyb uvedených v seznamu. (Pokud panel nástrojů **Seznam chyb** nevidíte, vyberte v horním řádku nabídky možnost **Zobrazit** > **Seznam chyb** .)

   ![Seznam chyb v sadě Visual Studio](media/csharp-aspnet-razor-error-list.png)

1. Pojďme to opravit. V editoru kódu umístěte kurzor na buď řádek, který obsahuje chybu, a pak zvolte žárovku rychlé akce na levém okraji. Pak z rozevírací nabídky zvolte **použít systém;** k přidání této direktivy do horní části souboru a vyřešení chyb.

   ![Přidat direktivu using System;](media/csharp-aspnet-razor-add-usings.png)

1. Stisknutím **kombinace kláves CTRL +** +uložte změny a potom stisknutím klávesy **F5** otevřete projekt ve webovém prohlížeči.

1. V horní části webu vyberte možnost **o** zobrazení změn.

   ![Zobrazit aktualizované informace o stránce, která obsahuje změny, které jste provedli](media/csharp-aspnet-razor-browser-page-about-changed.png)

1. Zavřete webový prohlížeč, stisknutím klávesy **SHIFT**+**F5** zastavte režim ladění a poté zavřete aplikaci Visual Studio.

## <a name="quick-answers-faq"></a>Rychlé odpovědi – Nejčastější dotazy

Tady je rychlý přehled nejčastějších dotazů, které vám pomůžeme zvýraznit některé klíčové koncepty.

### <a name="what-is-c"></a>Co je C#to?

[C#](/dotnet/csharp/getting-started/introduction-to-the-csharp-language-and-the-net-framework)je typově bezpečný a objektově orientovaný programovací jazyk, který je navržený tak, aby byl robustní a snadno se učí.

### <a name="what-is-aspnet-core"></a>Co je ASP.NET Core?

ASP.NET Core je open source architektura pro různé platformy pro vytváření aplikací připojených k Internetu, jako jsou například webové aplikace a služby. Aplikace ASP.NET Core mohou běžet buď v rozhraní .NET Core, nebo v .NET Framework. Můžete vyvíjet a spouštět aplikace ASP.NET Core pro různé platformy v systémech Windows, Mac a Linux. ASP.NET Core je open source na [GitHubu](https://github.com/aspnet/home).

### <a name="what-is-visual-studio"></a>Co je Visual Studio?

Visual Studio je integrovaná vývojová sada nástrojů pro produktivitu pro vývojáře. Představte si ho jako program, který můžete použít k vytvoření programů a aplikací.

## <a name="next-steps"></a>Další postup

Blahopřejeme k dokončení tohoto kurzu! Doufáme, že jste se dozvěděli C#trochu o, ASP.NET Core a integrovaném vývojovém prostředí sady Visual Studio. Další informace o vytváření webové aplikace nebo webu pomocí C# a ASP.NET najdete v následujících kurzech:

> [!div class="nextstepaction"]
> [Vytvoření webové aplikace v Razor Pages s využitím ASP.NET Core](/aspnet/core/tutorials/razor-pages/?view=aspnetcore-2.1)

## <a name="see-also"></a>Viz také:

[Publikování webové aplikace do služby Azure App Service pomocí sady Visual Studio](../../deployment/quickstart-deploy-to-azure.md)
