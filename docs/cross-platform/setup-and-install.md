---
title: "Instalační program a instalace | Microsoft Docs"
ms.custom: 
ms.date: 04/13/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2cfcad00-352c-4161-814c-f5ae32d8ada8
caps.latest.revision: "16"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: dba101890bd2f27c85e8e6053944d8781fa03ed4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="setup-and-install"></a>Nastavení a instalaci
Vytvářet nativní aplikace pro iOS, Android a Windows aplikace z běžných C# / kód .NET základní pomocí Xamarin, budete potřebovat následující:  
  
-   Pro práci s Windows a aplikací pro Android: vývoj počítač Windows s Visual Studio 2017 nebo 2015 s Xamarinem nainstalován. Můžete také použít Visual Studio 2013 podle pokynů pro [přímé instalace Xamarin](https://developer.xamarin.com/guides/cross-platform/getting_started/requirements/#install) (xamarin.com). 
  
-   Pro práci s aplikacemi pro iOS: Mac s systému macOS Sierra 10.12 nebo vyšší, s Xcode a Xamarin nainstalována.  
  
 Můžete nastavit systému Windows a počítače Mac ve stejnou dobu, a v době spuštění těchto instalační programy můžete přejít [Další informace o pro vývoj mobilních řešení s Xamarinem](../cross-platform/learn-about-mobile-development-with-xamarin.md) ke čtení a podívejte se na pozadí nezbytné materiálů.  
 
Pokud máte problémy s Xamarin po provedení tohoto nastavení a instalaci, vystavte tady svůj dotaz na [forums.xamarin.com](http://forums.xamarin.com/).
  
> [!NOTE]
>  Jak je 31. března 2016, všechny Xamarin je zahrnutá v všechny edice sady Visual Studio bez jakýchkoli nákladů a nemusí samostatné licence. Xamarin Studio Community Mac jsou rovněž bezplatná pro studenty, vývojáři operačních systémů a malé týmy. Poznámka: pro existující instalace sady Visual Studio, které jsou nakonfigurovány s dřívější licence Xamarin, musíte aktualizovat Xamarin verzi 4.0.3.214 nebo vyšší. Chcete-li to provést, přejděte na **nástroje > Možnosti > Xamarin > jiných**, klikněte na tlačítko **Zkontrolovat nyní** odkaz a stáhnout 4.0.3.214 aktualizovat. Při dalším spuštění Visual Studio, přejděte na **nástroje > Xamarin účtu...**  a měli byste vidět aktualizovaný stav.  
  
##  <a name="prereq"></a>Předpoklady  
  
###  <a name="for-targeting-windows-and-android"></a>Pro cílení na Windows a Android 
  
1.  Doporučená: fyzický Windows počítač (ne virtuální počítač) s Windows 8 nebo novější, pro nejlepší výkon emulátoru systému Android. (Jsme zmínili, je nutné, fyzický počítač a ne virtuální počítač?)  
  
2.  Můžete použít počítač se systémem Windows 7 nebo dřívější, v takovém případě budete používat Xamarin Player pro Android jako emulátor. 
    
3. Pro některé konfigurace možné vždy spouštět aplikace přímo na připojený fyzický zařízení.  
  
### <a name="for-targeting-ios"></a>Pro cílení na iOS  
  
1.  A síti Mac nebo Mac mini s systému macOS Sierra spuštěné systému macOS 10.12 nebo novější (požadováno pro Xcode 8.3).  
  
2.  Když pomocí sady Visual Studio v počítači s Windows (7 +) jako primární vývojového prostředí, je nutné, pouze při kompilaci a ladění aplikací pro iOS, připojit k simulátoru iOS nebo připojeného zařízení a používat návrháře storyboard v sadě Visual Studio pro síťově připojeného počítače Mac návrh uživatelského rozhraní. Starší modely Mac je zcela dostatečné pro tuto sekundární roli.  
  
##  <a name="windows"></a>Instalační program systému Windows (Visual Studio a Xamarin)  
  
> [!TIP]
>  Tyto pokyny platí pro Visual Studio 2017. Visual Studio 2015, najdete v části [MSDN](https://msdn.microsoft.com/en-us/library/mt613162.aspx). Použití Xamarin s Visual Studio 2013 (aktualizace 2 je vyžadována), postupujte podle pokynů pro [přímé instalace Xamarin](https://developer.xamarin.com/guides/cross-platform/getting_started/requirements/#install) (xamarin.com).  
  
1.  [Stáhněte a spusťte instalační program pro všechny edice Visual Studio 2017](https://www.visualstudio.com/downloads/) (Community, Professional a Enterprise). Visual Studio 2017 Community je bezplatná edice; edice Professional a Enterprise lze použít na základě zkušební verze po dobu 30 dnů, po které budete muset zakoupit licenci.  
  
    1.  Pokud již máte Visual Studio 2017 nainstalována, spusťte **instalační program Visual Studio** z **spustit** nabídky.
  
2.  V rámci instalačního programu, klikněte na **další možnosti** tlačítko (ikona tři řádky) _vedle_ **spusťte** zvolte **upravit**.:  
  
     ![Vyberete možnost upravit v instalaci sady Visual Studio](../cross-platform/media/cross-plat-xamarin-setup-1a.png "Cross-Plat Xamarin instalační 1")  
  
3.  Zkontrolujte následující pole:  
  
    1.  **Mobilní a herní > pro vývoj mobilních řešení s .NET**. To také automaticky vybere různé nástroje pro Android v rámci běžných nástrojů a Software Development Kit. Tato možnost by měl aktualizovat také případné existující instalace Xamarin.  
  
         ![Vyberte možnost vývoj mobilních řešení v rámci herní a vývoj mobilních řešení pro](../cross-platform/media/cross-plat-xamarin-setup-2a.png "Cross-Plat Xamarin instalace 2")  
  
    2. (Volitelné) **Windows > vývoj pro univerzální platformu Windows**. Tato zahrnout možnosti pro instalaci bitové kopie emulátorů, které bude trvat déle, než se stáhnout; vždy můžete vrátit do instalačního programu sady Visual Studio je přidat později. 
  
4.  Klikněte **upravit** tlačítko a nechat spustit proces. Znovu, bude to trvat delší dobu, během které doby můžete pokračovat s pokyny pro instalaci Mac a projít [Další informace o pro vývoj mobilních řešení s Xamarinem](../cross-platform/learn-about-mobile-development-with-xamarin.md).  
  
5.  Po dokončení instalace spusťte Visual Studio a přihlaste se pomocí účtu Microsoft po zobrazení výzvy (Toto je stejný účet, který použijete s Windows).  
      
6.  Pro testování aplikací pro Android, použijte [emulátoru Android SDK](https://developer.xamarin.com/guides/android/deployment,_testing,_and_metrics/debug-on-emulator/android-sdk-emulator/) Pokud nemáte fyzických zařízení. Viz poznámka níže.  
  
 **Poznámka o emulátorů na počítačích s Windows:** procesory podporují pouze jeden virtualizační technologie současně, je nejlepší mít jenom jeden používán na vývojovém počítači. Existují tři hlavní virtualizations, které patří technologie Hyper-V (používané emulátor sady Visual Studio pro Android a emulátoru Windows Phone), virtuální pole (používané Genymotion) a HAXM Intel (používá se emulátorem sady SDK pro Android). Je nejlepší používat emulátorů pouze jednoho z důvodu problémů s různými mezi Hyper-V a virtuální pole, zadejte na libovolného daného počítače, proto doporučení výše a používat Hyper-V v systému Windows 8 a vyšší počítače a emulátorů Intel HAXM na systému Windows 7 a starší, i když s Windows v počítačích Mac.  
  
##  <a name="mac"></a>Instalační program MAC (Apple ID, Xcode a Xamarin)  
  
1.  Vytvoření volné Apple ID na [https://appleid.apple.com](https://appleid.apple.com/) Pokud již nemáte. To je nezbytné pro instalaci a přihlášení k Xcode.  
  
2.  Stáhněte a nainstalujte Xcode z [https://developer.apple.com/xcode/](https://developer.apple.com/xcode/), a přidejte Apple ID, jak je popsáno na [přidání si účet na XCode](https://developer.apple.com/library/content/documentation/IDEs/Conceptual/AppStoreDistributionTutorial/AddingYourAccounttoXcode/AddingYourAccounttoXcode.html#//apple_ref/doc/uid/TP40013839-CH40-SW1) (apple.com).  
  
3.  Stáhněte a nainstalujte podle pokynů Xamarin [instalace a konfigurace Xamarin.iOS](http://developer.xamarin.com/guides/ios/getting_started/installation/mac/) (xamarin.com).  
  
4.  Po dokončení instalace Xamarin v počítačích se systémy Windows a Mac, postupujte podle pokynů [připojení k počítači Mac](http://developer.xamarin.com/guides/ios/getting_started/installation/windows/xamarin-mac-agent/) (xamarin.com), aby mohl pracovat s iOS a Mac ze sady Visual Studio v počítači s Windows.  
  
     Všimněte si, že oba počítače musí být ve stejné místní síti.