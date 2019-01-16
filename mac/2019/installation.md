---
title: Nainstalujte Visual Studio 2019 for Mac Preview
description: Pokyny k instalaci. 2019 Visual Studio pro Mac ve verzi Preview a další komponenty potřebné pro vývoj pro různé platformy.
author: conceptdev
ms.author: crdun
ms.date: 11/03/2018
ms.technology: vs-ide-install
ms.assetid: 22B1F2CD-32AE-464D-80AC-C8AB4786B015
ms.openlocfilehash: acd8f3bc4f5fefa0a0c8b273856579067fb33c6a
ms.sourcegitcommit: 5a65ca6688a2ebb36564657d2d73c4b4f2d15c34
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/15/2019
ms.locfileid: "54316193"
---
# <a name="install-visual-studio-2019-for-mac-preview"></a>Nainstalujte Visual Studio 2019 for Mac Preview

> [!NOTE]
> 2019 Visual Studio pro Mac ve verzi preview se dá instalovat vedle sebe s nejnovější stabilní verze sady Visual Studio pro Mac. Během instalace budete vyzváni k aktualizaci existující sady Visual Studio, pokud není nejnovější stabilní verzi.

## <a name="requirements-for-the-visual-studio-2019-for-mac-preview"></a>Požadavky pro Visual Studio 2019 for Mac preview

- Počítač Mac s macOS 10.13 vysokou Sierra nebo vyšší.

K vytváření aplikací Xamarin pro iOS nebo macOS, budete také potřebovat:

- Xcode 10.0 nebo vyšší. Nejnovější stabilní verze je obvykle vhodné.
- Apple ID. Pokud ještě nemáte Apple ID můžete vytvořit nový na https://appleid.apple.com. Je potřeba mít Apple ID, instalace a přihlášení do Xcode.

## <a name="installing-the-preview"></a>Instalace verze preview

1. Stažení instalačního programu preview z [Visual Studio for Mac preview stránky](https://aka.ms/vs4mac-preview).
2. Po dokončení stahování klikněte na tlačítko **VisualStudioforMacPreviewInstaller.dmg** připojit instalační program, spusťte jej dvojitým kliknutím šipku logo:

    [![Klikněte na šipku velké k zahájení instalace](media/install-preview-installer-sml.png)](media/install-preview-installer.png#lightbox)

3. Vám může se vám upozornění týkající se aplikace stahuje z Internetu. Klikněte na tlačítko **otevřít**.
4. Počkejte, než instalační program zkontroluje počítač:

    [![Instalační program zkontroluje váš systém nainstalované součásti.](media/install-preview-checking-sml.png)](media/install-preview-checking.png#lightbox)

5. Upozornění se zobrazí s výzvou k potvrzení o ochraně osobních údajů a licenční podmínky. Použijte odkazy, přečtěte si je a pak stiskněte klávesu **pokračovat** Pokud souhlasíte s tím:

    [![Na odkazech na ochranu osobních údajů a podmínky a potom pokračovat, souhlasíte s](media/install-preview-privacy-sml.png)](media/install-preview-privacy.png#lightbox)

6. Zobrazí se seznam dostupných úloh. Vyberte ty, které chcete použít:

    [![Zvolte nepovinné úlohy funkcí, které chcete nainstalovat](media/install-preview-selection-sml.png)](media/install-preview-selection.png#lightbox)

    Pokud vaše aktuální Visual Studio 2017 for Mac je starší než verze 7.7, zobrazí výzva ke schválení upgrade na nejnovější stabilní verze (která je nezbytná pro podporu instalace vedle sebe). Stisknutím klávesy **pokračovat** schválit upgradu:

    ![Upgrade stabilní verzi 7.7 je povinný](media/install-preview-older-upgrade.png)

7. Po provedení výběru, stiskněte **nainstalovat** tlačítko.
8. Instalační program se zobrazí průběh, stáhne a nainstaluje sadu Visual Studio pro Mac a vybrané úlohy. Vám může zobrazit výzva k zadání hesla k udělení oprávnění pro instalaci.
9. Použití **sady Visual Studio (Preview)** kdykoli budete chtít otestovat verzi preview, nebo přepněte zpátky na nejnovější stabilní sady Visual Studio pro práci produkčního prostředí. Zde jsou uvedeny dvě ikony:

    ![Ikona rozdíly stabilní verze a preview](media/install-preview-icons-sml.png)

Pokud máte potíže s sítě při instalaci v podnikovém prostředí, přečtěte si [instalace za bránou firewall nebo proxy](https://docs.microsoft.com/visualstudio/mac/installation#install-visual-studio-for-mac-behind-a-firewall-or-proxy-server) pokyny.

Další informace o změnách v [poznámky k verzi](https://docs.microsoft.com/visualstudio/releasenotes/vs2019-mac-preview-relnotes).

> [!NOTE]
> Pokud zvolíte ne nainstalovat platformu nebo nástroj při původní instalaci (zrušením výběru ho v kroku #6), je nutné instalační program znovu spustit, pokud budete chtít později přidat komponenty.

## <a name="install-visual-studio-for-mac-behind-a-firewall-or-proxy-server"></a>Instalace sady Visual Studio pro Mac za bránou firewall nebo proxy serverem

Instalace sady Visual Studio pro Mac za bránou firewall, některé koncové body musí být přístupné umožní se soubory ke stažení potřebné nástroje a aktualizací softwaru.

Konfigurace sítě pro povolení přístupu do následujících umístění:

- [Visual Studio koncových bodů](/visualstudio/install/install-visual-studio-behind-a-firewall-or-proxy-server)

## <a name="next-steps"></a>Další kroky

Instalace sady Visual Studio for Mac umožňuje začít psát kód pro vaše aplikace. Následující pokyny jsou k dispozici pro vás provedou další kroky vytváření a nasazování vašich projektů.

### <a name="ios"></a>iOS

1. [Hello, iOS](https://developer.xamarin.com/guides/ios/getting_started/hello,_iOS/)
2. [Zřizování zařízení](https://developer.xamarin.com/guides/ios/getting_started/installation/device_provisioning)(pro spuštění vaší aplikace na zařízení).

### <a name="android"></a>Android

1. [Pomocí Xamarin Android SDK Manager](https://developer.xamarin.com/guides/android/getting_started/installation/android-sdk/?ide=xs)
2. [Emulátor sady Android SDK](https://developer.xamarin.com/guides/android/getting_started/installation/android-emulator/)
4. [Nastavení zařízení pro vývoj](https://developer.xamarin.com/guides/android/getting_started/installation/set_up_device_for_development/)

### <a name="net-core-apps-aspnet-core-web-apps-unity-game-development"></a>Aplikace .NET core, ASP.NET Core webových aplikací, vývoj her pro Unity

Další úlohy, najdete [úlohy](/visualstudio/mac/workloads) stránky.

## <a name="see-also"></a>Viz také:

- [Instalace sady Visual Studio 2017 (ve Windows)](/visualstudio/install/install-visual-studio)
