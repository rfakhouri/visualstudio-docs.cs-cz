---
title: Instalační program sady Visual Studio pro Mac Tools for Unity
author: dantogno
ms.author: v-davian
ms.date: 07/17/2017
ms.assetid: 83FDD7A3-5D16-4B4B-9080-078E3FB5C623
ms.openlocfilehash: a1d6d523de9a5a57cf6b4c696a68dbdde1428156
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="setup-visual-studio-for-mac-tools-for-unity"></a>Instalační program sady Visual Studio pro Mac Tools for Unity

Tato část vysvětluje, jak začít pracovat, pomocí sady Visual Studio pro Mac Tools for Unity.

## <a name="install-visual-studio-for-mac"></a>Instalaci sady Visual Studio pro Mac

Stažení a instalaci sady Visual Studio for Mac. Všechny edice sady Visual Studio pro Mac podporují Visual Studio pro Mac Tools for Unity, včetně bezplatná edice Community:

* Stažení sady Visual Studio pro Mac od [visualstudio.com](https://www.visualstudio.com/).
* Visual Studio pro Mac Tools for Unity instalují automaticky během procesu instalace.
* Postupujte podle kroků v [Průvodce instalací](/visualstudio/mac/installation) nápovědu k další instalaci.

## <a name="confirm-that-the-visual-studio-for-mac-tools-for-unity-extension-is-enabled"></a>Zkontrolujte, zda je povoleno sady Visual Studio pro Mac Tools for Unity rozšíření

Při sady Visual Studio pro Mac Tools for Unity rozšíření by měl být ve výchozím nastavení povolené, můžete to ověřit a zkontrolujte číslo nainstalovaná verze:

1.  V nabídce sady Visual Studio vyberte **rozšíření...** .

  ![Vyberte rozšíření](media/setup-vsmac-tools-unity-image1.png)

2.  Rozbalte část herní vývoj a potvrďte sady Visual Studio pro Mac nástroje pro položku Unity.

  ![Položka Unity zobrazení](media/setup-vsmac-tools-unity-image2.png)

## <a name="install-unity"></a>Nainstalujte Unity

Visual Studio pro Mac Tools for Unity vyžaduje Unity verze 5.6.1 nebo vyšší. Všechny plány Unity pracovat s Visual Studio Tools for Unity, včetně osobních plánu úrovně free. Stáhnout Unity z [store.unity.com](https://store.unity.com/).

> [!NOTE]
> Pokud chcete ověřit, že Visual Studio Tools for Unity jsou povoleny ve vaší verzi Unity, vyberte **o Unity** z nabídky Unity a podívejte se na text "sady Microsoft Visual Studio nástroje pro Unity povoleno" v levém dolním dialogového okna.
>
>   ![O Unity](media/setup-vsmac-tools-unity-image3.png)

## <a name="configure-unity-for-use-with-visual-studio-for-mac"></a>Konfigurace Unity pro použití se sadou Visual Studio pro Mac

Visual Studio musí být nastavena jako editor externího skriptu v Unity:

1.  Vyberte **předvolby...**  z nabídky Unity.

  ![Vyberte předvolby](media/setup-vsmac-tools-unity-image4.png)

2.  V dialogovém okně Předvolby vyberte **externích nástrojů** kartě.

3.  Z externího skriptu Editor rozevíracího seznamu vyberte **Visual Studio** Pokud je hodnota uvedena, v opačném případě vyberte **Procházet...** .

  ![Vyberte sady Visual Studio](media/setup-vsmac-tools-unity-image5.png)

4.  Pokud **Procházet...**  byla vybrána, přejděte do adresáře aplikace a vyberte sady Visual Studio a pak klikněte na tlačítko **otevřete**.

  ![Vyberte Otevřít](media/setup-vsmac-tools-unity-image6.png)

5.  Po výběru v sadě Visual Studio **Editor skriptů externí** seznamu, zavřete dialogové okno Předvolby pro dokončení procesu konfigurace.
