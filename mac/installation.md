---
title: Instalaci sady Visual Studio pro Mac | Microsoft Docs
description: "Pokyny k instalaci sady Visual Studio pro Mac a dalších komponent potřebných pro vývoj pro různé platformy."
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.technology: vs-ide-install
ms.assetid: 22B1F2CD-32AE-464D-80AC-C8AB4786B015
ms.openlocfilehash: 25d3227bcf8a18a2fc6ba68c194e9cac75b2e919
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
---
# <a name="setup-and-install-visual-studio-for-mac"></a>Instalační program a instalace sady Visual Studio pro Mac

## <a name="setup"></a>Instalace

Pro počáteční vývoj nativní, multiplatformní aplikace při existuje stažení sady Visual Studio pro Mac jsou několik věcí, které je nutné nainstalovat a nastavit v rámci přípravy.

Pro práci s iOS v sadě Visual Studio budete potřebovat následující:

* Mac s systému macOS Sierra 10.12 nebo vyšší
* Xcode 8.3
* Apple ID. Pokud nemáte Apple ID již můžete vytvořit novou v https://appleid.apple.com. Je potřeba mít Apple ID, instalace a přihlášení k Xcode.

## <a name="install"></a>Instalace

1. Stažení sady Visual Studio pro Mac od [https://www.visualstudio.com/](https://www.visualstudio.com/)

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
Pokud jste vybrali instalaci není platformy nebo nástroj při původní instalaci (podle unselecting ho v kroku #6), musíte spustit [instalační program](https://www.visualstudio.com/vs/) znovu Pokud chcete přidat součásti později.

## <a name="manual-installation"></a>Ruční instalace

Pokud vaše instalace selže nebo libovolné jedné součásti instalace se nezdaří, bude pravděpodobně možné vyřešit problém pomocí ruční instalace. K zobrazení požadované součásti a stáhnout každé z nich, proveďte následující kroky:

1. Na druhé obrazovce na instalační program Visual Studio, přejděte na panelu nabídek a vyberte **zobrazit pokyny k ruční instalaci**:

    ![Možnost zobrazující ruční instalaci položky nabídky](media/installer-image12.png)

2. Postupujte podle pokynů ke stažení a instalaci součástí ručně:

  ![Dialogové okno Ruční instalace](media/installer-image13.png)

## <a name="install-visual-studio-for-mac-behind-a-firewall-or-proxy-server"></a>Instalaci sady Visual Studio pro Mac za serverem brány firewall nebo proxy server

Nainstalujte sadu Visual Studio pro Mac za bránou firewall, musí být provedeny určité koncových bodů přístupný, aby bylo možné povolit stažení požadovaných nástrojů a aktualizace softwaru.

Konfigurace sítě pro povolení přístupu do následujícího umístění:

* [Koncové body Visual Studio](https://docs.microsoft.com/visualstudio/install/install-visual-studio-behind-a-firewall-or-proxy-server)