---
title: Usnadnění tipy a triky pro Visual Studio
description: Další informace o tipy a triky, díky kterým integrovaného vývojového prostředí (IDE) sady Visual Studio pro každodenní použití, včetně osobám s postižením.
ms.date: 02/21/2019
ms.topic: conceptual
helpviewer_keywords:
- accessibility [Visual Studio]
ms.assetid: 6b491d88-f79e-4686-8841-857624bdcfda
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e86791e77d5c8f6eb1e6b88ac663e1f11cc53e1e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62793311"
---
# <a name="accessibility-tips-and-tricks-for-visual-studio"></a>Usnadnění tipy a triky pro Visual Studio

> [!TIP]
> Další informace o aktualizacích pro usnadnění přístupu, najdete v článku [vylepšení přístupnosti v sadě Visual Studio 2017 verze 15.3](https://devblogs.microsoft.com/visualstudio/accessibility-improvements-in-visual-studio-2017-version-15-3/) blogový příspěvek.

Visual Studio obsahuje vestavěných funkcí usnadnění, které jsou kompatibilní se čtečkami obrazovky a dalšími technologiemi přístupnosti. Toto téma obsahuje seznam běžných klávesových zkratek můžete použít k provádění úloh jen pomocí klávesnice a obsahuje informace o používání motivů vysoký kontrast – kvůli zlepšení viditelnosti. Také ukazuje způsob použití poznámek k odhalit užitečné informace o svém kódu a nastavení zvukové vodítek pro sestavení a zarážky události.

> [!NOTE]
> Toto téma se vztahuje k sadě Visual Studio ve Windows. Visual Studio pro Mac, najdete v části [usnadnění pro Visual Studio for Mac](/visualstudio/mac/accessibility).

## <a name="save-your-ide-settings"></a>Uložit nastavení IDE

 Ukládá se rozložení okna, schéma mapování klávesnice a další předvolby, můžete přizpůsobit vaše prostředí IDE. Další informace najdete v tématu [přizpůsobení integrovaného vývojového prostředí sady Visual Studio](../../ide/personalizing-the-visual-studio-ide.md).

## <a name="modify-your-ide-for-high-contrast-viewing"></a>Upravit vaše integrované vývojové prostředí pro zobrazení s vysokým kontrastem

Pro některé ty jsou obtížnější zobrazíte některé barvy. Pokud má vyšší kontrast psaní kódu, ale nechcete použít typické "Vysoký kontrast –" motivy, nabízíme teď motiv "Modrý (zvláště kontrastní)".

  ![Porovnání modrý motiv a zvláště kontrastní modrý motiv](media/blue-extra-contrast-theme.png)

## <a name="use-annotations-to-reveal-useful-information-about-your-code"></a>Použití anotací zobrazíte užitečné informace o kódu

Editor sady Visual Studio obsahuje mnoho text "vylepšení", které umožňují vědět záložky, vlastnosti a funkce na konkrétní body na řádek kódu, jako je například šroubovák a ikony žárovky, chyby a upozornění "podtržení vlnovkou" a tak dále. Můžete použít příkaz "Zobrazení poznámek k řádkům" nastavena na vám pomohou zjistit a poté přejděte mezi tato vylepšení.

  ![Použití sady příkazů zobrazit poznámek k řádkům](media/show-line-annotations-command-set.png)

## <a name="access-toolbars-by-using-shortcut-key-combinations"></a>Panely nástrojů přístup s použitím kombinace klávesových zkratek

Integrované vývojové prostředí sady Visual Studio má panely nástrojů, stejně jako mnoha nástrojových oken. Následující kombinace klávesových zkratek můžete přistupovat k nim.

|Funkce|Popis|Kombinace kláves|
|-------------|-----------------| - |
|Panely nástrojů rozhraní IDE|Vyberte první tlačítko na panelu nástrojů Standardní.|**ALT**, **Ctrl** + **kartu**|
|Panelech nástrojů|Přesune fokus na panely nástrojů v panelu nástrojů. <br> <br> **POZNÁMKA:** Tento postup funguje pro většinu okna nástrojů, ale pouze v případě, že je aktivní v panelu nástrojů. Kromě toho musíte zvolit klávesu SHIFT před klávesu ALT. V některých oknech nástrojů, jako je například Průzkumník týmových projektů musí podržte stisknutou klávesu SHIFT na chvíli předtím, než zvolí klávesu ALT.|**SHIFT** + **Alt**|
|Panely nástrojů|Přejdete na první položku v dalším panelu nástrojů (když je fokus panelu nástrojů).|**Ctrl** + **Tab**|

### <a name="other-useful-shortcut-key-combinations"></a>Další užitečné kombinace klávesových zkratek

Některé další užitečné kombinace klávesových zkratek, patří.

|Funkce|Popis|Kombinace kláves|
|-------------|-----------------| - |
|IDE – integrované vývojové prostředí|Vysoký kontrast – zapnutí a vypnutí. <br> <br> **POZNÁMKA:** Standardní místní Windows|**Levý Alt + Levý Shift + PrtScn**|
|Dialogové okno|Zaškrtněte nebo zrušte zaškrtnutí políčka zaškrtávací políčko v dialogovém okně. <br> <br> **POZNÁMKA:** Standardní místní Windows|**MEZERNÍK**|
|Místní nabídky|Otevřete nabídku kontextu (klikněte pravým tlačítkem). <br> <br> **POZNÁMKA:** Standardní místní Windows|**Shift** + **F10**|
|Nabídky|Rychlý přístup k položce nabídky pomocí jeho klíče akcelerátoru. Zvolte **Alt** klíč následovaný podtržené písmena v nabídce k aktivaci příkazu. Chcete-li zobrazit dialogové okno Otevřít projekt v sadě Visual Studio, například byste zvolili **Alt** + **F** + **O**  +  **P**.  <br><br> **POZNÁMKA:** Standardní místní Windows|**ALT** + **[písmeno]**|
|Vyhledávací pole|Použijte funkci hledání v sadě Visual Studio.|**Ctrl** + **Q**|
|Okno nástrojů|Přecházení mezi kartami sady nástrojů.|**Ctrl** + **UPARROW**<br /><br /> and<br /><br /> **CTRL** + **šipka dolů**|
|Okno nástrojů|Přidání ovládacího prvku z panelu nástrojů do formuláře nebo návrháře.|**Zadejte**|
|Dialogové okno Možnosti: Prostředí > klávesnice|Odstranit kombinace klíče zadané v **stiskněte klávesovou zkratku** možnost.|**BACKSPACE**|

> [!NOTE]
> Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici.

## <a name="use-the-sound-applet-to-set-build-and-breakpoint-cues"></a>Nastavení sestavení a zarážky pomůcky pomocí apletu zvuku

Zvukové aplet ve Windows můžete přiřadit zvuk na události programu sady Visual Studio. Konkrétně můžete přiřadit zvuky k následujícím událostem program:

* Dosažení zarážky
* Sestavení bylo zrušeno.
* Sestavení selhalo
* Sestavení proběhlo úspěšně.

Tady je způsob:

1. V **hledání** pole na počítači se systémem Windows 10, typ **změnit systémové zvuky**.

   ![Vyhledávací pole ve Windows 10](media/type-here-to-search.png)

   (Případně pokud máte Cortana povolená, Řekněme, že "Hey Cortana" a potom vyslovením "Změnit systémové zvuky".)

2. Dvakrát klikněte na panel **změnit systémové zvuky**.

   ![Výsledky hledání ve Windows 10](media/change-system-sounds.png)

3. V **zvuk** dialogové okno, klikněte na tlačítko **zvuky** kartu. <br><br>
   Potom v **Program události**, přejděte k položce **sady Microsoft Visual Studio**a vyberte zvuky, které má být použita k událostem, které zvolíte.

   ![Na kartě zvuky zvukové apletu ve Windows 10](media/sound-applet.png)

4. Klikněte na **OK**.

## <a name="see-also"></a>Viz také:

* [Funkce pro usnadnění přístupu sady Visual Studio](../../ide/reference/accessibility-features-of-visual-studio.md)
* [Postupy: Přizpůsobení nabídek a panelů nástrojů v sadě Visual Studio](../../ide/how-to-customize-menus-and-toolbars-in-visual-studio.md)
* [Přizpůsobení prostředí IDE sady Visual Studio](../../ide/personalizing-the-visual-studio-ide.md)
* [Microsoft Accessibility](https://www.microsoft.com/Accessibility)
* [Usnadnění přístupu (Visual Studio for Mac)](/visualstudio/mac/accessibility)