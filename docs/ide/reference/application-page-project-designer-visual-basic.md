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
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/11/2018
ms.locfileid: "38800730"
---
# <a name="application-page-project-designer-visual-basic"></a>Stránka Aplikace, návrhář projektu (Visual Basic)

Použití **aplikace** stránky Návrháře projektu k určení nastavení aplikace a vlastnosti projektu.

Pro přístup k **aplikace** zvolte uzel projektu (ne **řešení** uzlu) v **Průzkumníka řešení**. Klikněte na tlačítko **projektu** > **vlastnosti** na řádku nabídek. Jakmile se zobrazí Návrhář projektu, vyberte **aplikace** kartu.

[!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]

## <a name="general-application-settings"></a>Obecné nastavení aplikace

Tyto možnosti umožňují nakonfigurovat obecná nastavení pro aplikaci.

### <a name="assembly-name"></a>Název sestavení

Určuje název výstupního souboru, který bude obsahovat manifest sestavení. Pokud změníte tuto vlastnost **název výstupního** vlastnost také změní. Můžete také zadat název výstupního souboru z příkazového řádku s použitím [/out (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/out) přepínač kompilátoru. Informace o tom, jak programově přístup k této vlastnosti naleznete v tématu <xref:VSLangProj.ProjectProperties.AssemblyName%2A>.

### <a name="root-namespace"></a>Kořenový obor názvů

Určuje základní obor názvů pro všechny soubory v projektu. Například, pokud jste nastavili **kořenové Namespace** k `Project1` a máte `Class1` mimo libovolný obor názvů ve vašem kódu, jeho obor názvů by `Project1.Class1`. Pokud máte `Class2` v oboru názvů `Order` v kódu, jeho obor názvů by `Project1.Order.Class2`.

Pokud zrušíte výběr **kořenové Namespace**, obor názvů strukturu projektu můžete zadat v kódu.

> [!NOTE]
> Pokud používáte Global – klíčové slovo v [příkaz Namespace](/dotnet/visual-basic/language-reference/statements/namespace-statement), můžete definovat obor názvů mimo kořenový obor názvů vašeho projektu. Pokud zrušíte výběr **kořenové Namespace**, `Global` stane oboru nejvyšší úrovně, která eliminuje potřebu `Global` – klíčové slovo v `Namespace` příkaz. Další informace najdete v tématu "Globální – klíčové slovo v Namespace příkazy" v [obory názvů v jazyce Visual Basic](/dotnet/visual-basic/programming-guide/program-structure/namespaces).

Informace o tom, jak vytvořit obory názvů ve vašem kódu, naleznete v tématu [příkaz Namespace](/dotnet/visual-basic/language-reference/statements/namespace-statement).

Další informace o vlastnosti kořenový obor názvů najdete v tématu [/RootNamespace](/dotnet/visual-basic/reference/command-line-compiler/rootnamespace).

Informace o tom, jak programově přístup k této vlastnosti naleznete v tématu <xref:VSLangProj.ProjectProperties.RootNamespace%2A>.

### <a name="target-framework-all-configurations"></a>Cílová architektura (všechny konfigurace)

Určuje verzi rozhraní .NET Framework, který aplikace cílí. Tato možnost může mít různé hodnoty v závislosti na nainstalovaných verzí rozhraní .NET Framework v počítači.

Výchozí hodnota se shoduje s cílovou architekturu, která jste zadali v **nový projekt** dialogové okno.

> [!NOTE]
> Požadované balíčky, které jsou uvedeny v [dialogové okno požadavky](../../ide/reference/prerequisites-dialog-box.md) se nastaví automaticky, když otevřete dialogové okno poprvé. Pokud později změníte cílový rámec projektu, je nutné zadat předpoklady ručně, aby odpovídaly novému cílovému rozhraní.

Další informace najdete v tématu [postupy: cílení na určitou verzi rozhraní .NET Framework](../../ide/how-to-target-a-version-of-the-dotnet-framework.md) a [Visual Studio přehled multiplatformního zacílení](../../ide/visual-studio-multi-targeting-overview.md).

### <a name="application-type"></a>Typ aplikace

Určuje typ aplikace k sestavení. Pro aplikace Windows 8.x, můžete zadat **aplikace Windows Store**, **knihovny tříd**, nebo **soubor WinMD**. Pro většinu ostatních typů aplikací, můžete zadat **aplikace Windows**, **konzolovou aplikaci**, **knihovny tříd**, **Windows Service**, nebo **Knihovna webových prvků**.

Pro projekt webové aplikace, je nutné zadat **knihovny tříd**.

Pokud zadáte **soubor WinMD** možnost, typy je možné promítnout do jakékoli Windows Runtime programovací jazyk. Balení výstup projektu jako soubor WinMD, může kód aplikace v několika jazycích a spolupracovat, jako kdyby jste napsali kód vše ve stejném jazyce. Můžete použít **soubor WinMD** možnost pro řešení, které se zaměřují na modul Windows Runtime knihovny, včetně [!INCLUDE[win8_appname_long](../../debugger/includes/win8_appname_long_md.md)] aplikace. Další informace najdete v tématu [vytváření komponent Windows Runtime v jazyce C# a Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

> [!NOTE]
> Modul Windows Runtime můžete promítnout typy tak, aby byly zobrazeny jako nativních objektů v libovolný preferovaný jazyk je využívá. Například použít jako sadu JavaScript – objekty jazyka JavaScript aplikace, které spolupracují s modulem Windows Runtime a aplikace C# použít knihovnu jako kolekce objektů .NET. Díky balení výstup projektu jako soubor WinMD, můžete využívat stejné technologie, která používá prostředí Windows Runtime.

Další informace o **typ aplikace** vlastnost, naleznete v tématu [/Target (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/target). Informace o tom, jak programově přístup k této vlastnosti naleznete v tématu <xref:VSLangProj.ProjectProperties.OutputType%2A>.

### <a name="icon"></a>Ikona

Nastavuje soubor .ico, který chcete použít jako ikona programu. Vyberte  **\<Procházet... >** k vyhledání existujícího obrázku. Zobrazit [/win32icon](/dotnet/visual-basic/reference/command-line-compiler/win32icon) (nebo [/win32icon (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/win32icon-compiler-option)) pro další informace. Programový přístup k této vlastnosti, najdete v článku <xref:VSLangProj.ProjectProperties.ApplicationIcon%2A>.

### <a name="startup-form--startup-object--startup-uri"></a>Úvodní formulář nebo spouštěcí objekt / spouštěcí identifikátor URI

Určuje formuláře nebo vstupní bod při spuštění aplikace.

Pokud **Povolit aplikační framework** je vybrán tento seznam (výchozí), má název **úvodní formulář** a zobrazuje pouze formuláře rozhraní framework aplikace podporuje pouze formuláře při spuštění nejsou objekty.

Pokud je projekt aplikace WPF pro prohlížeč, je tento seznam s názvem **spouštěcí identifikátor URI**, a výchozí hodnota je **Page1.xaml**. **Spouštěcí identifikátor URI** seznamu vám umožní zadat prostředek rozhraní uživatele (a XAML element), které aplikace se zobrazí při spuštění aplikace. Další informace naleznete v tématu <xref:System.Windows.Application.StartupUri%2A>.

Pokud **Povolit aplikační framework** není zaškrtnuto, tento seznam bude **spouštěcí objekt** a zobrazuje formuláře a tříd nebo moduly s `Sub Main`.

**Spouštěcí objekt** definuje vstupní bod, který bude volán při načtení aplikace. Obecně je nastavené na hodnotu hlavního formuláře v aplikaci nebo na `Sub Main` proceduru, která se má spustit při spuštění aplikace. Vzhledem k tomu, že nemá vstupní bod knihovny tříd, jejich jedinou možností pro tuto vlastnost je **(žádný)**. Další informace najdete v tématu [/main](/dotnet/visual-basic/reference/command-line-compiler/main). Programový přístup k této vlastnosti, najdete v článku <xref:VSLangProj.ProjectProperties.StartupObject%2A>.

### <a name="assembly-information"></a>Informace o sestavení

Kliknutím na toto tlačítko Zobrazit [dialogové okno informace o sestavení](../../ide/reference/assembly-information-dialog-box.md).

### <a name="enable-application-framework"></a>Povolit aplikační framework

Určuje, zda projekt bude používat aplikační platformu. Nastavení této možnosti má vliv na možnosti dostupné v **úvodní formulář**/**spouštěcí objekt**.

Pokud je toto políčko zaškrtnuto, vaše aplikace používá standardní `Sub Main`. Výběrem tohoto zaškrtávacího políčka povoluje funkce v **vlastnosti rozhraní framework aplikace Windows** části a také vyžaduje, abyste vyberte formulář spuštění.

Pokud je toto políčko zaškrtnuté, vaše aplikace používá vlastní `Sub Main` , který jste zadali v **úvodní formulář**. V tomto případě můžete zadat buď objekt při spuštění (vlastní `Sub Main` v metodě nebo třídě) nebo formuláře. Navíc možnosti **vlastnosti rozhraní framework aplikace Windows** oddílu k dispozici.

### <a name="view-windows-settings"></a>Zobrazit nastavení Windows

Kliknutím na toto tlačítko Generovat a otevřete soubor app.manifest. Visual Studio tento soubor používá ke generování manifestu data aplikace. Pak sadu UAC požadovaná úroveň spuštění úpravou `<requestedExecutionLevel>` značku app.manifest následujícím způsobem:

`<requestedExecutionLevel level="asInvoker" />`

ClickOnce – funguje s úrovní `asInvoker` nebo ve virtualizovaných režimu (bez generování manifestu). Pro určení virtualizované režimu, odeberte celou z app.manifest.

Další informace o generování manifestu naleznete v tématu [nasazení ClickOnce v systému Windows Vista](../../deployment/clickonce-deployment-on-windows-vista.md).

## <a name="windows-application-framework-properties"></a>Vlastnosti rozhraní Framework aplikace Windows

Následující nastavení jsou dostupná **vlastnosti rozhraní framework aplikace Windows** oddílu. Tyto možnosti jsou dostupné pouze tehdy, pokud **Povolit aplikační framework** je zaškrtnuto políčko. Popisuje části následující za touto možností **vlastnosti rozhraní framework aplikace Windows** nastavení pro aplikace Windows Presentation Foundation (WPF).

### <a name="enable-xp-visual-styles"></a>Povolení vizuálních stylů XP

Povolí nebo zakáže vizuálních stylů Windows XP, označované také jako *Windows XP motivy*. Vizuální styly Windows XP povolit, například ovládací prvky s oblých rohů a dynamické barvy. Výchozí hodnota je povolená.

### <a name="make-single-instance-application"></a>Ujistěte se, jedna instance aplikace

Zaškrtněte toto políčko, pokud chcete zabránit uživatelům ve spouštění více instancí aplikace. Výchozí nastavení je toto políčko *vymazat*, což umožňuje více instancí aplikace ke spuštění. Další informace naleznete v události <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>.

### <a name="save-mysettings-on-shutdown"></a>Při vypnutí ukládání My.Settings

Zaškrtněte toto políčko, chcete-li určit, že aplikace `My.Settings` nastavení se ukládají, když uživatelé vypnutí počítačů. Ve výchozím nastavení zapnutá. Pokud tato možnost je zakázaná, můžete uložit nastavení aplikace ručně voláním `My.Settings.Save`.

### <a name="authentication-mode"></a>Režim ověřování

Vyberte **Windows** (výchozí) k určení použití ověřování Windows k identifikaci aktuálně přihlášeného uživatele. Tyto informace za běhu můžete načíst pomocí `My.User` objektu. Vyberte **definovaného aplikací** budete poskytovat vlastní kód pro ověření uživatelům, tedy ne pomocí výchozí metody ověřování Windows.

### <a name="shutdown-mode"></a>Ukončení režimu

Vyberte **když se zavře úvodní formulář** (výchozí) k určení, že ukončení aplikace, když se formulář nastaven jako spouštěcí zavře, i v případě, že jsou otevřené jiné formuláře. Vyberte **při poslední formuláře zavře** k určení, že aplikace ukončena při zavření posledního formuláře, nebo když `My.Application.Exit` nebo `End` příkaz je explicitně volána.

Vyberte **při jednoznačném vypnutí** k určení, že aplikaci ukončit, pokud explicitně volat `Shutdown`.

Vyberte **na poslední okno zavřete** k určení, že aplikace ukončena při zavření posledního okna, nebo když explicitně volat `Shutdown`. Toto je výchozí nastavení.

Vyberte **na hlavní okno zavřete** k určení, že aplikace ukončena, když hlavní okno se zavře, nebo když explicitně volat `Shutdown`.

### <a name="splash-screen"></a>Úvodní obrazovka

Vyberte formulář, který chcete použít jako úvodní obrazovka. Musí mít dříve vytvoříte úvodní obrazovky pomocí formuláře nebo šablony. Výchozí hodnota je **(žádný)**.

### <a name="view-application-events"></a>Zobrazit události aplikace

Kliknutím na toto tlačítko zobrazíte kód souboru události, ve kterém můžete zapisovat události pro události rozhraní framework aplikace `Startup`, `Shutdown`, `UnhandledException`, `StartupNextInstance` a `NetworkAvailabilityChanged`. Můžete také přepsat metody rozhraní framework určitých aplikací. Například můžete změnit chování zobrazení na úvodní obrazovce přepsáním `OnInitialize`.

## <a name="windows-application-framework-properties-for-windows-presentation-foundation-wpf-applications"></a>Vlastnosti rozhraní Framework aplikace Windows pro aplikace Windows Presentation Foundation (WPF)

Následující nastavení jsou dostupná **vlastnosti rozhraní framework aplikace Windows** části, pokud je projekt aplikace Windows Presentation Foundation. Tyto možnosti jsou dostupné pouze tehdy, pokud **Povolit aplikační framework** je zaškrtnuto políčko. Možnosti uvedené v této tabulce jsou k dispozici pouze pro aplikace WPF nebo aplikace prohlížeče WPF. Nejsou k dispozici pro uživatelský ovládací prvek WPF nebo vlastní ovládací prvek knihovny.

### <a name="shutdown-mode"></a>Ukončení režimu

Tato vlastnost platí jenom pro aplikace Windows Presentation Foundation.

Vyberte **při jednoznačném vypnutí** k určení, že aplikaci ukončit, pokud explicitně volat <xref:System.Windows.Application.Shutdown%2A>.

Vyberte **na poslední okno zavřete** k určení, že aplikace ukončena při zavření posledního okna, nebo když explicitně volat <xref:System.Windows.Application.Shutdown%2A>. Toto je výchozí nastavení.

Vyberte **na hlavní okno zavřete** k určení, že aplikace ukončena, když hlavní okno se zavře, nebo když explicitně volat <xref:System.Windows.Application.Shutdown%2A>.

Další informace o použití tohoto nastavení najdete v tématu <xref:System.Windows.Application.Shutdown%2A>

### <a name="edit-xaml"></a>Upravit XAML

Kliknutím na toto tlačítko otevřete a upravte soubor definice aplikace (Application.xaml) v editoru XAML. Po kliknutí na toto tlačítko otevře Application.xaml v definici uzlu aplikace. Budete muset upravit tento soubor k provádění určitých úloh, jako je například definování prostředků. Pokud soubor definice aplikace buď neexistuje, Návrhář projektu ho vytvoří.

### <a name="view-application-events"></a>Zobrazit události aplikace

Kliknutím na toto tlačítko Zobrazit `Application` soubor částečné třídy (Application.xaml.vb) v editoru kódu. Pokud soubor neexistuje, vytvoří Návrháře projektu s názvem příslušné třídy a oboru názvů.

<xref:System.Windows.Application> Objekt vyvolává události, když dojde k určitým změnám stavu aplikace (třeba na spuštění aplikace nebo ukončení). Úplný seznam událostí, které tato třída zveřejňuje najdete v tématu <xref:System.Windows.Application>. Tyto události jsou zpracovány v oddíle kód uživatele `Application` částečné třídy.