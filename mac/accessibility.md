---
title: Usnadnění
description: Tento článek představuje funkce pro usnadnění přístupu v sadě Visual Studio pro Mac a jak může být povoleno.
author: asb3993
ms.author: amburns
ms.date: 08/15/2017
ms.assetid: 2C4AAC2E-3B4A-4496-8BE0-1F5A7F81D1CA
ms.openlocfilehash: b1b2cb26f6e42486e8740bf9610baeeb308a9b66
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
ms.locfileid: "33870535"
---
# <a name="accessibility"></a>Usnadnění

Kromě funkcí a nástrojů v systému macOS Visual Studio pro Mac má následující funkce, což přístupnější pro osoby s postižením:

- Text zvětšení v řešení a Editor dotyková zařízení
- Možnosti velikosti textu v editorech
- Přizpůsobení barev v editorech
- Úprava klávesových zkratek
- Doplňování kódu pro metody a parametry 

Další informace o funkce pro usnadnění přístupu v systému macOS najdete v tématu [webu společnosti Apple](https://www.apple.com/accessibility/mac/).

## <a name="using-accessibility-features-in-visual-studio-for-mac"></a>Pomocí funkce usnadnění v sadě Visual Studio pro Mac

Funkce usnadnění v sadě Visual Studio pro Mac jsou ve výchozím nastavení vypnuté. Aby se mohly, proveďte následující kroky:

1. Přejděte na **sady Visual Studio > Předvolby > jiné > usnadnění**.

2. Vyberte **povolit usnadnění přístupu** zaškrtávací políčko, jak je znázorněno v následujícím diagramu:

    ![Povolit usnadnění přístupu zaškrtávací políčko](media/accessibility-image1.png)

3. Stiskněte **, restartujte Visual Studio** tlačítko Povolit funkce pro usnadnění přístupu vstoupily v platnost.


Alternativně můžete příkazového řádku k povolení funkce usnadnění přístupu. K tomu, zadejte následující příkaz v terminálu: 

```bash
defaults write com.microsoft.visual-studio com.monodevelop.AccessibilityEnabled 1 
```

Po zapnutí usnadnění, musíte restartovat Visual Studio.

## <a name="how-to-use-keyboard-navigation"></a>Postupy: použití klávesnice navigační

Navigační klávesnice se dá nastavit pomocí nastavení možnost úplný přístup klávesnice v **předvolbách systému > klávesnice > zkratky** k **všechny ovládací prvky**:

  ![Systémy předvolby panelu v systému macos](media/accessibility-image2.png)

Nastavení úplné klávesnice přístupu zapnete rámečku fokusu. Pak můžete vybrat ovládacích prvků pomocí:
- Karta dál projít ovládací prvky
- SHIFT – karta zpětné projít ovládací prvky
- Klávesy se šipkami pro přesun mezi ovládacími prvky ve směru šipky. 

Stisknutím panelu místa aktivuje cílených ovládacího prvku.

## <a name="how-to-enable-and-use-voice-over"></a>Postupy: povolení a používání hlasového přes

Zapnout VoiceOver nebo vypnout stisknutím **Cmd + F5**

Procházet příkazy VoiceOver uživatelského rozhraní, použijte následující příkazy:

- Přesunutí kurzoru VoiceOver mezi ovládacími prvky: **Ctrl + Alt + vlevo klávesa se šipkou klávesa se šipkou vpravo a**

VoiceOver přečte název ovládacích prvků, některé podrobnosti o něm a co můžete dělat s ním. 

- Zadejte skupiny a ovládací prvky (například panelu pro řešení, nástrojů a dalších dotyková zařízení): **Ctrl + Alt + Shift + šipka dolů**

Jakmile se v ovládacím prvku, můžete použít **Ctrl + Alt + šipky** pohyb uvnitř ho. 
 
Obecné informace o použití VoiceOver v systému macOS najdete v následujících příručkách:

- [Začínáme s VoiceOver](https://help.apple.com/voiceover/info/guide/10.12/)
- [Příkazy voiceOver v systému macOS](http://lab.dotjay.com/notes/voiceover-commands/)
