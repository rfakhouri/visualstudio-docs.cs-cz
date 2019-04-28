---
title: Install Visual Studio 2019 for Mac
description: Pokyny k instalaci. 2019 Visual Studio pro Mac a další komponenty potřebné pro vývoj pro různé platformy.
author: conceptdev
ms.author: crdun
ms.date: 04/02/2019
ms.technology: vs-ide-install
ms.assetid: 22B1F2CD-32AE-464D-80AC-C8AB4786B015
ms.custom: video
ms.openlocfilehash: b56d7d97ec49bf4c83f2d26a38648cd22cdcfe6a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62982949"
---
# <a name="install-visual-studio-2019-for-mac"></a>Install Visual Studio 2019 for Mac

Jak začít s vývojem nativní a multiplatformní aplikace .NET v systému macOS, nainstalujte Visual Studio 2019 pro Mac níže uvedeného postupu.

## <a name="requirements"></a>Požadavky

- Počítač Mac s macOS Sierra 10.12 vysoké nebo vyšší.

K vytváření aplikací Xamarin pro iOS nebo macOS, budete také potřebovat:

- Xcode 10.0 nebo vyšší. Nejnovější stabilní verze je obvykle vhodné.
- Apple ID. Pokud ještě nemáte Apple ID můžete vytvořit nový na https://appleid.apple.com. Je potřeba mít Apple ID, instalace a přihlášení do Xcode.

## <a name="installation-instructions"></a>Pokyny k instalaci

1. Stažení instalačního programu z [Visual Studio for Mac stránku pro stažení](https://aka.ms/vsmac).
2. Po dokončení stahování klikněte na tlačítko **VisualStudioforMacInstaller.dmg** připojit instalační program, spusťte jej dvojitým kliknutím šipku logo:

    [![Klikněte na šipku velké k zahájení instalace](media/install-installer-sml.png)](media/install-installer.png#lightbox)

3. Vám může se vám upozornění týkající se aplikace stahuje z Internetu. Klikněte na tlačítko **otevřít**.
4. Počkejte, než instalační program zkontroluje počítač:

    [![Instalační program zkontroluje váš systém nainstalované součásti.](media/install-checking-sml.png)](media/install-checking.png#lightbox)

5. Upozornění se zobrazí s výzvou k potvrzení o ochraně osobních údajů a licenční podmínky. Použijte odkazy, přečtěte si je a pak stiskněte klávesu **pokračovat** Pokud souhlasíte s tím:

    [![Na odkazech na ochranu osobních údajů a podmínky a potom pokračovat, souhlasíte s](media/install-privacy-sml.png)](media/install-privacy.png#lightbox)

6. Zobrazí se seznam dostupných úloh. Vyberte ty, které chcete použít:

    [![Zvolte nepovinné úlohy funkcí, které chcete nainstalovat](media/install-selection-sml.png)](media/install-selection.png#lightbox)

7. Po provedení výběru, stiskněte **nainstalovat** tlačítko.
8. Instalační program se zobrazí průběh, stáhne a nainstaluje sadu Visual Studio pro Mac a vybrané úlohy. Vám může zobrazit výzva k zadání hesla k udělení oprávnění pro instalaci.

Pokud máte potíže s sítě při instalaci v podnikovém prostředí, přečtěte si [instalace za bránou firewall nebo proxy](https://docs.microsoft.com/visualstudio/mac/installation#install-visual-studio-for-mac-behind-a-firewall-or-proxy-server) pokyny.

Další informace o změnách v [poznámky k verzi](https://docs.microsoft.com/visualstudio/releasenotes/vs2019-mac-relnotes).

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

## <a name="related-video"></a>Související videa

> [!Video https://channel9.msdn.com/Shows/Visual-Studio-Toolbox/Visual-Studio-for-Mac-Acquisition/player]

## <a name="see-also"></a>Viz také:

- [Instalace sady Visual Studio (ve Windows)](/visualstudio/install/install-visual-studio)
