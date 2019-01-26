---
title: Režim mapování posuvníku panelu a řádku režimu
ms.date: 09/25/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3189bf2c87b6996cfd11a42a05ee9612d79bee38
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54965767"
---
# <a name="how-to-customize-the-scroll-bar"></a>Postupy: Přizpůsobení posuvníku

Při práci se soubory kódu dlouho, může být obtížné sledovat kde všechno, co je v souboru. Můžete upravit posuvník Editor kódu, abyste získali celkový přehled o co se děje ve vašem kódu.

## <a name="annotations"></a>Poznámky

Můžete vybrat, zda posuvník zobrazuje poznámky, jako je například změny kódu, zarážky, záložek, chyby a pozici blikajícího kurzoru.

   1. Otevřít **posuvníky** stránka možností výběrem **nástroje** > **možnosti** > **textový Editor**  >  **Všechny jazyky** > **posuvníky**.

   2. Vyberte **zobrazit poznámky přes svislý posuvník**a pak vybrat poznámky, které chcete zobrazit. Jsou dostupné poznámky:

      - změny
      - značky
      - chyby
      - pozici blikajícího kurzoru

      > [!TIP]
      > **Zobrazit značky** možnost obsahuje zarážky a záložky.

Vyzkoušejte si, že otevřete soubor kódu a nahrazení nějaký text, který se nachází na několika místech v souboru. Posuvník demonstruje účinek nahrazení, tak si změny můžete zálohovat, pokud něco, co by nemělo být nahrazen.

Tady je vzhled posuvníku po hledání řetězce. Všimněte si, že všechny instance řetězce zobrazí posuvník.

![Visual Studio posuvník po hledání řetězce](../ide/media/enhancedscrollbarsearch.png)

Tady je posuvník po nahrazení všechny instance řetězce. Červené značky v pořadu posuvníku panelu, kde nahrazování textu zavedeny chyby.

![Visual Studio posuvník po nahrazení řetězce s chybami](../ide/media/enhancedscrollbarreplace.png)

## <a name="display-modes"></a>Režimy zobrazení

Posuvník má dva režimy: panelu režim a režim mapování.

### <a name="bar-mode"></a>Panel režimu

*Panel režimu* zobrazí poznámka ukazatelů posuvníku. Kliknutím na posuvník posune stránku nahoru nebo dolů, ale nepřejde do tohoto umístění v souboru.

### <a name="map-mode"></a>Režim mapování

V *režim mapování*po kliknutí na umístění na posuvník, kurzor přejde do tohoto umístění v souboru namísto pouze posouvání navýšení nebo snížení kapacity na stránce. Řádky kódu jsou uvedeny v miniaturní posuvníku. Můžete zvolit, jak široké sloupce mapy je tak, že vyberete hodnotu v **hled zdrojů**. Pokud chcete povolit větší náhled kódu při přesunutí ukazatele myši na mapě, vyberte **zobrazení popisu tlačítka ve verzi Preview** možnost. Sbalených oblasti jinak jsou zobrazena šedě a rozbalte při dvojitém kliknutí na ně.

> [!TIP]
> Můžete vypnout zobrazení miniaturní kódu v režimu mapování tak, že nastavíte **hled zdrojů** k **vypnout**. Pokud **zobrazení popisu tlačítka ve verzi Preview** je vybrané, se stále zobrazuje náhled kódu na tomto místě při najetí na ukazatel na posuvníku a kurzor stále přejde do tohoto umístění v souboru po kliknutí na.

Následující obrázek ukazuje příklad prohledávání, když je zapnut režim mapování a je nastavena šířku na **střední**:

![Visual Studio posuvník v režimu mapy](../ide/media/enhancedscrollbar.png)

Na následujícím obrázku **zobrazení popisu tlačítka ve verzi Preview** možnost:

![Visual Studio posuvník s popisem](../ide/media/enhancedscrollbarsearchtooltip.png)

## <a name="see-also"></a>Viz také:

- [Funkce editoru kódu](../ide/writing-code-in-the-code-and-text-editor.md)