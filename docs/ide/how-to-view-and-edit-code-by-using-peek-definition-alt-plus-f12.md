---
title: Použitím funkce Náhled definice
ms.date: 01/10/2018
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 79bebcdaaf2d970f019da12141275358120ac70e
ms.sourcegitcommit: 9753c7544cec852ca5efd0834e0956d9e53a5734
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/13/2019
ms.locfileid: "67043413"
---
# <a name="how-to-view-and-edit-code-by-using-peek-definition-altf12"></a>Postupy: Zobrazení a úpravy kódu s použitím funkce Náhled definice (Alt + F12)

Můžete použít **definice operace Peek** příkaz k zobrazení a úpravám kódu bez přepnutí mimo kód, který píšete. **Náhled definice** a **přejít k definici** obsahují stejné informace, ale **definice operace Peek** zobrazí v místním okně a **přejít k definici** ukazuje kód v samostatném okně s kódem. **Přejít k definici** způsobí, že váš kontext (tedy okno s aktivním kódem, aktuální řádek a pozice kurzoru) přejděte do okna Definice kódu. S použitím **definice operace Peek**, můžete zobrazit a upravit definici a pohyb uvnitř souboru definice při zachování svého místa v původním souboru kódu.

Můžete použít **definice operace Peek** s kódem jazyka C#, Visual Basic a C++. V jazyce Visual Basic **definice operace Peek** zobrazuje odkaz **prohlížeče objektů** pro symboly, které neobsahují metadata definice (například typy .NET, které jsou integrované v).

## <a name="use-peek-definition"></a>Použití náhledu definice

### <a name="open-a-peek-definition-window"></a>Otevření okna Náhled definice

1. Výběrem můžete prohlížet definici **funkce Náhled definice** v místní nabídce pro typ nebo člen, který chcete prozkoumat. Pokud je povolena možnost, můžete také prohlížet definice pomocí myši, stisknutím klávesy **Ctrl** (nebo jiného modifikátoru) a kliknutím na název členu. Nebo z klávesnice, stiskněte klávesu **Alt**+**F12**.

     Tento obrázek ukazuje **definice operace Peek** okna pro metodu s názvem `Print()`:

     ![Okno náhledu](../ide/media/peekwindow.png)

     Zobrazí se okno Definice pod `printer.Print("Hello World!")` řádku v původním souboru. Okno neskryje žádný kód v původním souboru. Řádky, které následují `printer.Print("Hello World!")` se zobrazí pod oknem definice.

1. Kurzor můžete přesunout na jiné místo v okně Náhled definice. Můžete i nadále pohybovat v původním okně kódu.

1. Můžete zkopírovat řetězec v okně definice a vložit ho do původního kódu. Můžete také přetáhnout řetězec z okna definice do původního kódu, aniž by byl v okně definice odstraněn.

1. Můžete zavřít okno Definice výběrem **Esc** klíč nebo **zavřete** tlačítko na kartě okna definice.

### <a name="open-a-peek-definition-window-from-within-a-peek-definition-window"></a>Otevření okna Náhled definice z okna Náhled definice

Pokud už máte **definice operace Peek** otevřené okno, můžete volat **definice operace Peek** znovu na kód v tomto okně. Otevře se jiné okno definice. Vedle karty okna definice se zobrazí sada teček s popisem cesty, která slouží k navigaci mezi okny definice. Popisek tlačítka na každé tečce zobrazuje název souboru a cestu k souboru definice, který tečka přestavuje.

   ![Operace Peek okna nejvyšší úrovně v okně Náhled](../ide/media/peekwithinpeek.png)

### <a name="peek-definition-with-multiple-results"></a>Náhled definice s více výsledky

Pokud používáte **definice operace Peek** na kód, který obsahuje více než jednu definici (například částečné třídy), seznam výsledků se zobrazí napravo od zobrazení definice kódu. Můžete zvolit některý z výsledků v seznamu k zobrazení jeho definice.

   ![Operace Peek okna z více výsledků](../ide/media/peekmultiple.png)

### <a name="edit-inside-the-peek-definition-window"></a>Upravit v okně Náhled definice

Při zahájení úprav v **definice operace Peek** okna, soubor, který modifikujte, automaticky se otevře jako samostatná karta v editoru kódu a odráží změny, které jste udělali. Ujistěte se, rušit a ukládat změny v můžete pokračovat **definice operace Peek** okně a na kartě budou odrážet provedené změny. I když zavřete **definice operace Peek** okno bez uložení změn, můžete provést, vrátit zpět a ukládat změny na kartě Výběr přesně tam, kde jste přestali v **definice operace Peek** okno.

   ![Úpravy v rámci okna Náhled](../ide/media/peekedit.png)

### <a name="to-change-options-for-peek-definition"></a>Chcete-li změnit možnosti pro náhled definice

1. Přejděte na **nástroje** > **možnosti** > **textový Editor** > **Obecné**.

1. Vyberte možnost **Otevřít definici v zobrazení náhledu**.

1. Klikněte na tlačítko **OK** zavřete **možnosti** dialogové okno.

   ![Nastavení možnosti kliknutí myší funkce Náhled definice](../ide/media/editor_options_peek_view.png)

### <a name="keyboard-shortcuts-for-peek-definition"></a>Klávesové zkratky pro náhled definice

Můžete použít tyto klávesové zkratky v **definice operace Peek** okno:

|Funkce|Klávesová zkratka|
|-------------------|:-----------------------:|
|Otevřít okno definice|**Alt**+**F12**|
|Zavřít okno definice|**ESC**|
|Povýšit okno definice na běžnou kartu dokumentu|**SHIFT**+**Alt**+**Domů**|
|Navigace mezi okny definice|**CTRL**+**Alt** + **-** a **Ctrl**+**Alt**+ **=**|
|Navigace mezi několika výsledky|**F8** a **Shift**+**F8**|
|Přepnout mezi oknem editoru kódu a oknem definice|**SHIFT**+**Esc**|

> [!NOTE]
> Můžete také použít stejné klávesové zkratky pro úpravu kódu v **definice operace Peek** okno jako můžete použít na jiném místě v sadě Visual Studio.

## <a name="see-also"></a>Viz také:

- [Vyhledání kódu](../ide/navigating-code.md)
- [Přejít k definici a Náhled definice](../ide/go-to-and-peek-definition.md)
- [Pro zvýšení produktivity v sadě Visual Studio](../ide/productivity-features.md)