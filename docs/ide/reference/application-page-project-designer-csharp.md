---
title: Stránka Aplikace, návrhář projektu (C#)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- cs.ProjectPropertiesApplicationWPF
- cs.ProjectPropertiesApplication
helpviewer_keywords:
- Project Designer, Application page
- Application page in Project Designer
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 0df628a83bf88acb4f73d7bb47269458bd34ace9
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/11/2018
ms.locfileid: "38808882"
---
# <a name="application-page-project-designer-c"></a>Stránka Aplikace, návrhář projektu (C#)

Použití **aplikace** stránku **Návrháře projektu** k určení nastavení aplikace a vlastnosti projektu.

Pro přístup k **aplikace** zvolte uzel projektu (ne **řešení** uzlu) v **Průzkumníka řešení**. Klikněte na tlačítko **projektu**, **vlastnosti** na řádku nabídek. Jakmile se zobrazí Návrhář projektu, klikněte na tlačítko **aplikace** kartu.

[!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]

## <a name="general-application-settings"></a>Obecné nastavení aplikace
 Tyto možnosti umožňují nakonfigurovat obecná nastavení pro aplikaci.

 **Název sestavení** Určuje název výstupního souboru, který bude obsahovat manifest sestavení. Změna této vlastnosti se také změní **název výstupního** vlastnost. Tuto změnu z příkazového řádku můžete také provést pomocí [/out (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/out-compiler-option). Programový přístup k této vlastnosti, najdete v článku <xref:VSLangProj.ProjectProperties.AssemblyName%2A>.

 **Výchozí obor názvů** určuje základní obor názvů pro soubory přidané do projektu.

 Zobrazit [obor názvů](/dotnet/csharp/language-reference/keywords/namespace) pro další informace o vytváření oborů názvů ve vašem kódu.

 Programový přístup k této vlastnosti, najdete v článku <xref:VSLangProj.ProjectProperties.RootNamespace%2A>.

 **Cílové rozhraní Framework** Určuje verzi rozhraní .NET Framework, který aplikace cílí. Tato možnost může mít různé hodnoty v závislosti na nainstalovaných verzí rozhraní .NET Framework v počítači.

 Výchozí hodnota je stejná jako Cílová architektura, kterou jste vybrali v **nový projekt** dialogové okno.

> [!NOTE]
> Požadované balíčky uvedené v [dialogové okno požadavky](../../ide/reference/prerequisites-dialog-box.md) se nastaví automaticky při prvním otevření dialogu. Pokud později změníte cílový rámec projektu, budete muset vybrat předpoklady ručně, aby odpovídaly novému cílovému rozhraní.


 Další informace najdete v tématu [postupy: cílení na určitou verzi rozhraní .NET Framework](../../ide/how-to-target-a-version-of-the-dotnet-framework.md) a [Visual Studio přehled multiplatformního zacílení](../../ide/visual-studio-multi-targeting-overview.md).

 **Typ aplikace** Určuje typ aplikace k sestavení. Pro aplikace Windows 8.x, můžete zadat **aplikace Windows Store**, **knihovny tříd**, nebo **soubor WinMD**. Pro většinu ostatních typů aplikací, můžete zadat **aplikace Windows**, **konzolovou aplikaci**, **knihovny tříd**, **Windows Service**, nebo **Knihovna webových prvků**.

 Pro projekt webové aplikace, je nutné zadat **knihovny tříd**.

 Pokud zadáte **soubor WinMD** možnost, typy je možné promítnout do jakékoli Windows Runtime programovací jazyk. Balení výstup projektu jako soubor WinMD, může kód aplikace v několika jazycích a spolupracovat, jako kdyby jste napsali kód vše ve stejném jazyce. Můžete určit tuto možnost pro řešení, které se zaměřují na modul Windows Runtime knihovny, včetně [!INCLUDE[win8_appname_long](../../debugger/includes/win8_appname_long_md.md)] aplikace. Další informace najdete v tématu [vytváření komponent Windows Runtime v jazyce C# a Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

> [!NOTE]
> Modul Windows Runtime můžete promítnout typy tak, aby byly zobrazeny jako nativních objektů v libovolný preferovaný jazyk je využívá. Například použít jako sadu JavaScript – objekty jazyka JavaScript aplikace, které spolupracují s modulem Windows Runtime a aplikace C# použít knihovnu jako kolekce objektů .NET. Díky balení výstup projektu jako soubor WinMD, můžete využívat stejné technologie, která používá prostředí Windows Runtime.


 Další informace o **typ aplikace** vlastnost, naleznete v tématu [/Target (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/target-compiler-option). Informace o tom, jak programově přístup k této vlastnosti naleznete v tématu <xref:VSLangProj.ProjectProperties.OutputType%2A>.

 **Informace o sestavení** kliknete na toto tlačítko se zobrazí [dialogové okno informace o sestavení](../../ide/reference/assembly-information-dialog-box.md).

 **Spouštěcí objekt** definuje vstupní bod, který bude volán při načtení aplikace. Obvykle je tato možnost nastavená buď hlavního formuláře v aplikaci nebo na `Main` proceduru, která se má spustit při spuštění aplikace. Vzhledem k tomu, že nemá vstupní bod knihovny tříd, jejich jedinou možností pro tuto vlastnost je **(Nenastaveno)**.

 Ve výchozím nastavení v projektu aplikace WPF pro prohlížeč, tato možnost je **(Nenastaveno)**. Další možností je *Projectname*. App. V tento druh projektu je nutné nastavit počáteční identifikátor URI pro načtení prostředku uživatelského rozhraní při spuštění aplikace. Chcete-li to provést, otevřete soubor Application.xaml ve vašem projektu a nastavit `StartupUri` vlastnosti do souboru .xaml v projektu, jako je například Window1.xaml. Seznam prvků přijatelný kořenový najdete v tématu <xref:System.Windows.Application.StartupUri%2A>. Budete také muset definovat `public static void Main()` metody ve třídě v projektu. Tato třída se objeví v **spouštěcí objekt** jako seznam *ProjectName.ClassName*. Pak můžete vybrat třídu jako spouštěcí objekt.

 Zobrazit [/Main (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/main-compiler-option) Další informace. Programový přístup k této vlastnosti, najdete v článku <xref:VSLangProj.ProjectProperties.StartupObject%2A>.

## <a name="resources"></a>Prostředky
 Tyto možnosti umožňují nakonfigurovat obecná nastavení pro aplikaci.

 **Ikona a manifest** ve výchozím nastavení, je přepínač vybrán a **ikonu** a **Manifest** aktivnují možnosti. To umožňuje vybrat vlastní ikona nebo vyberte jiný generování manifestu možnosti. Nechte tento přepínač vybrat, pokud poskytujete soubor prostředků pro projekt.

 **Ikona** nastavuje soubor .ico, který chcete použít jako ikona programu. Klikněte na tlačítko se třemi tečkami k vyhledání existujícího obrázku nebo zadejte název souboru, který chcete. Zobrazit [/win32icon (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/win32icon-compiler-option) Další informace. Programový přístup k této vlastnosti, najdete v článku <xref:VSLangProj.ProjectProperties.ApplicationIcon%2A>.

 **Manifest** vybere možnost generování manifestu, když je aplikace spuštěná v systému Windows Vista v rámci řízení uživatelských účtů (UAC). Tato možnost může mít následující hodnoty:

-   **Vložit manifest s výchozím nastavením**. Podporuje typické způsobem, ve kterém aplikace Visual Studio pracuje na Windows Vista, který je pro vložení informací o zabezpečení ve spustitelném souboru aplikace, určení, že `requestedExecutionLevel` být `AsInvoker`. Toto je výchozí možnost.

-   **Vytvořit aplikaci bez manifestu**. Tato metoda se označuje jako *virtualizace*. Tuto možnost použijte, pokud z důvodu kompatibility s dřívějšími aplikacemi.

-   **Properties\app.manifest**. Tato možnost je vyžadována pro aplikace nasazené pomocí technologie ClickOnce nebo bez registrace modelu COM Pokud publikujete třeba aplikaci pomocí nasazení ClickOnce **Manifest** se automaticky nastaví na tuto možnost.

**Soubor prostředků** vyberte přepínač, když poskytujete soubor prostředků pro projekt. Výběrem této možnosti zakáže **ikonu** a **Manifest** možnosti.

Zadejte název cesty nebo klikněte na tlačítko Procházet (**...** ) Chcete-li přidat soubor prostředků Win32 do projektu.