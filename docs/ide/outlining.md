---
title: Rozbalení a sbalení oblasti kódu v sadě Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- outlining
- Visual Studio, expand/collapse code
- Visual Studio, outlining
- expand/collapse code
- code [Visual Studio], outlining
- code [Visual Studio], hiding
- outlining code
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 62e6d5c7667bf697eeb190d69a996886fbee643f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="outlining"></a>Sbalování

Můžete skrýt nějaký kód ze zobrazení sbalením oblasti kód tak, aby se v části znaménko plus (**+**). Kliknutím na symbol plus rozbalíte sbalené oblast. Pokud jste uživatelem klávesnice, můžete vybrat **Ctrl**+**M**+**M** můžete rozbalit nebo sbalit. Můžete také sbalit oblast popisující poklepáním na kterýkoli řádek v oblasti na popisující okrajem, která se zobrazí vlevo kódu. Po přesunutí ukazatele myši sbalené oblast, můžete zobrazit obsah sbalené oblasti jako popisek.

Oblasti v popisující okraj jsou také vyznačené po přesunutí ukazatele myši okraj pomocí myši. Barva zvýraznění výchozí zdánlivě slabé místo v některých konfiguracích barev. Můžete změnit v **nástroje** > **možnosti** > **prostředí** > **písma a barev**  >  **Sbalitelné oblast**.

Pokud pracujete v popsané kódu, můžete rozbalit oddílů, které chcete pracovat, je sbalit, když jste hotovi a poté přesuňte do dalších částech. Pokud nechcete, aby tak, aby měl osnovy zobrazí, můžete použít **zastavit osnovy** příkaz k odebrání informace outline bez narušení vašeho kódu.

**Vrátit zpět** a **vrátit** příkazy **upravit** nabídky vliv tyto akce. **Kopie**, **Vyjmout**, **vložení**, a operací přetažení myší zachovat popisující informací, ale není stav sbalitelné oblasti. Například při kopírování oblasti, která sbalena, **vložit** operaci se vložit zkopírovaný text jako rozšířené oblast.

> [!CAUTION]
> Při změně oblast popsané osnovy mohou být ztraceny. Odstranění nebo najít a nahradit provozu může například vymazat konce oblasti.

Následující příkazy naleznete na **upravit** > **Osnova** podnabídky.

|||
|-|-|
|Skrýt výběr|(**Ctrl**+**M**, **Ctrl**+**H**)-sbalí vybraného bloku kódu, který obvykle nebude k dispozici pro osnovy, například `if` bloku. Chcete-li odebrat vlastní oblasti, použijte **zastavit skrytí aktuální** (nebo **Ctrl**+**M**, **Ctrl** + **U**). Není k dispozici v jazyce Visual Basic.|
|Přepnutí osnovy rozšíření|-Obrátí aktuální stav skrytý nebo rozbalených nejvnitřnější osnovy části, když ukazatel leží vnořené sbalenou část.|
|Přepněte všechny osnovy|(**Ctrl**+**M**, **Ctrl**+**L**)-nastaví všechny oblasti na stejnou sbalené nebo rozbalit stavu. Pokud jsou některé oblasti rozšířit a některé sbalené, pak sbalené rozbaleny regionů.|
|Zastavit osnovy|(**Ctrl**+**M**, **Ctrl**+**P**) – Odebere popisující informací pro celý dokument.|
|Zastavit skrytí aktuální|(**Ctrl**+**M**, **Ctrl**+**U**) – Odebere popisující informací pro aktuálně vybranou uživatelem definované oblast. Není k dispozici v jazyce Visual Basic.|
|Sbalit do definice|(**Ctrl**+**M**, **Ctrl**+**O**)-sbalí všechny typy členů.|
|Blokování Sbalit:\<logické hraniční >|(Visual C++) Sbalí oblast, ve kterém je umístěn kurzor funkci. Například pokud kurzor se nachází uvnitř smyčku, smyčky je skrytá.|
|Sbalit vše na: \<logické struktury >|(Visual C++) Sbalí všechny struktury uvnitř funkce.|

Visual Studio SDK můžete použít také k definování text oblastí, které chcete rozbalit nebo sbalit. V tématu [návod: vytvoření přehledu](../extensibility/walkthrough-outlining.md).

## <a name="see-also"></a>Viz také

- [Psaní kódu v editoru](../ide/writing-code-in-the-code-and-text-editor.md)
