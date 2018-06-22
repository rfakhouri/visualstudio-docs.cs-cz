---
title: Instalaci sady Visual Studio pro Mac
description: Pokyny k instalaci sady Visual Studio pro Mac a dalších komponent potřebných pro vývoj pro různé platformy.
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.technology: vs-ide-install
ms.assetid: 22B1F2CD-32AE-464D-80AC-C8AB4786B015
ms.openlocfilehash: 416d82b7325ffa4a9952630e4c1ca9b5fbc7834e
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/20/2018
ms.locfileid: "36280491"
---
# <a name="setup-and-install-visual-studio-for-mac"></a>Instalační program a instalace sady Visual Studio pro Mac

## <a name="setup"></a>Instalace

Pro počáteční vývoj nativní, multiplatformní aplikace při existuje stažení sady Visual Studio pro Mac jsou několik věcí, které je nutné nainstalovat a nastavit v rámci přípravy.

Pro práci s iOS v sadě Visual Studio budete potřebovat následující:

* Mac s systému macOS Sierra 10.12 nebo vyšší
* Xcode 8.3 nebo vyšší. Obvykle se doporučuje nejnovější stabilní verze.
* Apple ID. Pokud nemáte Apple ID již můžete vytvořit novou v https://appleid.apple.com. Je potřeba mít Apple ID, instalace a přihlášení k Xcode.

## <a name="install"></a>Instalace

1. Stažení sady Visual Studio pro Mac z [https://visualstudio.microsoft.com/](https://visualstudio.microsoft.com/)

2. Po stažení balíčku Instalační služby, klikněte na **VisualStudioInstaller.dmg** souboru připojit instalační program a pak spusťte dvojitým kliknutím na soubor logo, které jsou popsány v následující obrázek:

  ![Instalační program dialogové okno](media/installer-image1.png)

3. Může se zobrazit výzva s dialogového okna výstrah podobně jako na následujícím obrázku. V takovém případě klikněte na tlačítko **otevřete**:

  ![dialogového okna výstrah](media/installer-image2.png)

4. Instalační program zkontroluje systému a ověřte součástí, které je třeba nainstalovat nebo aktualizovat:

  ![Vyhodnocení systému](media/installer-image3.png)

5. Zobrazí se pak uvedené pomocí dialogového okna výstrah s žádostí o potvrzení o ochraně osobních údajů a licenční podmínky. Stiskněte **pokračovat** tlačítko Potvrdit podmínky:

  ![Dialogové okno licencí](media/installer-image4.png)

6. Instalační program zobrazí seznam požadovaných součástí, které chybí a které je potřeba stáhli a nainstalovali. Vyberte produkty, které chcete stáhnout zde:

  ![Vyberte položky](media/installer-image5.png)

  Pokud nechcete, aby k instalaci všech platformách, použijte Průvodce níže vám pomohou rozhodnout platforem, které nainstalovat:

  * **Aplikace pomocí Xamarinu**:
      - Xamarin.Forms – vyberte **Android** a **iOS** platformy.
      - iOS vybrat pouze – **iOS** platformy (Všimněte si, že budete muset nainstalovat [ **Xcode**](https://developer.apple.com/xcode/)).
      - Android vybrat pouze – **Android** platformy (Všimněte si, že byste měli také vybrat relevantní závislosti).
      - Mac vybrat pouze – **systému macOS** platformy (Všimněte si, že budete muset nainstalovat [ **Xcode**](https://developer.apple.com/xcode/)).
      - Vyberte aplikace Xamarin plně napříč platformami – **Android**, **iOS**, a **systému macOS** platformy.
  * **Aplikace .NET core** – vyberte **.NET Core** platformy.
  * **Webové aplikace ASP.NET Core** – vyberte **.NET Core** platformy.
  * **Vývoj pro různé platformy Unity herní** – žádné další platformy je potřeba nainstalovat překračuje Visual Studio for Mac. Odkazovat [Průvodce nastavením Unity](setup-vsmac-tools-unity.md) Další informace o instalaci rozšíření Unity.

  Tato obrazovka instalace zobrazí verze a velikosti jednotlivých součástí. Můžete kliknutím na jednotlivé komponenty, chcete-li zobrazit seznam závislosti pro tuto součást (pro Android), najdete v části Další balíčky, které stáhne (pro .NET Core), nebo zobrazit žádné další aplikace, které jsou vyžadované (pro iOS a systému macOS):

  ![Android Další závislosti](media/installer-image6.png)

7. Jakmile budete s výběrem radostí, vyberte **instalace a aktualizace** tlačítko spuštění procesu instalace.

8. Instalační program spustí stahování a instalaci procesů vybrané položky:

  ![Při spouštění instalace](media/installer-image7.png)

  ![Stahování Xamarin.Mac](media/installer-image8.png)

  ![Dokončení instalace](media/installer-image9.png)

9. Můžete být vyzváni k zvýšení oprávnění, které jsou nezbytné pro jednotlivé součásti, které jsou potřebné k dokončení instalace. Chcete-li pokračovat v procesu instalace, zadejte pověření správce:

  ![Zadejte oprávnění pokračujte s instalačním programem](media/installer-image10.png)

10. Po úspěšné instalace můžete začít vyvíjet aplikace v sadě Visual Studio stisknutím **spustit**:

  ![Otevřete Visual Studio](media/installer-image11.png)

> [!NOTE]
Pokud jste vybrali instalaci není platformy nebo nástroj při původní instalaci (podle unselecting ho v kroku #6), musíte spustit [instalační program](https://visualstudio.microsoft.com/vs/) znovu Pokud chcete přidat součásti později.


## <a name="install-visual-studio-for-mac-behind-a-firewall-or-proxy-server"></a>Instalaci sady Visual Studio pro Mac za serverem brány firewall nebo proxy server

Nainstalujte sadu Visual Studio pro Mac za bránou firewall, musí být provedeny určité koncových bodů přístupný, aby bylo možné povolit stažení požadovaných nástrojů a aktualizace softwaru.

Konfigurace sítě pro povolení přístupu do následujícího umístění:

* [Koncové body Visual Studio](/visualstudio/install/install-visual-studio-behind-a-firewall-or-proxy-server)

## <a name="next-steps"></a>Další kroky

Instalace sady Visual Studio pro Mac, můžete zahájit zápis kódu pro vaše aplikace. Následující příručky jsou k dispozici pro vás provede další kroky psaní a nasazení vašich projektů.

### <a name="ios"></a>iOS

1. [Hello, iOS](https://developer.xamarin.com/guides/ios/getting_started/hello,_iOS/)
2. [Zřizování zařízení](https://developer.xamarin.com/guides/ios/getting_started/installation/device_provisioning)(ke spuštění aplikace na zařízení).


### <a name="android"></a>Android

1. [Pomocí Xamarin Android SDK Manager](https://developer.xamarin.com/guides/android/getting_started/installation/android-sdk/?ide=xs)
2. [Emulátor sady Android SDK](https://developer.xamarin.com/guides/android/getting_started/installation/android-emulator/)
4. [Nastavení zařízení pro vývoj](https://developer.xamarin.com/guides/android/getting_started/installation/set_up_device_for_development/)

### <a name="net-core-apps-aspnet-core-web-apps-unity-game-development"></a>Aplikace .NET core, webové aplikace ASP.NET Core, vývoj her pro Unity

Další úlohy, najdete v části [úlohy](workloads.md) stránky.
