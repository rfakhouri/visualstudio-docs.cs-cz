---
title: "Ověřte prostředí Xamarin | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd39882e-06d1-4b39-80d2-4d07b6e4f8f5
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- xamarin
ms.openlocfilehash: 5878da6742412a368e7b5ff84d0e0e20a4751914
ms.sourcegitcommit: 342e5ec5cec4d07864d65379c2add5cec247f3d6
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/27/2018
---
# <a name="verify-your-xamarin-environment"></a>Ověřte prostředí Xamarin
Po dokončení instalační programy (viz [nastavení a instalaci](../cross-platform/setup-and-install.md)), věnovat několik minut, ověřte, zda je vše připraveno prostředí vývoj na platformě Xamarin.  
  
 Po dokončení těchto ověřování, můžete provést jednu nebo obě následující kurzy:  
  
-   [Základy vytváření aplikací s Xamarin.Forms v sadě Visual Studio](../cross-platform/learn-app-building-basics-with-xamarin-forms-in-visual-studio.md)  
  
-   [Vytváření aplikací s nativním uživatelským rozhraním pomocí Xamarinu v sadě Visual Studio](../cross-platform/build-apps-with-native-ui-using-xamarin-in-visual-studio.md)  
  
## <a name="all-platforms"></a>Všechny platformy  
 Nejprve vyberte **nástroje > Možnosti**, rozbalte položku **Xamarin > jiných**a klikněte na tlačítko **zkontrolujte teď** odkaz pro aktualizace. Musíte používat Xamarin 4.0.3.214 nebo později zabránili předchozí problémy s licencí.  
  
 Pak vytvořte nové řešení Xamarin v sadě Visual Studio pomocí **soubor > Nový projekt**, pak v dialogovém okně rozbalte **šablony > jiné jazyky > Visual C# > napříč platformami**, vyberte  **Prázdná aplikace (nativní přenosné)**a klikněte na tlačítko OK. Tím se vytvoří řešení s projektu knihovny přenosných tříd sdílené a jednotlivých projektů pro Android, iOS a Windows:  
  
 ![Výsledky vytvoření nového projektu z prázdnou aplikaci &#40; Nativní přenositelností &#41; Šablona](../cross-platform/media/crossplat-xamarin-verify-1.png "CrossPlat Xamarin ověřte 1")  
  
> [!NOTE]
>  Pokud nejsou šablony došlo, najdete v [jsou šablony projektu Xamarin chybí? Zkuste to](#missing) v dolní části této stránky.  
  
## <a name="android"></a>Android  
  
1. Zkontrolujte, že máte nejnovější Android SDK nástroje nainstalované přechodem na **nástroje > Android > Android SDK Manager** a nainstalovat nejnovější verzi nástroje Android SDK, nástrojů platformy Android SDK a Android SDK – nástroje pro vytváření komponenty. Všimněte si, že není potřeba vždy instalovat nejnovější úroveň rozhraní API systému Android; rozhraní API, které potřebujete, závisí na úrovni platformy, které chcete zacílit. Obecně platí instalace Xamarin nainstaluje úroveň platformu, která vyžaduje.  

2.  Ověření návrháře Android: v projektu pro Android v Průzkumníku řešení, otevřete **prostředky > rozložení > Main.axml** souboru. (Pokud nevidíte tento soubor přímo, zkuste vyhledat v Průzkumníku řešení; existuje v projektu pro Android pouze a není v projektu pro iOS.)  
  
    - Pokud se zobrazí chyba s oznámením "Nainstalované sady SDK pro Android je příliš starý.", klikněte na tlačítko **otevřete Android SDK** v této zprávě vyberte a nainstalujte nejnovější SDK verze nástroje k dispozici jako v kroku 1 výše. 
  
3.  Ověření, sestavování a ladění v emulátoru (nebo zařízení):  
  
    -   Klikněte pravým tlačítkem na projekt pro Android v Průzkumníku řešení a vyberte **nastavit jako spouštěný projekt**.  
  
         ![Visual Studio nastavit jako možnost spuštění projektu](../cross-platform/media/crossplat-xamarin-verify-2.png "CrossPlat Xamarin ověřte 2")  
  
    -   Vyberte odpovídající emulátor založené na verzi systému Android cíl; Pokud máte zařízení s vývoj pro Android připojené k počítači, zobrazí se také, že tady spolu s emulátorů:  
  
        -   Windows 8 +: vyberte **VS emulátoru** target v sadě Visual Studio ladění rozevíracího seznamu, jak je uvedeno níže a spuštění ladicího programu stisknutím **F5**. Další podrobnosti najdete v tématu [emulátor představení sady Visual Studio pro Android](http://blogs.msdn.com/b/visualstudioalm/archive/2014/11/12/introducing-visual-studio-s-emulator-for-android.aspx) (Visual Studio ALM blog). Pokud narazíte na problémy získávání emulátor fungovat, najdete v článku [řešení potíží s Visual Studio Emulator for Android](../cross-platform/troubleshooting-the-visual-studio-emulator-for-android.md). Můžete také vytvořit nové profily zařízení pro emulátor výběrem **nástroje > Visual Studio Emulator for Android...** .  
  
             ![Výběr emulátor sady Visual Studio pro Android jako cíl ladění](../cross-platform/media/crossplat-xamarin-verify-3.png "CrossPlat Xamarin ověřte 3")  
  
             Poznámka: Pokud se nezobrazí **nástroje > Visual Studio Emulator for Android...**  nabídky, nemusí mít emulátoru sám nainstalovat. Přejděte na **ovládací panely > programy a funkce**, vyberte **Microsoft Visual Studio**a klikněte na tlačítko **změnu** znovu spusťte instalační program. Klikněte na tlačítko **upravit** v instalačním programu, zaškrtněte políčko pro **vývoj pro různé platformy Mobile > Microsoft Visual Studio Emulator for Android**a klikněte na tlačítko **aktualizace**.  
  
        -   Pro systém Windows 7 a starší: Vyberte Xamarin Player pro Android v rozevíracím seznamu místo a stisknutím klávesy F5 spusťte. Podrobnosti o Xamarin Player, přečtěte si jeho Správce zařízení a Poradce při potížích, [Xamarin Android Player](http://developer.xamarin.com/guides/android/getting_started/installation/android-player/) (xamarin.com).  
  
> [!NOTE]
>  V sadě Visual Studio můžete si povšimnout přítomnost tlačítko Android emulátoru Manager (AVD) na panelu nástrojů (Zobrazit níže), otevře se Správce zařízení, která konkrétně slouží ke konfiguraci emulátor Google Android.  To nemá žádný vliv na buď emulátor sady Visual Studio pro Android nebo Xamarin přehrávač, z nichž každá má své vlastní Správce zařízení pro konfiguraci profilů.  V tématu [emulátor představení sady Visual Studio pro Android](http://blogs.msdn.com/b/visualstudioalm/archive/2014/11/12/introducing-visual-studio-s-emulator-for-android.aspx) (blog Visual Studio ALM) a [Xamarin Android Player](http://developer.xamarin.com/guides/android/getting_started/installation/android-player/) (xamarin.com) podrobnosti.  
> ![CrossPlat Xamarin ověřte 7](../cross-platform/media/crossplat-xamarin-verify-7.png "CrossPlat Xamarin ověřte 7")  
  
## <a name="windows-phone"></a>Windows Phone  
  
1.  Ověření návrháře Windows Phone: v projektu Windows Phone v Průzkumníku řešení otevřete **MainPage.xaml** souboru.  
  
2.  Ověření sestavování a ladění v emulátoru nebo na zařízení (Poznámka: je nutné mít nainstalované prostřednictvím instalaci sady Visual Studio pro tento krok nebo připojeného zařízení emulátoru Windows Phone):  
  
    -   Windows Phone projekt v Průzkumníku řešení klikněte pravým tlačítkem a vyberte **nastavit jako spouštěný projekt**.  
  
    -   Vyberte **emulátoru 8.1** cíl nebo připojeném zařízení v sadě Visual Studio ladit rozevíracího seznamu, jak je uvedeno níže a spuštění ladicího programu stisknutím klávesy F5.  
  
         ![Výběr emulátoru Windows Phone jako cíl ladění](../cross-platform/media/crossplat-xamarin-verify-4.png "CrossPlat Xamarin ověřte 4")  
  
    -   Pokud narazíte na problémy získávání emulátor fungovat, přečtěte si [řešení potíží s emulátoru Windows Phone 8](/previous-versions/windows/apps/jj681694\(v%3dvs.105\)).  
  
## <a name="ios"></a>iOS  
  
1.  Zkontrolujte, že počítač Mac je dostupný v síti a spárované sadou Visual Studio, jak je popsáno na [připojení k počítači Mac](http://developer.xamarin.com/guides/ios/getting_started/installation/windows/xamarin-mac-agent/) (xamarin.com).  
  
2.  Ověření návrháře storyboard: v projektu iOS v Průzkumníku řešení otevřete **Main.storyboard** souboru. Zde je Visual Studio hostování návrháře vzdáleně systémem Mac.  
  
3.  Ověření, sestavování a ladění:  
  
    1.  Klikněte pravým tlačítkem na projekt pro iOS v Průzkumníku řešení a vyberte **nastavit jako spouštěný projekt**.  
  
    2.  Vyberte **iPhoneSimulator** cíle ze sestavení sady Visual Studio rozevíracího seznamu, jak je uvedeno níže, nebo **iPhone** cíle, pokud máte připojeného zařízení. Pokud nejsou uvedeny žádné simulátorů, spusťte na počítači Mac, vyberte Xcode **Xcode -> Předvolby**a klikněte na tlačítko **Stáhnout**. V části **součásti** byste měli vidět simulátoru verze, které jsou k dispozici ke stažení. Další pokyny pro ladění naleznete na Xamarin [ladění](https://developer.xamarin.com/guides/ios/deployment,_testing,_and_metrics/debugging_in_xamarin_ios/#Debugging_on_the_Simulator) stránky (xamarin.com).  
  
         ![Výběr iPhoneSimulator sestavení cíl](../cross-platform/media/crossplat-xamarin-verify-5.png "CrossPlat Xamarin ověřte 5")  
  
    3.  Vyberte cíl iPhone ze sady Visual Studio ladění rozevíracího seznamu, jak je uvedeno níže a spuštění ladicího programu stisknutím klávesy F5. Spustí se simulátoru v systému Mac, kde budete pracovat s aplikací, při ladění se stane v sadě Visual Studio. Pokud máte fyzického zařízení iPhone nebo iPad připojené k počítači Mac, zobrazí se zde a můžete ji vybrat místo. Pokud nevidíte žádné zařízení nebo simulátorů uvedené, zkontrolujte připojení k počítači Mac najdete v tématu propojené v kroku 1 výše nebo přechodem na **nástroje** >**iOS**  > **Xamarin Mac Agent**  
  
         ![Výběr cíli ladění iPhone](../cross-platform/media/crossplat-xamarin-verify-6.png "CrossPlat Xamarin ověřte 6")  
  
    4.  Pokud narazíte na potíže s připojením k počítači Mac, přečtěte si [odstraňování problémů s připojením](http://developer.xamarin.com/guides/ios/getting_started/installation/windows/xamarin-mac-agent/xma-troubleshooting/) (xamarin.com).  
  
    5.  Pokud se zobrazí tom, že chyba "žádné nainstalované zřizovacích profilů shodují nainstalované iOS podpisových klíčů, postupujte takto:  
  
        -   Zkontrolujte, že váš účet Apple Id je přidaný do Xcode na počítači Mac, jak je popsáno na [přidání si účet na Xcode](https://developer.apple.com/library/content/documentation/IDEs/Conceptual/AppStoreDistributionTutorial/AddingYourAccounttoXcode/AddingYourAccounttoXcode.html#//apple_ref/doc/uid/TP40013839-CH40-SW1) (apple.com).  Po přidání účtu, je nutné restartovat Visual Studio a Xcode.  
  
             ![CrossPlat Xamarin ověřte 8](../cross-platform/media/crossplat-xamarin-verify-8.png "CrossPlat Xamarin ověřte 8")  
  
        -   Ověřte v iOS sady vlastností projektu v iOS podpisový kartě, že vlastní pole nárocích je prázdná pro konfiguraci ladění active.  Poznámka: pouze vyzkoušejte odebrání toto nastavení, pokud byla zjištěna výše chybová zpráva.  
  
##  <a name="missing"></a> Chybí šablony projektu Xamarin Zkuste to  
 Šablony může být chybějící, pokud nainstalujete Xamarin přímo z webu Xamarin a máte Visual Studio 2013 a Visual Studio 2015 nainstalovat vedle sebe. Je snadné opravit, když: Povolit jenom **Xamarin pro Visual Studio 2015** funkce v instalačním programu Xamarin.  
  
1.  V Ovládacích panelech otevřete **programy a funkce**, vyberte **Xamarin** položku a klikněte na tlačítko **změnu**.  
  
2.  V Průvodci instalací pro Xamarin, který se zobrazí, klikněte na tlačítko **Další** a potom **změnu**.  
  
3.  V seznamu volitelných funkcí pro instalaci, rozbalte **Xamarin pro Visual Studio 2015**, zvolte **bude nainstalována na místní disk**a klikněte na tlačítko **Další** přidávání funkce.