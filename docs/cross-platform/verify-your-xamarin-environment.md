---
title: Ověřte prostředí Xamarin | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.topic: conceptual
ms.assetid: fd39882e-06d1-4b39-80d2-4d07b6e4f8f5
ms.technology: vs-ide-mobile
author: charlespetzold
ms.author: chape
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: 862af0d8912811aee8e0110b48fa8cc3e8f1c06b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="verify-your-xamarin-environment"></a>Ověřte prostředí Xamarin

Po dokončení instalační programy (viz [nastavení a instalaci](../cross-platform/setup-and-install.md)), věnovat několik minut, ověřte, zda je vše připraveno prostředí vývoj na platformě Xamarin.  
  
 Po dokončení ověření instalace zkuste jednu nebo obě následující kurzy:  
  
-   [Další informace základy vytváření aplikací s Xamarin.Forms v sadě Visual Studio](../cross-platform/learn-app-building-basics-with-xamarin-forms-in-visual-studio.md) sestavit aplikaci Xamarin.Forms.
  
-   [Vývoj aplikací s nativní uživatelského rozhraní v sadě Visual Studio pomocí Xamarin](../cross-platform/build-apps-with-native-ui-using-xamarin-in-visual-studio.md) používat nativní uživatelského rozhraní na jednotlivých platformách ale sdílet nějaký kód v rozhraní .NET standardní knihovně.
  
## <a name="all-platforms"></a>Všechny platformy 
 
V sadě Visual Studio, vyberte nejdřív **nástroje > rozšíření a aktualizace** a zaškrtněte políčko, pokud některé z těchto komponent Xamarin vyžadovat aktualizace.  
  
Pak vytvořte nové řešení Xamarin.Forms v sadě Visual Studio pomocí **soubor > Nový projekt**. V dialogovém okně rozbalte **Visual C# > napříč platformami**, vyberte **mobilní aplikace (Xamarin.Forms)**a klikněte na tlačítko OK. V dialogovém okně, který následuje, vyberte **prázdnou aplikaci**. V části **strategie sdílení kódu**, vyberte **.NET Standard**. Klikněte na tlačítko OK.

Tyto akce vytvoření řešení s čtyři projekty: sdílené projektu knihovny standardní rozhraní .NET 2.0 a projekty aplikací pro Android, iOS a univerzální platformu Windows (UWP):  
  
![Výsledky vytvoření nového projektu z šablony prázdnou aplikaci Xamarin.Forms](../cross-platform/media/crossplat-xamarin-verify-1.png "CrossPlat Xamarin ověřte 1")  
   
## <a name="android"></a>Android  
  
1. Zkontrolujte, že máte nejnovější Android SDK nástroje nainstalované přechodem na **nástroje > Android > Android SDK Manager**. Nainstalujte nejnovější verze nástroje pro Android SDK, nástroje pro platformu Android SDK a nástroje sestavení Android SDK. Není potřeba vždycky nainstalovat nejnovější úroveň rozhraní API systému Android. Úroveň rozhraní API, které potřebujete, závisí na úrovni platformy, které chcete zacílit. Obecně platí instalace platformě Xamarin nainstaluje úroveň platformu Android, která vyžaduje.  
  
2.  Ověření, sestavování a ladění na emulátoru nebo zařízení:  
  
    -   Klikněte pravým tlačítkem na projekt pro Android v Průzkumníku řešení a vyberte **nastavit jako spouštěný projekt**.  
  
    -   Na panelu nástrojů měli byste vidět rozevírací seznam obsahující seznam zařízení se systémem Android k dispozici a emulátorů. 
    
    Zařízení se systémem Android musí být povolen pro ladění v možnosti pro vývojáře stránky nastavení zařízení USB. Zařízení je pak připojený k počítači pomocí kabelu USB. 
    
    Emulátorů jsou také uvedeny. Vyberte jednu z zařízení nebo emulátorů Visual Studio:

  ![Výběr emulátor sady Visual Studio pro Android jako cíl ladění](../cross-platform/media/crossplat-xamarin-verify-3.png "CrossPlat Xamarin ověřte 3")  
  
  Podrobnější informace najdete v části [emulátor představení sady Visual Studio pro Android](http://blogs.msdn.com/b/visualstudioalm/archive/2014/11/12/introducing-visual-studio-s-emulator-for-android.aspx) (Visual Studio ALM blog). Pokud narazíte na problémy získávání emulátor fungovat, najdete v článku [řešení potíží s Visual Studio Emulator for Android](../cross-platform/troubleshooting-the-visual-studio-emulator-for-android.md). Můžete také vytvořit nové profily zařízení pro emulátor výběrem **nástroje > Android > Správce emulátoru Android**.  
  
3. Stisknutím klávesy F5 a nasazení programu na emulátoru nebo zařízení s Androidem.
  
## <a name="windows"></a>Windows 
  
1.  Universal Windows project v Průzkumníku řešení klikněte pravým tlačítkem a vyberte **nastavit jako spouštěný projekt**.  

2.  V **platformy řešení** rozevíracího seznamu, vyberte **x86** nebo **x64**. Vyberte **místního počítače**.

3.  Stisknutím klávesy F5 nasazení programu na ploše.
  
## <a name="ios"></a>iOS  
  
1.  Zkontrolujte, že počítač Mac je dostupný v síti a spárované sadou Visual Studio, jak je popsáno na [připojení k počítači Mac](/xamarin/ios/get-started/installation/windows/connecting-to-mac/).  
  
2.  Klikněte pravým tlačítkem na projekt pro iOS v Průzkumníku řešení a vyberte **nastavit jako spouštěný projekt**.  
  
3.  Vyberte **iPhoneSimulator** cíle ze sestavení sady Visual Studio rozevíracího seznamu, jak je uvedeno níže, nebo **iPhone** cíle, pokud máte zařízení uvazována pro Mac.   
  
 ![Výběr iPhoneSimulator sestavení cíl](../cross-platform/media/crossplat-xamarin-verify-5.png "CrossPlat Xamarin ověřte 5") 

 Pokud nejsou uvedeny žádné simulátorů, spusťte na počítači Mac, vyberte Xcode **Xcode > Předvolby**a klikněte na tlačítko **Stáhnout**. V části **součásti** záhlaví jste měli vidět simulátoru verze, které jsou k dispozici ke stažení. Další pokyny pro ladění naleznete na [iOS ladění](/xamarin/ios/deploy-test/debugging-in-xamarin-ios/?tabs=vsmac#Debugging_on_the_Simulator) stránky.
  
4.  Cíl zařízení emulátoru, vyberte z rozevíracího seznamu v sadě Visual Studio:

 ![Výběr cíli ladění iPhone](../cross-platform/media/crossplat-xamarin-verify-6.png "CrossPlat Xamarin ověřte 6")

5. Stisknutím klávesy F5 spusťte ladicího programu. Simulátor se spustí v systému Mac, kde budete pracovat s aplikací, při ladění se stane v sadě Visual Studio. Pokud máte fyzického zařízení iPhone nebo iPad připojené k počítači Mac, zobrazí se v seznamu a můžete ji vybrat místo. Pokud se nezobrazí žádné zařízení nebo simulátorů uvedené, zkontrolujte připojení k Mac. Přečtěte si článek propojené ve výše uvedeném kroku 1, nebo přejít na **nástroje > iOS > pár pro Mac**  
  
6.  Pokud narazíte na potíže s připojením k počítači Mac, přečtěte si [odstraňování problémů s připojením](/xamarin/ios/get-started/installation/windows/connecting-to-mac/troubleshooting/).  
  
7.  Pokud se zobrazí chyba s oznámením "žádné nainstalované zřizovacích profilů odpovídat nainstalované iOS podpisových klíčů", zkuste následující návrhy:  
  
  - Zkontrolujte, že váš účet Apple Id je přidaný do Xcode na počítači Mac, jak je popsáno na [přidání si účet na Xcode](https://developer.apple.com/library/content/documentation/IDEs/Conceptual/AppStoreDistributionTutorial/AddingYourAccounttoXcode/AddingYourAccounttoXcode.html#//apple_ref/doc/uid/TP40013839-CH40-SW1) (apple.com).  Po přidání účtu, je nutné restartovat Visual Studio a Xcode.  
    
  - Ověřte v iOS sady vlastností projektu v iOS podpisový kartě, že vlastní pole nárocích je prázdná pro konfiguraci ladění active.  Poznámka: pouze vyzkoušejte odebrání toto nastavení, pokud byla zjištěna výše chybová zpráva.  
  
  ![CrossPlat Xamarin ověřte 8](../cross-platform/media/crossplat-xamarin-verify-8.png "CrossPlat Xamarin ověřte 8")  
