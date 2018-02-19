---
title: "Mobilní vývoj pro různé platformy v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 12/06/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-mobile
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8202717a-e990-45cf-b092-438651ccb38a
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: dfdd5aee71c74febbeca0b7c9683aaa6be915e6e
ms.sourcegitcommit: a07b789cc41ed72664f2c700c1f114476e7b0ddd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/19/2018
---
# <a name="cross-platform-mobile-development-in-visual-studio"></a>Mobilní vývoj pro různé platformy v sadě Visual Studio

Aplikace pro Android, iOS a Windows zařízení můžete vytvořit pomocí sady Visual Studio.  Při navrhování vaší aplikace pomocí nástrojů v sadě Visual Studio můžete snadno přidání připojených služeb, jako je například Office 365, Azure App Service a Application Insights.

Sestavení aplikace pomocí jazyka C# a rozhraní .NET Framework, HTML a JavaScript nebo C++. Sdílení kódu, řetězce, obrázky a v některých případech i v uživatelském rozhraní.

Pokud chcete vytvořit aplikaci grafické herní nebo dokonalé, instalace nástrojů Visual Studio tools for Unity a užívat produktivitu výkonné funkce Visual Studio s Unity, rozšířených napříč platformami hra na grafických modul a vývojového prostředí pro aplikace, která Spusťte na iOS, Android, Windows a jiné platformy.

## <a name="build-an-app-for-android-ios-and-windows-net-framework"></a>Vytvoření aplikace pro Android, iOS a Windows (rozhraní .NET Framework)

![Zařízení](../cross-platform/media/homedevices.png "HomeDevices")

S Xamarinem můžete určit cílovou Android, iOS a Windows ve stejném řešení, sdílení kódu a to i v uživatelském rozhraní.

|Víc se uč|
|--------------------|
|[Instalaci sady Visual Studio](http://www.visualstudio.com/products/visual-studio-community-vs) (VisualStudio.com)|
|[Další informace o Xamarinu ve Visual Studiu](http://www.visualstudio.com/explore/xamarin-vs) (VisualStudio.com)|
|[Visual Studio a Xamarin](../cross-platform/visual-studio-and-xamarin.md) (Knihovna MSDN)|
|[Správa životního cyklu aplikací (ALM) s aplikacemi Xamarin](../cross-platform/application-lifecycle-management-alm-with-xamarin-apps.md) (Knihovna MSDN)|
|[Další informace o univerzální aplikace pro Windows v sadě Visual Studio](https://www.visualstudio.com/vs/universal-windows-platform/) (VisualStudio.com)|
|[Další informace o podobnosti mezi Swift a C#](http://aka.ms/scposter) (download.microsoft.com)|
|[Další informace o emulátor sady Visual Studio pro Android](http://www.visualstudio.com/explore/msft-android-emulator-vs) (VisualStudio.com)|

###  <a name="AndroidHTML"></a> Cíl Android, iOS a Windows z jednoho základu kódu
 Nativní aplikace pro Android, iOS a Windows můžete vytvořit pomocí jazyka C# nebo F # (Visual Basic není podporována v tuto chvíli).  Chcete-li začít, nainstalujte Visual Studio 2015, vyberte **vlastní** možnosti v instalačním programu a zaškrtněte políčko v části **křížové platformy vývoj mobilních řešení pro > C# nebo rozhraní .NET (Xamarin)**. Můžete také spustit s [instalační program Xamarin](https://www.xamarin.com/download), které je potřeba nainstalovat Xamarin pro Visual Studio 2013.

 Pokud je již nainstalovaná sada Visual Studio 2015, spusťte instalační program z **ovládací panely > programy a funkce** a vyberte stejný **vlastní** možnost pro Xamarin, jak je uvedeno výše.

 Když jste hotovi, zobrazí se šablony projektů v **nový projekt** dialogové okno. Nejjednodušší způsob, jak najít Xamarin šablony je právě hledání "Xamarin."

 Xamarin zveřejňuje nativní funkce systému Android, iOS a Windows jako objekty .NET. Proto aplikací mít úplný přístup k rozhraní API pro nativní a nativní uživatelské ovládací prvky a jsou právě přizpůsobivý jako aplikace napsané v jazyce nativní platforma.

 Po vytvoření projektu, budete využívat všechny funkce produktivitu sady Visual Studio. Budete například pomocí návrháře můžete vytvořit svoje stránky a k prohlížení v nativní rozhraní API mobilních platforem používat technologii IntelliSense. Až budete připraveni spuštění aplikace a zobrazit, jak vypadá, můžete použít emulátor sady Visual Studio pro Android nebo sady SDK pro Android emulátoru, nativně spouštět aplikace pro Windows nebo spouštět aplikace pro Windows v emulátoru Windows Phone. Připojené zařízení s Androidem a Windows můžete také použít přímo. Pro projekty iOS připojit k síťově připojeného počítače Mac a spusťte emulátor Mac ze sady Visual Studio nebo připojení k připojené zařízení.

#### <a name="design-one-set-of-pages-that-render-across-all-devices-by-using-xamarinforms"></a>Návrh jednu sadu stránek, které vykreslení ve všech zařízeních s použitím Xamarin.Forms
 V závislosti na složitosti návrhu aplikace, můžete zvážit sestavení pomocí *Xamarin.Forms* šablony v **Mobile Apps** skupiny šablon projektu. Xamarin.Forms je sada nástrojů uživatelského rozhraní, které umožňují vytvořit jednotné rozhraní, které můžete sdílet mezi Android, iOS a Windows.  Při kompilaci řešení Xamarin.Forms získáte aplikace pro Android, iOS aplikace a aplikace pro Windows. Další podrobnosti najdete v tématu [Další informace o pro vývoj mobilních řešení s Xamarinem](../cross-platform/learn-about-mobile-development-with-xamarin.md).

####  <a name="ShareHTML"></a> Sdílet kód mezi Android, iOS a aplikace pro Windows
 Pokud nepoužíváte Xamarin.Forms a zvolit návrh pro každou platformu jednotlivě, můžete sdílet většinu kódu bez uživatelského rozhraní mezi projekty platformy (Android, iOS a Windows). To zahrnuje veškeré obchodní logiky, integrace cloudu, přístup k databázi nebo jiný kód, který cílí rozhraní .NET Framework. Pouze kód, který nelze sdílet je kód, který se zaměřuje konkrétní platformu.

 ![Sdílet kód mezi Windows, iOs a Android uživatelského rozhraní](../cross-platform/media/sharecode.png "ShareCode")

 Váš kód můžete sdílet s použitím sdíleného projektu, projektu knihovny přenosných tříd nebo obojí. Je možné, že některé kód pro rozlišení, které nejlépe v sdílený projekt a určitý kód provede další smysl v projektu knihovny přenosných tříd.

|Víc se uč|
|--------------------|
|Vyberte, zda se sdílet kódu pomocí sdílených projektů, projektů knihovny přenosných tříd nebo obojí.<br /><br /> [Sdílení kódu napříč platformami](http://blogs.msdn.com/b/dotnet/archive/2014/04/21/sharing-code-across-platforms.aspx) (blog na rozhraní .NET Framework)<br /><br /> [Sdílení kódu možnosti](http://developer.xamarin.com/guides/cross-platform/application_fundamentals/building_cross_platform_applications/sharing_code_options/) (Xamarin)<br /><br /> [Kód možnosti sdílení s rozhraním .NET Framework](http://msdn.microsoft.com/library/dn720832.aspx) (Knihovna MSDN)|

###  <a name="WindowsHTML"></a> Cílová zařízení Windows 10
 ![Windows Devices](../cross-platform/media/windowsdevices.png "WindowsDevices")

 Pokud chcete vytvořit jenom jedna aplikace, která je cílena úplného spektra zařízení s Windows 10, vytvořte univerzální aplikace pro Windows. Budete návrh aplikace pomocí jednoho projektu a vaše stránky se zobrazují správně bez ohledu na to, jaké zařízení se používá k jejich zobrazení.

 Spustit pomocí šablony projektu univerzální aplikace Windows. Vizuální návrh svoje stránky a otevřete v okně prostředí preview a najdete v části Jak se zobrazují pro různé typy zařízení. Pokud vám nevyhovuje, jak se zobrazí stránka s na zařízení, můžete optimalizovat stránce lépe přizpůsobit velikost obrazovky, řešení nebo různé orientace jako třeba v režimu šířku i na výšku. Všechny, můžete provést pomocí možnosti nabídka snadno dostupné a intuitivní nástroje systému windows v sadě Visual Studio. Až budete připraveni ke spuštění aplikace a krok prostřednictvím kódu, zjistíte všechny zařízení emulátorů a simulátorů pro různé typy zařízení společně v jednom seznamu rozevíracího seznamu, který se nachází na **standardní** panelu nástrojů.

 Windows 10 je docela nové, takže jsou zde také šablony projektů cílených Windows 8.1. Pokud chcete, aby a vaše aplikace poběží na telefony, tablety a počítače s Windows 10 můžete použít tyto šablony projektu. Všechna zařízení se systémem Windows 8.1 se však zobrazí automatické upgradu na Windows 10, takže pokud nemáte konkrétní důvodů, proč by místo cíle Windows 8.1, doporučujeme používat šablony projektu, které cílí na Windows 10.

|Víc se uč|
|--------------------|
|[Další informace o univerzálních aplikací pro Windows](https://msdn.microsoft.com/library/windows/apps/dn894631.aspx) (Centrum vývojářů pro Windows)|
|[Vytvoření vaší první z nich](http://msdn.microsoft.com/library/windows/apps/dn609832.aspx) (Centrum vývojářů pro Windows)|
|[Vývoj aplikací pro Univerzální platformu Windows (UWP)](../cross-platform/develop-apps-for-the-universal-windows-platform-uwp.md)|
|[Migrace aplikací do univerzální platformy Windows (UWP)](https://msdn.microsoft.com/en-us/library/mt148501.aspx)|

##  <a name="HTML"></a> Vytvoření aplikace pro Android, iOS a Windows (HTML/JavaScript)
 ![Zařízení](../cross-platform/media/homedevices.png "HomeDevices")

 Pokud jste vývojář webu a jste obeznámeni s jazyky HTML a JavaScript, můžete určit cílovou Windows, Android a iOS pomocí nástroje sady Visual Studio pro Apache Cordova. Tyto aplikace můžete cílit na všechny tři platformy a můžete je vytvořit pomocí dovedností a procesy, které jste nejvíce obeznámeni s.

 Apache Cordova je rozhraní, které zahrnuje modul plug-in. Tento modul plug-in model poskytuje jediného rozhraní API jazyka JavaScript, který můžete použít pro přístup nativní zařízení s možností všechny tři platformy (Android, iOS a Windows).

 Protože tato rozhraní API a platformy, můžete sdílet většina zápisu mezi všechny tři platformy. To snižuje náklady na vývoj a údržba. Je také potřeba začít úplně od začátku. Pokud jste vytvořili jiné typy webových aplikací, můžete tyto soubory sdílet s vaší aplikace Cordova bez nutnosti upravit nebo změnit jejich návrh žádným způsobem.

 ![Multi&#45;Device Hybrid Apps](../cross-platform/media/multidevicehybridapps.png "MultiDeviceHybridApps")

 Pokud chcete začít, nainstalujte Visual Studio 2015 a vybrat **HTML/JavaScript (Apache Cordova)** funkce během instalace. Pokud používáte Visual Studio 2013, nainstalujte Visual Studio Tools for Apache Cordova rozšíření. V obou případech nástroje Cordova automaticky nainstalovat veškerý software třetích stran, které je nutné k sestavení aplikace více platformami.

 Po instalaci rozšíření, otevřete Visual Studio a vytvořte **prázdná aplikace (Apache Cordova)** projektu. Potom můžete vyvíjet aplikace pomocí jazyka JavaScript a Typescript. Můžete také přidat moduly plug-in rozšířit funkce aplikace a rozhraní API pro moduly plug-in se zobrazí v technologii IntelliSense, jak napsat kód.

 Až budete připraveni ke spuštění aplikace a krok prostřednictvím kódu, zvolte emulátoru, jako je například Apache Ripple emulátoru nebo Visual Studio Emulator (Android nebo Windows Phone), v prohlížeči nebo zařízení, které jste se připojili k počítači. Spusťte aplikaci. Pokud vyvíjíte aplikace na počítači s Windows, které můžete dokonce spouštět na tomto. Všechny tyto možnosti jsou součástí sady Visual Studio jako součást sady Visual Studio Tools pro Apache Cordova.

 Šablony projektů pro vytváření univerzálních aplikací pro Windows jsou stále k dispozici v sadě Visual Studio tak zaregistrované, můžete je použít, pokud budete chtít cílové jenom zařízení se systémem Windows. Pokud se rozhodnete později cílit Android a iOS, můžete vždy přenesení kódu do projektu Cordova. Existují open-source verze rozhraní API WinJS, takže můžete opakovaně použít kód, který využívá těchto rozhraní API. Ale nutné dodat, pokud budete chtít v budoucnu cíle jiné platformy, doporučujeme spustit pomocí nástrojů Visual Studio pro Apache Cordova.

|Víc se uč|
|--------------------|
|[Instalaci sady Visual Studio](http://www.visualstudio.com/products/visual-studio-community-vs) (VisualStudio.com)|
|[Začínáme s nástroji Visual Studio Tools pro Apache Cordova](/visualstudio/cross-platform/tools-for-cordova/) (docs.microsoft.com)|
|[Další informace o emulátor sady Visual Studio pro Android](http://www.visualstudio.com/explore/msft-android-emulator-vs) (VisualStudio.com)|

##  <a name="CPP"></a> Vytvoření aplikace pro Android a Windows (C++)
 ![Pomocí C & č. 43; & č. 43; k sestavení pro Android, iOS a Windows](../cross-platform/media/cross_plat_cpp_intro_image.png "Cross_Plat_CPP_Intro_Image")

 Nejdřív Nainstalujte Visual Studio 2015 a Visual C++ pro nástroje pro vývoj pro různé platformy Mobile. Potom můžete vytvořit nativní aktivity aplikace pro Android nebo aplikaci, která je cílem Windows. C++ šablony, které cílí iOS ještě nejsou k dispozici. Můžete určit cílovou Android a Windows ve stejném řešení, pokud chcete a potom sdílet kód mezi nimi pomocí napříč platformami statickou nebo dynamickou sdílenou knihovnu.

 Pokud potřebujete k vytvoření aplikace pro Android, která vyžaduje žádné řazení manipulace pokročilé grafiky, jako je například hry, můžete to udělat C++. Začínat **aktivity nativní aplikace (Android)** projektu. Tento projekt má plnou podporu pro nástrojů Clang.

 ![Šablona projektu nativní aktivity](../cross-platform/media/cross-plat_cpp_native.png "mezi Plat_CPP_Native")

 Až budete připraveni spuštění aplikace a zobrazit, jak vypadá, použijte emulátor sady Visual Studio pro Android. Je rychlé, spolehlivé a snadné k instalaci a konfiguraci.

 Můžete také vytvořit aplikaci, která cílí úplného spektra zařízení s Windows 10 pomocí C++ a šablona projektu univerzální aplikace Windows. Další informace o to [zařízení s Windows 10 cíl](#WindowsHTML) oddíl, který se zobrazí v tomto tématu výše.

 C++ – kód mezi Android a Windows můžete sdílet vytvořením statickou nebo dynamickou sdílenou knihovnu.

 ![Statické a dynamické sdílené knihovny](../cross-platform/media/cross_plat_cpp_libraries.png "Cross_Plat_CPP_Libraries")

 Můžete využívat této knihovny v systému Windows nebo projekt pro Android, jako jsou ty dříve popisované v této části. Můžete také spotřebujete ho v aplikaci, který můžete vytvořit pomocí Xamarin, Java nebo jakýkoli jazyk, který umožňuje vyvolání funkce v nespravované knihovně DLL.

 Při psaní kódu v tyto knihovny, můžete použít technologie IntelliSense a prozkoumejte rozhraní nativní API platformy Android a Windows. Tyto knihovny projekty jsou plně integrované s ladicího programu sady Visual Studio, můžete nastavit zarážky, krokovat kód a najít a opravit problémy s použitím všech pokročilých funkcí ladicího programu.

|Víc se uč|
|--------------------|
|[Stáhněte si Visual Studio.](http://www.visualstudio.com/products/visual-studio-community-vs) (VisualStudio.com)|
|[Nainstalujte Visual C++ pro nástroje pro vývoj mobilních řešení pro různé platformy.](https://msdn.microsoft.com/library/dn872463\(v=vs.140\).aspx) (Knihovna MSDN)|
|[Další informace o používání C++ pro více cílových platforem.](https://www.visualstudio.com/vs/cplusplus-mdd/) (VisualStudio.com)|
|[Nainstalujte co potřebujete a potom vytvořte nativní aktivity aplikace pro Android](https://msdn.microsoft.com/library/dn872463\(v=vs.140\).aspx) (Knihovna MSDN)|
|[Další informace o emulátor sady Visual Studio pro Android](http://www.visualstudio.com/explore/msft-android-emulator-vs) (VisualStudio.com)|
|[Další informace o sdílení kódu C++ s aplikací pro Android a Windows](https://www.visualstudio.com/vs/cplusplus-mdd/) (VisualStudio.com)|
|[Vývoj pro různé platformy mobilních příklady pro jazyk C++](https://msdn.microsoft.com/library/dn707596.aspx) (Knihovna MSDN)|
|[Příklady dalších mobilní vývoj pro různé platformy pro jazyk C++](https://code.msdn.microsoft.com/site/search?f%5B0%5D.Type=SearchText&f%5B0%5D.Value=android&f%5B1%5D.Type=ProgrammingLanguage&f%5B1%5D.Value=C%2B%2B&f%5B1%5D.Text=C%2B%2B) (code.msdn)|

##  <a name="Unity"></a> Vytvořte hru a platformy pro Android, iOS a Windows pomocí nástrojů Visual Studio tools for Unity
 Visual Studio Tools for Unity je bezplatná rozšíření pro Visual Studio, která integruje Visual Studio úpravy výkonné kódu, produktivitu a ladicí nástroje s *Unity*, modul oblíbených herní/grafiky napříč platformami a vývojové prostředí pro dokonalé aplikace, které se zaměřují na Windows, iOS, Android a jiné platformy, včetně webu.

 ![Vývojové prostředí VSTU](../cross-platform/media/vstu_overview.png "VSTU_Overview")

 Pomocí nástrojů Visual Studio pro Unity (VSTU) můžete použít Visual Studio psaní herní a editor skriptů v jazyce C# a pak použijte jeho výkonný ladicí program k vyhledání a opravte chyby. Nejnovější verze VSTU poskytuje podporu pro Unity 5 a zahrnuje barevné zvýrazňování syntaxe pro jazyk shaderu ShaderLab pro Unity, lepší synchronizace s Unity, bohatší ladění a generování kódu vylepšené MonoBehavior průvodce. VSTU přináší také soubory projektu Unity, zprávy konzoly a možnost spuštění vaše hra do sady Visual Studio, takže může trávit méně času přepnutí do a z editoru Unity při psaní kódu.

 Začněte vytvářet vaše hra Unity a Visual Studio Tools for Unity ještě dnes.

|Víc se uč|
|--------------------|
|[Další informace o vytváření Unity hry pomocí sady Visual Studio](https://www.visualstudio.com/en-us/features/unitytools-vs.aspx)|
|[Další informace o Visual Studio Tools for Unity](../cross-platform/visual-studio-tools-for-unity.md) (Knihovna MSDN)|
|[Začít používat Visual Studio Tools for Unity](../cross-platform/getting-started-with-visual-studio-tools-for-unity.md) (Knihovna MSDN)|
|[Přečtěte si informace o nejnovější vylepšení pro sadu Visual Studio Tools pro Unity 2.0 Preview](http://blogs.msdn.com/b/visualstudio/archive/2014/12/03/visual-studio-tools-for-unity-2-0-preview.aspx) (blog Visual Studio)|
|[Podívejte se na video Úvod do sady Visual Studio Tools pro Unity 2.0 Preview](http://www.bing.com/videos/search?q=visual+studio+tools+for+unity&qs=n&form=QBVLPG&pq=visual+studio+tools+for+unity&sc=6-29&sp=-1&sk=#view=detail&mid=0A13177F0BC7463A24080A13177F0BC7463A2408) (Video)|
|[Další informace o Unity](http://unity3d.com/) (Unity webu)|

## <a name="see-also"></a>Viz také
 - [Přidejte do projektu sady Visual Studio Office 365 API](http://msdn.microsoft.com/library/office/dn605899\(v=office.15\).aspx)
 - [Azure App Services - mobilní aplikace](https://azure.microsoft.com/en-us/services/app-service/mobile/)
 - [HockeyApp pro mobile](https://azure.microsoft.com/en-us/services/hockeyapp/)