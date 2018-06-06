---
title: Instalační program sady Visual Studio pro Mac Tools for Unity
description: Nastavení a instalaci nástrojů pro Unity pro použití v sadě Visual Studio pro Mac
author: dantogno
ms.author: v-davian
ms.date: 05/25/2018
ms.assetid: 83FDD7A3-5D16-4B4B-9080-078E3FB5C623
ms.openlocfilehash: 18839ce37feb4f2a113c4a8875ce1c25ddba31e1
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34573268"
---
# <a name="setup-visual-studio-for-mac-tools-for-unity"></a>Instalační program sady Visual Studio pro Mac Tools for Unity

Tato část vysvětluje, jak začít pracovat, pomocí sady Visual Studio pro Mac Tools for Unity.

## <a name="install-visual-studio-for-mac"></a>Instalaci sady Visual Studio pro Mac

### <a name="unity-bundled-installation"></a>Unity dodávat instalace

Počínaje Unity 2018.1, Visual Studio pro Mac je výchozí nastavení IDE C# pro Unity a je součástí Pomocníka pro stažení Unity, stejně jako nástroj pro instalaci Unity rozbočovače. Stáhnout Unity z [store.unity.com](https://store.unity.com/).

Během instalace Ujistěte se, že je v seznamu součástí k instalaci pomocí Unity zaškrtnuté Visual Studio pro Mac:

#### <a name="unity-hub"></a>Unity rozbočovače

![instalace rozbočovače Unity](media/setup-vsmac-tools-unity-image7.png)

#### <a name="unity-download-assistant"></a>Pomocník pro stažení Unity

![Instalace Pomocníka stažení Unity](media/setup-vsmac-tools-unity-image8.png)

#### <a name="check-for-updates-to-visual-studio-for-mac"></a>Vyhledávat aktualizace pro Visual Studio pro Mac

Verze sady Visual Studio pro Mac součástí Unity instalace nemusí být nejnovější. Doporučujeme zkontrolovat aktualizace Ujistěte se, že máte přístup k nejnovější nástroje a funkce.

* [Aktualizace sady Visual Studio pro Mac](update.md)

### <a name="manual-installation"></a>Ruční instalace

Pokud již máte Unity 5.6.1 nebo vyšší, ale nemáte Visual Studio pro Mac, Visual Studio pro Mac můžete nainstalovat ručně. Všechny edice sady Visual Studio pro Mac jsou seskupeny pomocí sady Visual Studio pro Mac Tools for Unity, včetně bezplatná edice Community:

* Stažení sady Visual Studio pro Mac od [visualstudio.com](https://www.visualstudio.com/).
* Visual Studio pro Mac Tools for Unity instalují automaticky během procesu instalace.
* Postupujte podle kroků v [Průvodce instalací](installation.md) nápovědu k další instalaci.

> [!NOTE]
> Visual Studio pro Mac Tools for Unity vyžaduje Unity verze 5.6.1 nebo vyšší. Pokud chcete ověřit, že Visual Studio Tools for Unity jsou povoleny ve vaší verzi Unity, vyberte **o Unity** z nabídky Unity a podívejte se na text "sady Microsoft Visual Studio nástroje pro Unity povoleno" v levém dolním dialogového okna.
>
> ![O Unity](media/setup-vsmac-tools-unity-image3.png)

## <a name="confirm-that-the-visual-studio-for-mac-tools-for-unity-extension-is-enabled"></a>Zkontrolujte, zda je povoleno sady Visual Studio pro Mac Tools for Unity rozšíření

Při sady Visual Studio pro Mac Tools for Unity rozšíření by měl být ve výchozím nastavení povolené, můžete to ověřit a zkontrolujte číslo nainstalovaná verze:

1. V nabídce sady Visual Studio vyberte **rozšíření...** .

  ![Vyberte rozšíření](media/setup-vsmac-tools-unity-image1.png)

1. Rozbalte část herní vývoj a potvrďte sady Visual Studio pro Mac nástroje pro položku Unity.

  ![Položka Unity zobrazení](media/setup-vsmac-tools-unity-image2.png)

## <a name="configure-unity-for-use-with-visual-studio-for-mac"></a>Konfigurace Unity pro použití se sadou Visual Studio pro Mac

Počínaje Unity 2018.1, Visual Studio by měl být výchozí editor externího skriptu aplikace Unity. Můžete to ověřit nebo změnit editoru externího skriptu pro Visual Studio:

1. Vyberte **předvolby...**  z nabídky Unity.

  ![Vyberte předvolby](media/setup-vsmac-tools-unity-image4.png)

1. V dialogovém okně Předvolby vyberte **externích nástrojů** kartě.

1. Z externího skriptu Editor rozevíracího seznamu vyberte **Visual Studio** Pokud je hodnota uvedena, v opačném případě vyberte **Procházet...** .

  ![Vyberte sady Visual Studio](media/setup-vsmac-tools-unity-image5.png)

1. Pokud **Procházet...**  byla vybrána, přejděte do adresáře aplikace a vyberte sady Visual Studio a pak klikněte na tlačítko **otevřete**.

  ![Vyberte Otevřít](media/setup-vsmac-tools-unity-image6.png)

1. Po výběru v sadě Visual Studio **Editor skriptů externí** seznamu, zavřete dialogové okno Předvolby pro dokončení procesu konfigurace.
