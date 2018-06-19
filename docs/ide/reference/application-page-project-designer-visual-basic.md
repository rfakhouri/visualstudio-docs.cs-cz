---
title: Stránka Aplikace, návrhář projektu (Visual Basic)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vb.ProjectPropertiesApplicationWPF
- vb.ProjectPropertiesApplication
helpviewer_keywords:
- Project Designer, Application page
- Application page in Project Designer
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 62cbae6115b8268adbb1e2f9d6c27df8bf94a28b
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31954566"
---
# <a name="application-page-project-designer-visual-basic"></a>Stránka Aplikace, návrhář projektu (Visual Basic)

Použití **aplikace** stránky v Návrháři projektu zadat nastavení aplikace a vlastnosti projektu.

Pro přístup k **aplikace** vyberte uzel projektu (ne **řešení** uzel) v **Průzkumníku řešení**. Zvolte **projektu** > **vlastnosti** v řádku nabídek. Jakmile se zobrazí v Návrháři projektu, vyberte **aplikace** kartě.

[!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]

## <a name="general-application-settings"></a>Obecné nastavení aplikace

Následující možnosti vám umožňují konfigurovat obecné nastavení pro aplikaci.

### <a name="assembly-name"></a>Název sestavení

Určuje název výstupního souboru, který bude obsahovat manifest sestavení. Pokud změníte tuto vlastnost **název výstupu** také změny vlastností. Můžete také zadat název souboru výstupního souboru z příkazového řádku pomocí [/out (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/out) přepínače kompilátoru. Informace o tom, jak tato vlastnost přístup prostřednictvím kódu programu najdete v tématu <xref:VSLangProj.ProjectProperties.AssemblyName%2A>.

### <a name="root-namespace"></a>Kořenový obor názvů

Určuje základní obor názvů pro všechny soubory v projektu. Například pokud nastavíte **kořenové Namespace** k `Project1` a máte `Class1` mimo obor názvů v kódu, jeho obor názvů by byl `Project1.Class1`. Pokud máte `Class2` v oboru názvů `Order` v kódu, jeho obor názvů by byl `Project1.Order.Class2`.

Pokud zrušíte výběr **Namespace kořenové**, můžete zadat obor názvů strukturu projektu v kódu.

> [!NOTE]
> Pokud používáte Global – klíčové slovo v [příkaz Namespace](/dotnet/visual-basic/language-reference/statements/namespace-statement), můžete definovat oboru názvů z kořenového oboru názvů vašeho projektu. Pokud zrušíte výběr **kořenové Namespace**, `Global` stane nejvyšší úrovně oboru názvů, který odebírá potřebu, `Global` – klíčové slovo v `Namespace` příkaz. Další informace najdete v tématu "Globální – klíčové slovo v Namespace příkazy" v [obory názvů v jazyce Visual Basic](/dotnet/visual-basic/programming-guide/program-structure/namespaces).

Informace o tom, jak vytvořit obory názvů v kódu najdete v tématu [příkaz Namespace](/dotnet/visual-basic/language-reference/statements/namespace-statement).

Další informace o vlastnosti kořenový obor názvů najdete v tématu [/RootNamespace](/dotnet/visual-basic/reference/command-line-compiler/rootnamespace).

Informace o tom, jak tato vlastnost přístup prostřednictvím kódu programu najdete v tématu <xref:VSLangProj.ProjectProperties.RootNamespace%2A>.

### <a name="target-framework-all-configurations"></a>Cílová architektura (všechny konfigurace)

Určuje verzi rozhraní .NET Framework, cíle pro aplikace. Tato možnost může mít různé hodnoty v závislosti na tom, které jsou v počítači nainstalována verze rozhraní .NET Framework.

Výchozí hodnota odpovídá cílové rozhraní, které jste zadali v **nový projekt** dialogové okno.

> [!NOTE]
> Požadované balíčky, které jsou uvedeny v [dialogové okno požadavky](../../ide/reference/prerequisites-dialog-box.md) jsou nastaveny automaticky při otevření dialogu pro první. Pokud později změníte cílový framework projektu na, je nutné zadat požadavky ručně tak, aby odpovídala nové cílové rozhraní.

Další informace najdete v tématu [postupy: cílení na verzi rozhraní .NET Framework](../../ide/how-to-target-a-version-of-the-dotnet-framework.md) a [přehled cílení na více Visual Studio](../../ide/visual-studio-multi-targeting-overview.md).

### <a name="application-type"></a>Typ aplikace

Určuje typ aplikace k sestavení. Pro aplikace pro Windows 8.x, můžete zadat **aplikace pro Windows Store**, **knihovny tříd**, nebo **souboru WinMD**. Pro většinu jinými typy aplikací, můžete zadat **aplikace Windows**, **konzolové aplikace**, **knihovny tříd**, **služba systému Windows**, nebo **webové ovládací prvek knihovna**.

Pro projekt webové aplikace je nutné zadat **knihovny tříd**.

Pokud zadáte **souboru WinMD** možnost typy je možné promítnout do jakékoli programovací jazyk prostředí Windows Runtime. Ve výstupu projektu jako soubor WinMD balení, může kód aplikace v různých jazycích a mají kód spolupracovat, jako kdyby byl napsán všechno ve stejném jazyce. Můžete použít **souboru WinMD** možnost pro řešení, která cílí na prostředí Windows Runtime knihoven, včetně [!INCLUDE[win8_appname_long](../../debugger/includes/win8_appname_long_md.md)] aplikace. Další informace najdete v tématu [vytváření součásti systému Windows Runtime v C# a Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

> [!NOTE]
> Prostředí Windows Runtime můžete typy projektů, aby se zobrazily jako nativní objekty v kteroukoli jazyk používá je. Například JavaScript aplikace, které pracují se prostředí Windows Runtime použít jako sadu objektů jazyka JavaScript a aplikací v C# v knihovně jako kolekce objektů .NET. Ve výstupu projektu jako soubor WinMD balení, můžete využít výhod stejné technologie, která používá prostředí Windows Runtime.

Další informace o **typ aplikace** vlastnost, najdete v části [/Target (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/target). Informace o tom, jak tuto vlastnost přístup prostřednictvím kódu programu najdete v tématu <xref:VSLangProj.ProjectProperties.OutputType%2A>.

### <a name="icon"></a>Ikona

Nastaví soubor .ico, který chcete použít jako ikona programu. Vyberte  **\<Procházet... >** k vyhledání existujícího obrázku. V tématu [/win32icon](/dotnet/visual-basic/reference/command-line-compiler/win32icon) (nebo [/win32icon (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/win32icon-compiler-option)) Další informace. Přístup prostřednictvím kódu programu naleznete v tématu <xref:VSLangProj.ProjectProperties.ApplicationIcon%2A>.

### <a name="startup-form--startup-object--startup-uri"></a>Formulář spuštění nebo spuštění objektu nebo identifikátor URI spuštění

Určuje aplikace spuštění formuláře nebo vstupní bod.

Pokud **Povolit aplikační rozhraní** je vybraná (výchozí), je s názvem Tento seznam **formulář spuštění** a zobrazuje pouze forms protože rozhraní podporuje pouze spouštěcí formuláře, nejsou objekty.

Pokud je projekt aplikace WPF prohlížeče, je tento seznam s názvem **spuštění URI**, a výchozí hodnota je **Page1.xaml**. **Spuštění URI** seznamu umožňuje určit prostředek uživatelské rozhraní (XAML element), který aplikace zobrazí při spuštění aplikace. Další informace naleznete v tématu <xref:System.Windows.Application.StartupUri%2A>.

Pokud **Povolit aplikační rozhraní** není zaškrtnuto, tento seznam bude **spouštěcí objekt** a zobrazuje formuláře a třídy nebo moduly s `Sub Main`.

**Spouštěcí objekt** definuje vstupní bod, která se má volat při načtení aplikace. Obvykle to je nastaven na hodnotu hlavního formuláře v aplikaci nebo na `Sub Main` postup, který se má spustit při spuštění aplikace. Protože knihovny tříd nemají vstupního bodu, jejich jedinou možností pro tuto vlastnost je **(None)**. Další informace najdete v tématu [/main](/dotnet/visual-basic/reference/command-line-compiler/main). Přístup prostřednictvím kódu programu naleznete v tématu <xref:VSLangProj.ProjectProperties.StartupObject%2A>.

### <a name="assembly-information"></a>Informace o sestavení

Kliknutím na toto tlačítko Zobrazit [dialogové okno informace o sestavení](../../ide/reference/assembly-information-dialog-box.md).

### <a name="enable-application-framework"></a>Povolit aplikační rozhraní

Určuje, zda bude projekt používat rozhraní. Tato možnost ovlivní možnosti dostupné v **formulář spuštění**/**spouštěcí objekt**.

Pokud je toto políčko zaškrtnuto, vaše aplikace používá standardní `Sub Main`. Výběrem tohoto zaškrtávacího políčka povoluje funkce v **vlastnosti framework aplikace Windows** části a také vyžaduje, abyste vyberte formulář spuštění.

Pokud je toto políčko zaškrtnuté, vaše aplikace používá vlastní `Sub Main` ve stanoveném **formulář spuštění**. V takovém případě můžete zadat buď objekt spuštění (vlastní `Sub Main` v metody nebo třída) nebo formulář. Navíc na možnosti v **vlastnosti framework aplikace Windows** části k dispozici.

### <a name="view-windows-settings"></a>Zobrazení nastavení systému Windows

Kliknutím na toto tlačítko Generovat a otevřete soubor app.manifest. Visual Studio použije tento soubor pro generování manifestu dat pro aplikaci. Potom sadu řízení uživatelských účtů požadovanou úroveň provádění změnou `<requestedExecutionLevel>` značky v app.manifest následujícím způsobem:

`<requestedExecutionLevel level="asInvoker" />`

ClickOnce funguje s úrovní `asInvoker` nebo v režimu virtualizované (bez generování manifestu). K určení virtualizované režimu, odeberte z app.manifest celý značky.

Další informace o generování manifestu najdete v tématu [ClickOnce – nasazení v systému Windows Vista](../../deployment/clickonce-deployment-on-windows-vista.md).

## <a name="windows-application-framework-properties"></a>Vlastnosti Framework aplikace Windows

Následující nastavení jsou k dispozici v **vlastnosti framework aplikace Windows** části. Tyto možnosti jsou dostupné pouze v případě **Povolit aplikační rozhraní** je zaškrtnuté políčko. Popisuje části následující touto **vlastnosti framework aplikace Windows** nastavení pro aplikace Windows Presentation Foundation (WPF).

### <a name="enable-xp-visual-styles"></a>Povolit vizuální styly XP

Povolí nebo zakáže vizuální styly Windows XP, také známé jako *motivy systému Windows XP*. Vizuální styly Windows XP povolit, například ovládací prvky s zaoblenými hranami a dynamické barvy. Výchozí hodnota je povoleno.

### <a name="make-single-instance-application"></a>Ujistěte se, jedna instance aplikace

Zaškrtněte toto políčko, pokud chcete zabránit uživatelům ve spouštění více instancí aplikace. Výchozí nastavení je toto políčko *vymazán*, což umožňuje několik instancí aplikace ke spuštění. Další informace najdete v tématu <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> událostí.

### <a name="save-mysettings-on-shutdown"></a>Uložit My.Settings na vypnutí

Výběrem tohoto zaškrtávacího políčka určete, že aplikace `My.Settings` nastavení se ukládají, když uživatelé vypnutí počítačů. Ve výchozím nastavení zapnutá. Pokud tato možnost je zakázaná, můžete uložit nastavení aplikace ručně voláním `My.Settings.Save`.

### <a name="authentication-mode"></a>Režim ověřování

Vyberte **Windows** (výchozí) k určení použití ověřování systému Windows k identifikaci aktuálně přihlášeného uživatele. Tyto informace v době běhu můžete načíst pomocí `My.User` objektu. Vyberte **definované aplikací** Pokud zadáte vlastní kód pro ověření uživatele místo použití výchozí metody ověřování systému Windows.

### <a name="shutdown-mode"></a>Vypnutí režimu

Vyberte **při zavření formuláře spuštění** (výchozí) k určení, že aplikace ukončení formuláře nastavena jako spouštěcí zavře, i v případě, že jsou otevřené jiné formuláře. Vyberte **při poslední formuláře zavře** k určení, který ukončení aplikace při zavření posledního formuláře nebo když `My.Application.Exit` nebo `End` zavolá se příkaz explicitně.

Vyberte **na explicitní vypnutí** k určení, že aplikaci ukončit, i když explicitně volání `Shutdown`.

Vyberte **na poslední okno zavřete** k určení, který ukončení aplikace při poslední okno zavřete, nebo když explicitně volání `Shutdown`. Toto je výchozí nastavení.

Vyberte **na hlavní okno zavřete** k určení, že aplikace ukončete hlavní okno zavře, nebo když explicitně volání `Shutdown`.

### <a name="splash-screen"></a>Úvodní obrazovka

Vyberte formulář, který chcete použít jako úvodní obrazovka. Je musíte vytvořit úvodní obrazovka pomocí formuláře nebo šablony. Výchozí hodnota je **(None)**.

### <a name="view-application-events"></a>Zobrazit události aplikace

Kliknutím na toto tlačítko Zobrazit soubor kódu události, ve kterém můžete zapsat události pro události aplikace framework `Startup`, `Shutdown`, `UnhandledException`, `StartupNextInstance` a `NetworkAvailabilityChanged`. Můžete také přepsat metod framework určité aplikace. Například můžete změnit chování zobrazení úvodní obrazovka přepsáním `OnInitialize`.

## <a name="windows-application-framework-properties-for-windows-presentation-foundation-wpf-applications"></a>Vlastnosti Framework aplikace Windows Presentation Foundation (WPF) pro aplikace pro Windows

Následující nastavení jsou k dispozici v **vlastnosti framework aplikace Windows** části po projekt aplikace Windows Presentation Foundation. Tyto možnosti jsou dostupné pouze v případě **Povolit aplikační rozhraní** je zaškrtnuté políčko. Možnosti uvedené v této tabulce jsou k dispozici pouze pro aplikace WPF nebo Prohlížečových aplikací. Nejsou k dispozici pro uživatelský ovládací prvek WPF nebo vlastní ovládací prvek knihovny.

### <a name="shutdown-mode"></a>Vypnutí režimu

Tato vlastnost se vztahuje pouze na aplikace Windows Presentation Foundation.

Vyberte **na explicitní vypnutí** k určení, že aplikaci ukončit, i když explicitně volání <xref:System.Windows.Application.Shutdown%2A>.

Vyberte **na poslední okno zavřete** k určení, který ukončení aplikace při poslední okno zavřete, nebo když explicitně volání <xref:System.Windows.Application.Shutdown%2A>. Toto je výchozí nastavení.

Vyberte **na hlavní okno zavřete** k určení, že aplikace ukončete hlavní okno zavře, nebo když explicitně volání <xref:System.Windows.Application.Shutdown%2A>.

Další informace o použití tohoto nastavení najdete v tématu <xref:System.Windows.Application.Shutdown%2A>

### <a name="edit-xaml"></a>Upravit XAML

Kliknutím na toto tlačítko otevřete a upravte soubor definice aplikace (Application.xaml) v editoru XAML. Při kliknutí na toto tlačítko otevře Application.xaml v uzlu definice aplikace. Možná bude muset upravit tento soubor provádět určité operace, jako je například definice prostředků. Pokud neexistuje definiční soubor aplikace, Návrhář projektu vytvoří.

### <a name="view-application-events"></a>Zobrazit události aplikace

Kliknutím na toto tlačítko Zobrazit `Application` soubor částečné třídy (Application.xaml.vb) v editoru kódu. Pokud soubor neexistuje, vytvoří Návrhář projektu s názvem příslušné třídy a obor názvů.

<xref:System.Windows.Application> Objekt vyvolává události, když dojde k určité změny stavu aplikace (například na spuštění aplikace nebo ukončení). Úplný seznam událostí, které tato třída poskytuje, naleznete v části <xref:System.Windows.Application>. Tyto události jsou zpracovávány v části kódu uživatele `Application` třídu.