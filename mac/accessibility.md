---
title: Usnadnění
description: Tento článek představuje funkce pro usnadnění přístupu v sadě Visual Studio pro Mac a jak lze povolit.
author: conceptdev
ms.author: crdun
ms.date: 04/17/2019
ms.assetid: 2C4AAC2E-3B4A-4496-8BE0-1F5A7F81D1CA
ms.openlocfilehash: 0ee6ffc7bd1567a86bc361f55e00c52ccecddd61
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/11/2019
ms.locfileid: "67824451"
---
# <a name="accessibility"></a>Usnadnění

Visual Studio for Mac obsahuje následující funkce pro usnadnění přístupu, tak přístupnější pro osoby s různými schopnostmi:

- Rozšíření text v řešení a editor dotyková zařízení
- Možnosti změnit velikost textu v editorech
- Přizpůsobení barev v editorech
- Procházení pomocí klávesnice
- Vlastní místní nastavení
- Doplňování kódu pro metody a parametrů

Kromě těchto funkcí Apple poskytuje několik nástrojů, které pomáhají uživatelům se zvláštními potřebami, jako je VoiceOver a diktování.

Další informace o funkce pro usnadnění přístupu v systému macOS najdete v tématu [webu společnosti Apple](https://www.apple.com/accessibility/mac/).

## <a name="enabling-macos-assistive-technologies-in-visual-studio-for-mac"></a>Povolení macOS technologie pro usnadnění v sadě Visual Studio pro Mac

Visual Studio for Mac – podpora pro technologie pro usnadnění macOS je vypnuto ve výchozím nastavení. Ho Pokud chcete povolit, postupujte takto:

1. Přejděte na **sady Visual Studio (nabídka) > Předvolby > Další > usnadnění přístupu**

2. Zkontrolujte **povolit usnadnění** zaškrtávací políčko:

   ![Zaškrtávací políčko předvolby usnadnění](media/accessibility-preferences.png)

3. Vyberte **restartujte Visual Studio** tlačítko a restartujte aplikaci Visual Studio a povolit podporu pro technologie pro usnadnění společnosti Apple.

## <a name="how-to-use-keyboard-navigation"></a>Postupy: Navigace pomocí klávesnice

Podpora navigačního klávesnice je integrována do macOS, ale pokud chcete mít komplexní prostředí, které by měl nastavte macOS přejděte **všechny ovládací prvky**:

![Předvolby systému klávesnice všechny ovládací prvky](media/accessibility-preferences-keyboard.png)

Nastavení **úplný přístup klávesnice** k **všechny ovládací prvky** můžete přejít přes všechny ovládací prvky v okně nebo dialogovém okně. Pak můžete vybrat pomocí ovládacích prvků:

- TAB přejděte vpřed přes ovládací prvky
- Stiskněte Shift + Tab zpětně projít ovládacích prvků
- Klávesy se šipkami pro přesun mezi ovládacími prvky směrem šipky
- Ovládací prvek karty z pole Textová oblast
- Stisknutím klávesy MEZERNÍK aktivuje ovládacího prvku na aktuálně fokus.

## <a name="how-to-enable-and-use-voiceover"></a>Postupy: Povolení a používání VoiceOver

Povolit nebo zakázat hlasového stiskněte  **&#8984; + F5**

VoiceOver příkazy se zobrazují v tomto průvodci jako **VO + * klíč*** kterým **VO** odkazuje na modifikátor nastavit **VoiceOver nástroj** aplikace. Výchozí modifikátor **Ctrl + Alt**. Například v závislosti na vaší modifikátor VoiceOver **VO + M** znamená **Ctrl + Alt + M**. Pro zkrácení, bude se kurzor klíče označovány jako **vlevo** a **vpravo**atd.

Přejít Visual Studio pro Mac uživatelské rozhraní, použijte následující kombinace kláves:

- **VO + šipka doprava nebo doleva**: Navigace mezi elementy uživatelského rozhraní
  - VoiceOver bude oznámit popisek a typ ovládacího prvku a popisují, jak pracovat s ním.
- **VO + Shift + dolů / nahoru**: Krok do / z elementu
  - Po uvnitř elementu lze použít **VO + vlevo / vpravo** k navigaci v prvky v ní.
- **VO + MEZERNÍK**: Vyberte / pracovat s ovládacím prvkem
- **VO + M**: Interakce s aplikací Visual Studio pro Mac nabídek

Další informace o použití VoiceOver a kompletní seznam příkazů najdete v následujících příručkách:

- [Apple VoiceOver – Příručka Začínáme](https://support.apple.com/en-us/guide/voiceover-guide/welcome/web)
- [Příkazy voiceOver v systému macOS](http://lab.dotjay.com/notes/voiceover-commands/)

## <a name="see-also"></a>Viz také:

- [Funkce usnadnění v sadě Visual Studio (ve Windows)](/visualstudio/ide/reference/accessibility-features-of-visual-studio)
