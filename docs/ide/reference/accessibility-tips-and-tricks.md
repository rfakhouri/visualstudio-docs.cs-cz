---
title: Tipy a triky pro usnadnění pro Visual Studio
description: Přečtěte si další informace o tipech a štychech, které vám pomůžou usnadnit přístup k integrovanému vývojovému prostředí (IDE) sady Visual Studio pro všechny uživatele, včetně postižených uživatelů.
ms.date: 08/02/2019
ms.topic: conceptual
helpviewer_keywords:
- accessibility [Visual Studio]
ms.assetid: 6b491d88-f79e-4686-8841-857624bdcfda
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5a3a70f061ea4fd6dd51a3badbed922675b99fba
ms.sourcegitcommit: b56dc6fadc6c924beed36bb4c2ccc16cf6bcfa1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/02/2019
ms.locfileid: "68740250"
---
# <a name="accessibility-tips-and-tricks-for-visual-studio"></a>Tipy a triky pro usnadnění pro Visual Studio

> [!TIP]
> Další informace o aktualizacích usnadnění najdete v blogovém příspěvku o [vylepšeních dostupnosti v aplikaci Visual Studio 2017 verze 15,3](https://devblogs.microsoft.com/visualstudio/accessibility-improvements-in-visual-studio-2017-version-15-3/) .

Visual Studio obsahuje integrované funkce pro usnadnění přístupu, které jsou kompatibilní s čtečkami obrazovky a dalšími technologiemi usnadnění. Toto téma obsahuje seznam běžných kombinací klávesových zkratek, které lze použít k provádění úloh pouze pomocí klávesnice, a obsahuje informace o použití vysoce kontrastní motivů ke zlepšení viditelnosti. Také se dozvíte, jak používat poznámky k odhalení užitečných informací o vašem kódu a jak nastavit zvukové pomůcky pro události sestavení a zarážky.

> [!NOTE]
> Toto téma se vztahuje k sadě Visual Studio ve Windows. Visual Studio pro Mac najdete v tématu [přístupnost pro Visual Studio pro Mac](/visualstudio/mac/accessibility).

## <a name="save-your-ide-settings"></a>Uložení nastavení IDE

 Prostředí IDE můžete přizpůsobit uložením rozložení okna, schématu mapování klávesnice a dalších předvoleb. Další informace najdete v tématu [Přizpůsobení integrovaného vývojového prostředí (IDE) sady Visual Studio](../../ide/personalizing-the-visual-studio-ide.md).

## <a name="modify-your-ide-for-high-contrast-viewing"></a>Úprava prostředí IDE pro zobrazení s vysokým kontrastem

U některých lidé se některé barvy obtížně zobrazují. Pokud chcete mít větší kontrast jako při psaní kódu, ale nechcete používat typické motivy "Vysoký kontrast", teď nabízíme motiv "modrý (extra Contrast)".

  ![Porovnat modrý motiv a modrý motiv extra Contrast](media/blue-extra-contrast-theme.png)

## <a name="use-annotations-to-reveal-useful-information-about-your-code"></a>Použití poznámek k odhalení užitečných informací o kódu

Editor sady Visual Studio obsahuje mnoho textových "vylepšení", která vám pomůžou zjistit charakteristiky a funkce na určitých místech na řádku kódu, jako jsou ikony Screwdriver a žárovky, chyby a varování "vlnovky", záložky atd. Můžete použít sadu příkazů zobrazit poznámky k řádkům, které vám pomohou zjistit a procházet mezi těmito doplňky.

  ![Použití sady příkazů zobrazit poznámky k řádkům](media/show-line-annotations-command-set.png)

## <a name="access-toolbars-by-using-shortcut-key-combinations"></a>Přístup k panelům nástrojů pomocí kombinací klávesových zkratek

Integrované vývojové prostředí sady Visual Studio má panely nástrojů jako mnoho oken nástrojů. Následující kombinace klávesových zkratek vám pomůžou získat přístup k nim.

|Funkce|Popis|Kombinace kláves|
|-------------|-----------------| - |
|Panely nástrojů IDE|Vyberte první tlačítko na standardním panelu nástrojů.|**ALT**,**TAB** **CTRL** + |
|Panely nástrojů okna nástrojů|Přesuňte fokus na panely nástrojů v okně nástroje. <br> <br> **POZNÁMKA:** Tato funkce funguje pro většinu oken nástrojů, ale pouze v případě, že je fokus v okně nástroje. Také je nutné před klávesou ALT zvolit klávesu SHIFT. V některých oknech nástrojů, jako je například Team Explorer, je nutné před volbou klávesy ALT držet chvilku klávesu SHIFT.|**Shift**ALT + |
|Panely nástrojů|Přejít na první položku na následujícím panelu nástrojů (Pokud má panel nástrojů fokus).|**Ctrl** + **Tab**|

### <a name="other-useful-shortcut-key-combinations"></a>Další užitečné kombinace klávesových zkratek

Mezi další užitečné kombinace klávesových zkratek patří následující.

|Funkce|Popis|Kombinace kláves|
|-------------|-----------------| - |
|IDE – integrované vývojové prostředí|Přepnutí Vysoký kontrast zapnuto nebo vypnuto. <br> <br> **POZNÁMKA:** Standardní zástupce Windows|**Levý ALT + levý SHIFT + PRINT SCREEN**|
|Dialogové okno|Zaškrtněte nebo zrušte zaškrtnutí možnosti zaškrtávací políčko v dialogovém okně. <br> <br> **POZNÁMKA:** Standardní zástupce Windows|**Spacebar**|
|Místní nabídky|Otevřete místní nabídku (kliknutím pravým tlačítkem myši). <br> <br> **POZNÁMKA:** Standardní zástupce Windows|**Shift** + **F10**|
|Nabídky|Rychlý přístup k položce nabídky pomocí jeho klávesových zkratek Příkaz aktivujete tak, že v nabídce vyberete klávesu **ALT** následovanou podtrženými písmeny. Například pro zobrazení dialogového okna otevřít projekt v aplikaci Visual Studio byste si zvolili **ALT** + **F** + **O** + **P**.  <br><br> **POZNÁMKA:** Standardní zástupce Windows|ALT +  **[písmeno]**|
|Vyhledávací pole|Použijte funkci hledání v aplikaci Visual Studio.|**Ctrl** + **Q**|
|Okno nástrojů|Přesun mezi kartami sady nástrojů|**CTRL +**  + **šipka nahoru**<br /><br /> and<br /><br /> **CTRL +**  + **šipka dolů**|
|Okno nástrojů|Přidejte ovládací prvek ze sady nástrojů do formuláře nebo návrháře.|**Zadejte**|
|Dialogové okno Možnosti: Prostředí > klávesnice|Odstraní kombinaci kláves zadaná v možnosti klávesových **zkratek** CTRL.|**BACKSPACE**|
|Okno nástroje oznámení|Otevřete okno nástroje oznámení pomocí dvou kombinací kláves klávesových zkratek, jednu následovaný druhým. Potom zobrazte oznámení pomocí kláves se šipkami a vyberte je.| **Podržte** +  **&#92;** <br>**Ctrl** + **N**|

> [!NOTE]
> Dialogová okna a příkazy nabídek, které se zobrazí mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici.

## <a name="use-the-sound-applet-to-set-build-and-breakpoint-cues"></a>Použití apletu zvuk k nastavení hromádek sestavení a zarážky

Pomocí apletu zvuk v systému Windows můžete přiřadit zvuk k událostem programu Visual Studio. Konkrétně můžete přiřadit zvuky k následujícím událostem programu:

* Pozice zarážky
* Sestavení bylo zrušeno
* Sestavení selhalo
* Sestavení bylo úspěšné.

Tady je postup:

1. Do **vyhledávacího** pole na počítači s Windows 10 zadejte **změnit systémové zvuky**.

   ![Vyhledávací pole ve Windows 10](media/type-here-to-search.png)

   (Případně, pokud máte Cortana povoleno, řekněme "Hey Cortana" a pak vyslovte "změnit systémové zvuky".)

2. Dvakrát klikněte na možnost **změnit systémové zvuky**.

   ![Výsledky hledání ve Windows 10](media/change-system-sounds.png)

3. V dialogovém okně **zvuk** klikněte na kartu **zvuky** . <br><br>
   Potom v okně **události programu**přejděte na **Microsoft Visual Studio**a vyberte zvuky, které chcete použít pro události, které zvolíte.

   ![Karta zvuky v apletu zvuk v systému Windows 10](media/sound-applet.png)

4. Klikněte na **OK**.

## <a name="see-also"></a>Viz také:

* [Funkce pro usnadnění přístupu sady Visual Studio](../../ide/reference/accessibility-features-of-visual-studio.md)
* [Postupy: Přizpůsobení nabídek a panelů nástrojů v aplikaci Visual Studio](../../ide/how-to-customize-menus-and-toolbars-in-visual-studio.md)
* [Přizpůsobení prostředí IDE sady Visual Studio](../../ide/personalizing-the-visual-studio-ide.md)
* [Usnadnění Microsoftu](https://www.microsoft.com/Accessibility)
* [Usnadnění (Visual Studio pro Mac)](/visualstudio/mac/accessibility)