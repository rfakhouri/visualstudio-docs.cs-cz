---
title: "Usnadnění tipy a triky pro Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 09/15/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: accessibility [Visual Studio]
ms.assetid: 6b491d88-f79e-4686-8841-857624bdcfda
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: a4ac0c709f2b7f9dfded7c6781dda9831e457fa5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="accessibility-tips-and-tricks-for-visual-studio"></a>Usnadnění tipy a triky pro Visual Studio
> [!TIP]
> Další informace o nejnovějších aktualizacích usnadnění přístupu najdete v tématu [vylepšení přístupnosti v Visual Studio 2017 verze 15.3](https://blogs.msdn.microsoft.com/visualstudio/2017/08/14/accessibility-improvements-in-visual-studio-2017-version-15-3/) příspěvku na blogu.

Visual Studio obsahuje vestavěných funkcí usnadnění, které jsou kompatibilní s čtečky obrazovky a další technologie usnadnění. Toto téma obsahuje seznam běžných kombinace klávesových zkratek, můžete použít k provádění úloh s pouze klávesnice a obsahuje informace o použití motivů vysokého kontrastu ke zlepšení viditelnosti. Také ukazuje, jak používat poznámky na nich užitečné informace o kódu a jak nastavit zvukové hromádky pro sestavení a zarážek události.

## <a name="save-your-ide-settings"></a>Uložit nastavení IDE  
 Uložením rozložení okna, schéma mapování klávesnice a další předvolby můžete přizpůsobit prostředí IDE. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md).  

## <a name="modify-your-ide-for-high-contrast-viewing"></a>Upravit vaše IDE pro zobrazení vysoký kontrast
Pro některé zaměstnance je složité najdete některé barvy. Pokud chcete další kontrast, jako je kód, ale nechcete použít typické "Vysoký kontrast" motivy, nabízíme nyní motiv "Blue (navíc kontrast)".

  ![Porovnat motiv modrý a motiv modrý navíc kontrastem](media/blue-extra-contrast-theme.png "vidět rozdíl mezi motiv modrý a motiv modrý navíc kontrast")

## <a name="use-annotations-to-reveal-useful-information-about-your-code"></a>Použití poznámek na nich užitečné informace o kódu

Editoru Visual Studio obsahuje mnoho text "vylepšení" které umožňují vědět o vlastnosti a funkce na konkrétní body na řádek kódu, například lightbulbs, chyby a upozornění "podtržení vlnovkou", záložky a tak dále. Můžete nastavit vám pomohou zjistit a potom přejděte mezi těchto vylepšení příkaz "Zobrazit čáry poznámky".

  ![Použít sadu příkazů nástroje zobrazit čáry poznámky](media/show-line-annotations-command-set.png "ukazuje, jak nastavit sadu příkazů nástroje zobrazit čáry poznámky")

## <a name="access-toolbars-by-using-shortcut-key-combinations"></a>Panely nástrojů přístup pomocí kombinace klávesových zkratek
Visual Studio IDE má panely nástrojů, stejně jako mnoho nástroje systému windows. Následující kombinace klávesových zkratek můžete přistupovat k nim.

|Funkce|Popis|Kombinace klíče|  
|-------------|-----------------|---------------------|  
|Panely nástrojů rozhraní IDE|Vyberte první tlačítko na standardním panelu nástrojů.|**ALT**, **CTRL** + **KARTA**|  
|Nástroj panely nástrojů|Přesunete fokus na panely nástrojů v okně nástroje. <br> <br> **Poznámka:** tento postup funguje pro většinu nástroje systému windows, ale jenom v případě, že je aktivní okno nástroje. Navíc, musíte zvolit klávesu SHIFT před klávesu ALT. V některých okna nástrojů, jako je například Průzkumník týmových projektů musí podržíte klávesu SHIFT na chvíli před volbou klávesu ALT.|**POSUNUTÍ** + **ALT**|
|Panely nástrojů|Přejdete na první položky v dalším panelu nástrojů (Pokud je fokus panelu nástrojů).|**CTRL** + **KARTA**|

### <a name="other-useful-shortcut-key-combinations"></a>Další užitečné kombinace klávesových zkratek  
Některé další užitečné kombinace klávesových zkratek patří.

|Funkce|Popis|Kombinace klíče|  
|-------------|-----------------|---------------------|  
|IDE – integrované vývojové prostředí|Vysoký kontrast zapnutí a vypnutí. <br> <br> **Poznámka:** zástupce standardní Windows|**LEVÝ ALT + levé SHIFT + TISKOVÉ obrazovky**|  
|Dialogové okno|Vyberte nebo zrušte zaškrtnutí políčka možnost v dialogovém okně. <br> <br> **Poznámka:** zástupce standardní Windows|**MEZERNÍK**|  
|Kontextové nabídky|Otevřete nabídku kontextu (klikněte pravým tlačítkem). <br> <br> **Poznámka:** zástupce standardní Windows|**POSUNUTÍ** + **F10**|
|Nabídky|Rychlý přístup k položce nabídky pomocí jeho klávesy akcelerátoru. Vyberte **ALT** klíč následuje podtržené znaky v nabídce jej aktivovat. Například pokud chcete zobrazit dialogové okno otevřete projekt v sadě Visual Studio, by zvolit **ALT** + **F** + **O**  +  **P**.  <br><br> **Poznámka:** zástupce standardní Windows|**ALT** + **[písmeno]**|
|Okna nástrojů|Přecházení mezi kartami sady nástrojů.|**CTRL** + **UPARROW**<br /><br /> and<br /><br /> **CTRL** + **DOWNARROW**|  
|Okna nástrojů|Přidání ovládacího prvku formuláře nebo návrháře z panelu nástrojů.|**ZADEJTE**|  
|Klávesnice, prostředí, dialogové okno Možnosti|Odstranit kombinace kláves zadané v **klávesovou zkratku** možnost.|**BACKSPACE**|  

> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici.  


## <a name="use-the-sound-applet-to-set-build-and-breakpoint-cues"></a>Můžete nastavit upozornění sestavení a zarážek pomocí apletu zvuku
Můžete apletu zvukové přiřadit zvuk události programu sady Visual Studio v systému Windows. Konkrétně je možné přiřadit zvuky k následujícím událostem program:

 * Stiskněte klávesu zarážek
 * Sestavení bylo zrušené
 * Sestavení se nezdařilo
 * Sestavení bylo úspěšně dokončeno

Tady je způsob.

1. V **vyhledávání** pole v počítači se systémem Windows 10, typ **změnit systémové zvuky**.

  ![Vyhledávací pole ve Windows 10](media/type-here-to-search.png "pole typu zvuků do vyhledávání v počítači se systémem Windows 10")

  (Případně, pokud máte povolené Cortana, vyslovení "Blogu Hey Cortana" a poté vyslovte "Změnit systémové zvuky".)

2. Klikněte dvakrát na **změnit systémové zvuky**.

  ![Výsledky hledání ve Windows 10](media/change-system-sounds.png "dvojitým kliknutím změnit systémové zvuky ve výsledcích hledání")

3. V **zvuk** dialogové okno, klikněte **zvuků** kartě. <br><br>
 Potom v **programu události**, přejděte k položce **Microsoft Visual Studio**a vyberte zvuků, které chcete použít k událostem, které zvolíte.

  ![Na kartě zvuky zvukové apletu ve Windows 10](media/sound-applet.png "dvojitým kliknutím změnit systémové zvuky ve výsledcích hledání")

4. Click **OK**.



## <a name="see-also"></a>Viz také  
* [Funkce pro usnadnění přístupu sady Visual Studio](../../ide/reference/accessibility-features-of-visual-studio.md)
  * [Postupy: přizpůsobení nabídek a panelů nástrojů v sadě Visual Studio](../../ide/how-to-customize-menus-and-toolbars-in-visual-studio.md)
* [Přizpůsobení sady Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md)
* [Společnosti Microsoft věnovaném usnadnění](https://www.microsoft.com/Accessibility)
