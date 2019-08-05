---
title: Usnadnění
description: V tomto článku se seznámíte s funkcemi pro usnadnění přístupu v Visual Studio pro Mac a o tom, jak je možné je povolit.
author: conceptdev
ms.author: crdun
ms.date: 04/17/2019
ms.assetid: 2C4AAC2E-3B4A-4496-8BE0-1F5A7F81D1CA
ms.openlocfilehash: 13b8d40a6ab31d7178e95a3896afa1c85c804f6c
ms.sourcegitcommit: a124076dfd6b4e5aecda4d01984fee7b0c034745
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2019
ms.locfileid: "68787642"
---
# <a name="accessibility"></a>Usnadnění

Visual Studio pro Mac má následující funkce usnadnění přístupu, aby bylo lépe dostupné pro lidi s různými schopnostmi:

- Zvětšení textu v panelu řešení a editoru
- Možnosti změnit velikost textu v editorech
- Přizpůsobení barev v editorech
- Procházení pomocí klávesnice
- Přizpůsobení zástupce
- Dokončování kódu pro metody a parametry

Kromě těchto funkcí Apple poskytuje řadu nástrojů, které uživatelům pomůžou se speciálními potřebami, jako je VoiceOver a diktování.

Další informace o funkcích přístupnosti v macOS najdete na [webu společnosti Apple](https://www.apple.com/accessibility/mac/).

## <a name="enabling-macos-assistive-technologies-in-visual-studio-for-mac"></a>Povolení technologií macOS pro usnadnění v Visual Studio pro Mac

Ve výchozím nastavení je podpora pro technologie macOS pro usnadnění Standard vypnutá. Visual Studio pro Mac Pokud ho chcete povolit, postupujte podle těchto kroků:

1. Přejít do sady **Visual Studio (nabídka) > předvolby > jiné > přístupnost**

2. Zaškrtněte políčko **Povolit přístupnost** :

   ![Zaškrtávací políčko přístupnosti předvoleb](media/accessibility-preferences.png)

3. Vyberte tlačítko **restartovat Visual Studio** a restartujte Visual Studio a povolte podporu pro technologie pro usnadnění společnosti Apple.

## <a name="how-to-use-keyboard-navigation"></a>Postupy: Použití navigace pomocí klávesnice

Podpora navigace klávesnicí je integrovaná přímo do macOS, ale aby bylo možné mít nejkomplexnější prostředí, měli byste nastavit macOS na navigaci **všech ovládacích prvků**:

![Systémové předvolby klávesnice – všechny ovládací prvky](media/accessibility-preferences-keyboard.png)

Nastavení **úplného přístupu** k klávesnicím pro **všechny ovládací prvky** umožňuje procházet všemi ovládacími prvky v okně nebo dialogovém okně. Pak můžete vybrat ovládací prvky pomocí:

- Karta k přechodu mezi ovládacími prvky
- Klávesa SHIFT pro přechod zpět přes ovládací prvky
- Klávesy se šipkami pro pohyb mezi ovládacími prvky ve směru šipky
- Karta ovládacího prvku mimo oblast textu
- Stisknutí mezerníku aktivuje aktuálně fokus ovládacího prvku.

## <a name="how-to-enable-and-use-voiceover"></a>Postupy: Povolení a použití VoiceOver

Povolení nebo zakázání VoiceOver stisknutím klávesy  **&#8984; + F5**

Příkazy VoiceOver se zobrazí v této příručce jako **vo +_Key_**  , kde **vo** označuje modifikátor nastavený v aplikaci **VoiceOver Utility** . Výchozí modifikátor je **CTRL + ALT**. Například v závislosti na modifikátoru VoiceOver, **vo + m** bude znamenat **CTRL + ALT + m**. V případě zkrácení budou klávesy kurzorů označovány jako **levé** a **pravé**atd.

K procházení uživatelského rozhraní Visual Studio pro Mac použijte následující kombinace kláves:

- **Vo + vpravo/vlevo**: Navigace mezi prvky uživatelského rozhraní
  - VoiceOver oznámí popisek a typ ovládacího prvku a vysvětluje, jak s ním pracovat.
- **Vo + Shift + šipka dolů**: Krokovat dovnitř a ven z prvku
  - Jednou v prvku můžete použít **vo + Left/Right** k procházení prvků v ní.
- **Vo + mezera**: Výběr/interakce s ovládacím prvkem
- **VO + M**: Interakce s panelem nabídek Visual Studio pro Mac

Další informace o používání VoiceOver a vyčerpávajícího seznamu příkazů najdete v následujících příručkách:

- [Příručka pro Začínáme pro Apple VoiceOver](https://support.apple.com/en-us/guide/voiceover-guide/welcome/web)
- [Příkazy VoiceOver v macOS](http://lab.dotjay.com/notes/voiceover-commands/)

## <a name="see-also"></a>Viz také:

- [Funkce usnadnění v aplikaci Visual Studio (ve Windows)](/visualstudio/ide/reference/accessibility-features-of-visual-studio)
