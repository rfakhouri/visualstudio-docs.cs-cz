---
title: "Stránka aplikace, Návrhář projektu (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cs.ProjectPropertiesApplicationWPF
- cs.ProjectPropertiesApplication
helpviewer_keywords:
- Project Designer, Application page
- Application page in Project Designer
ms.assetid: f13701a8-4e2e-4474-9d60-bb43decbe0c1
caps.latest.revision: "56"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: ec48d6a581eb756ee89d9db1a3dfaa78ac1fb3a9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="application-page-project-designer-c"></a>Stránka Aplikace, návrhář projektu (C#)
Použití **aplikace** stránky **Návrhář projektu** zadat nastavení aplikace a vlastnosti projektu.  
  
Pro přístup k **aplikace** vyberte uzel projektu (ne **řešení** uzel) v **Průzkumníku řešení**. Zvolte **projektu**, **vlastnosti** v řádku nabídek. Jakmile se zobrazí v Návrháři projektu, klikněte **aplikace** kartě.  
  
[!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]  
  
## <a name="general-application-settings"></a>Obecné nastavení aplikace  
 Následující možnosti vám umožňují konfigurovat obecné nastavení pro aplikaci.  
  
 **Název sestavení**  
 Určuje název výstupního souboru, který bude obsahovat manifest sestavení. Změna této vlastnosti se také změní **název výstupu** vlastnost. Můžete provést také tuto změnu z příkazového řádku pomocí [/out (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/out-compiler-option). Přístup prostřednictvím kódu programu naleznete v tématu <xref:VSLangProj.ProjectProperties.AssemblyName%2A>.  
  
 **Výchozí obor názvů**  
 Určuje základní obor názvů pro soubory k projektu nepřidají.  
  
 V tématu [obor názvů](/dotnet/csharp/language-reference/keywords/namespace) pro další informace o vytváření oborů názvů v kódu.  
  
 Přístup prostřednictvím kódu programu naleznete v tématu <xref:VSLangProj.ProjectProperties.RootNamespace%2A>.  
  
 **Cílová architektura**  
 Určuje verzi rozhraní .NET Framework, cíle pro aplikace. Tato možnost může mít různé hodnoty v závislosti na tom, které jsou v počítači nainstalována verze rozhraní .NET Framework.  
  
 Výchozí hodnota je stejná jako cílové rozhraní, které jste vybrali v **nový projekt** dialogové okno.  
  
> [!NOTE]
>  Požadované balíčky uvedené v [dialogové okno požadavky](../../ide/reference/prerequisites-dialog-box.md) jsou automaticky nastavit poprvé otevřete dialogové okno. Pokud později změníte cílový framework projektu na, je nutné vybrat požadavky ručně tak, aby odpovídala nové cílové rozhraní.  
  
 Další informace najdete v tématu [postupy: cílení na verzi rozhraní .NET Framework](../../ide/how-to-target-a-version-of-the-dotnet-framework.md) a [přehled cílení na více Visual Studio](../../ide/visual-studio-multi-targeting-overview.md).  
  
 **Typ aplikace**  
 Určuje typ aplikace k sestavení. Pro aplikace pro Windows 8.x, můžete zadat **aplikace pro Windows Store**, **knihovny tříd**, nebo **souboru WinMD**. Pro většinu jinými typy aplikací, můžete zadat **aplikace Windows**, **konzolové aplikace**, **knihovny tříd**, **služba systému Windows**, nebo **webové ovládací prvek knihovna**.  
  
 Pro projekt webové aplikace je nutné zadat **knihovny tříd**.  
  
 Pokud zadáte **souboru WinMD** možnost typy je možné promítnout do jakékoli programovací jazyk prostředí Windows Runtime. Ve výstupu projektu jako soubor WinMD balení, může kód aplikace v různých jazycích a mají kód spolupracovat, jako kdyby byl napsán všechno ve stejném jazyce. Můžete zadat tuto možnost pro řešení, která cílí na prostředí Windows Runtime knihoven, včetně [!INCLUDE[win8_appname_long](../../debugger/includes/win8_appname_long_md.md)] aplikace. Další informace najdete v tématu [vytváření součásti systému Windows Runtime v C# a Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).  
  
> [!NOTE]
>  Prostředí Windows Runtime můžete typy projektů, aby se zobrazily jako nativní objekty v kteroukoli jazyk používá je. Například JavaScript aplikace, které pracují se prostředí Windows Runtime použít jako sadu objektů jazyka JavaScript a aplikací v C# v knihovně jako kolekce objektů .NET. Ve výstupu projektu jako soubor WinMD balení, můžete využít výhod stejné technologie, která používá prostředí Windows Runtime.  
  
 Další informace o **typ aplikace** vlastnost, najdete v části [/Target (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/target-compiler-option). Informace o tom, jak tato vlastnost přístup prostřednictvím kódu programu najdete v tématu <xref:VSLangProj.ProjectProperties.OutputType%2A>.  
  
 **Informace o sestavení**  
 Kliknutím na toto tlačítko zobrazí [dialogové okno informace o sestavení](../../ide/reference/assembly-information-dialog-box.md).  
  
 **Spouštěcí objekt**  
 Definuje vstupní bod, která se má volat při načtení aplikace. Obecně je nastavena buď do hlavního formuláře v aplikaci nebo na `Main` postup, který se má spustit při spuštění aplikace. Protože knihovny tříd nemají vstupního bodu, jejich jedinou možností pro tuto vlastnost je **(nenastavena)**.  
  
 Ve výchozím nastavení v aplikaci WPF prohlížeče projektu, tato možnost je **(nenastavena)**. Další možností je *Projectname*. App. V tento druh projektu budete muset nastavit počáteční identifikátor URI načíst prostředek uživatelského rozhraní při spuštění aplikace. Chcete-li to provést, otevřete soubor Application.xaml ve vašem projektu a nastavte `StartupUri` vlastnosti souboru XAML v projektu, například Window1.xaml. Seznam prvků přijatelné kořenové, najdete v části <xref:System.Windows.Application.StartupUri%2A>. Budete také muset definovat `public static void Main()` metodu v třídě v projektu. Tato třída se objeví v **spouštěcí objekt** seznamu jako *ProjectName.ClassName*. Pak můžete vybrat třída jako spouštěcí objekt.  
  
 V tématu [/Main (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/main-compiler-option) Další informace. Přístup prostřednictvím kódu programu naleznete v tématu <xref:VSLangProj.ProjectProperties.StartupObject%2A>.  
  
## <a name="resources"></a>Prostředky  
 Následující možnosti vám umožňují konfigurovat obecné nastavení pro aplikaci.  
  
 **Ikona a manifestu**  
 Ve výchozím nastavení, je přepínač vybrán a **ikonu** a **Manifest** jsou povoleny možnosti. To umožňuje vybrat vlastní ikonu, nebo vybrat jinou generování manifestu možnosti. Ponechte přepínač vybrat, pokud zadáte soubor prostředků pro projekt.  
  
 **Ikona**  
 Nastaví soubor .ico, který chcete použít jako ikona programu. Klikněte na tlačítko se třemi tečkami k vyhledání existujícího obrázku, nebo zadejte název souboru, který chcete. V tématu [/win32icon (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/win32icon-compiler-option) Další informace. Přístup prostřednictvím kódu programu naleznete v tématu <xref:VSLangProj.ProjectProperties.ApplicationIcon%2A>.  
  
 **Manifest**  
 Vybere možnost generování manifestu během spuštění aplikace v systému Windows Vista pod řízení uživatelských účtů (UAC). Tato možnost může mít následující hodnoty:  
  
-   **Vložení manifestu s výchozím nastavením**. Podporuje typické způsobem, ve kterém Visual Studio funguje v systému Windows Vista, což je pro vložení informací o zabezpečení ve spustitelném souboru aplikace, který zadání `requestedExecutionLevel` být `AsInvoker`. Toto je výchozí možnost.  
  
-   **Vytvořit aplikaci bez manifestu**. Tato metoda se označuje jako *virtualizace*. Tuto možnost použijte k zajištění kompatibility se starší aplikace.  
  
-   **Properties\app.manifest**. Tato možnost je povinná pro aplikace nasazené ClickOnce nebo-registrační COM. Pokud publikování aplikace pomocí nasazení ClickOnce **Manifest** se automaticky nastaví na tuto možnost.  
  
**Zdrojový soubor**  
Pokud zadáte soubor prostředků pro projekt, vyberte tento přepínač. Výběr této možnosti zakáže **ikonu** a **Manifest** možnosti.  
  
Zadejte název cesty nebo klikněte na tlačítko Procházet (**...** ) pro přidání zdrojového souboru Win32 do projektu.  
  
## <a name="see-also"></a>Viz také  
[Správa vlastností aplikace](../../ide/application-properties.md)  
[Psaní kódu v řešeních pro systém Office](/office-dev/office-dev/writing-code-in-office-solutions)