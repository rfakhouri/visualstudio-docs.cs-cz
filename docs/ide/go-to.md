---
title: Vyhledání kódu pomocí přejít na příkazy
ms.date: 09/26/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 509b2107-23d1-4fb3-987f-ab99ef45b72e
helpviewer_keywords:
- code editor, go to
- code editor, go to line
- go to line
- go to
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9aca1106bb6dfa3838890e4ae5c1886875e3e357
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/22/2018
---
# <a name="find-code-using-go-to-commands"></a>Vyhledání kódu pomocí přejít na příkazy

Visual Studio **přejít na** příkazy zaměřují se hledání kódu můžete rychle najít zadané položky. Můžete přejít na konkrétní řádku, typ, symbol, souboru a člena z jednoduchého jednotné rozhraní. Tato funkce existuje v Visual Studio 2017 nebo novější.

## <a name="how-to-use-it"></a>Způsobu jeho použití

Vstup        | Funkce
------------ | ---
**Klávesnice** | Stiskněte klávesu **Ctrl**+**T** nebo **Ctrl**+**,**
**Myš**    | Vyberte **upravit** > **přejít na** > **přejděte na všechny**

Malé okno se zobrazí v horní části napravo od vaší editor kódu.

![Přejděte do všech oken](media/go-to-all.png)

Při psaní do textového pole, výsledky se zobrazí v rozevíracím seznamu pod textové pole. Přejít na element, vyberte ho v seznamu.

![Přejděte do okna](../ide/media/vside_navigatetowindow.png)

Můžete také zadat otazník (**?**) zobrazíte další nápovědu.

![Přejděte na všechny nápovědy](media/go-to-all-help.png)

## <a name="filtered-searches"></a>Filtrované hledání

Ve výchozím nastavení je zadaná položka hledán v všechny položky řešení. Hledání kódu tak, aby specifické typy elementů však můžete omezit pomocí zahájením literálu hledané výrazy s určitých znaků. Filtr hledání můžete také rychle změnit výběrem tlačítka na **přejít na** nástrojů dialogové okno pole. Tlačítka, které změnit typ filtry jsou na levé straně a tlačítka, které změnit rozsah vyhledávání se na pravé straně.

![Přejděte na členy](../ide/media/vside_navigation_toolbar.png)

### <a name="filter-to-a-specific-type-of-code-element"></a>Filtrovat na konkrétní typ. element kódu

Chcete-li zúžit hledání tak, aby určitý typ element kódu, můžete do vyhledávacího pole zadejte předponu nebo vyberte jednu z pěti ikony filtru:

Předpona | Ikona | Zástupce | Popis
:----: | ---- | -------- | ---
\#     | ![Ikona symbol](media/gotoall_symbolicon.png) | **CTRL**+**1**, **Ctrl**+**S** | Přejděte na zadaný symbol
f      | ![Soubor ikony](media/gotoall_fileicon.png)     | **CTRL**+**1**, **Ctrl**+**F** | Přejděte do určeného souboru
m      | ![Ikona členu](media/gotoall_membericon.png) | **CTRL**+**1**, **Ctrl**+**M** | Přejděte k zadanému členu
t      | ![Ikony typu](media/gotoall_typeicon.png)     | **CTRL**+**1**, **Ctrl**+**T** | Přejděte na zadaný typ.
:      | ![Ikona čáry](media/gotoall_lineicon.png)     | **CTRL**+**G**         | Přejděte na zadané číslo řádku

### <a name="filter-to-a-specific-location"></a>Filtrovat na konkrétní umístění

Upřesněte hledání do určitého umístění, vyberte jednu z ikon dvě dokumentu:

Ikona | Popis
---- | ---
![Aktuální dokumentu](media/gotoall_currentdocument.png) | Prohledat pouze aktuální dokument
![Externí dokumenty](media/gotoall_external.png) | Vyhledávání externí dokumentů kromě těch, které umístěný v projekt nebo řešení

## <a name="camel-casing"></a>CamelCase

Pokud používáte [camelCase](https://en.wikipedia.org/wiki/Camel_case) ve vašem kódu můžete najít elementy kódu rychlejší zadáním velkých písmen názvu element kódu. Například, pokud má váš kód typu s názvem `CredentialViewModel`, můžete zúžit hledání tak, že zvolíte **typ** filtru (**t**) a pak zadáním stejně velkých písmen názvu (`CVM`) v Přejděte do dialogu. Tato funkce může být užitečné, pokud má váš kód dlouhé názvy.

![Přejděte do okna - hledání s kapitálek](../ide/media/vside_capitalsearch.png)

## <a name="settings"></a>Nastavení

Vyberte ikonu zařízení ![Ikona zařízení](media/gotoall_gear.png) Umožňuje změnit, jak tato funkce funguje:

Nastavení | Popis
------- | ---
Karta náhled použití | Ihned zobrazit vybranou položku v karta Náhled prostředí IDE
Zobrazit podrobnosti    | V okně zobrazit projektu, soubor, řádku a souhrnné informace z dokumentační komentáře
Okno centra   | Přesuňte toto okno k centru horní části editoru kódu, místo pravé horní

## <a name="see-also"></a>Viz také

- [Přejděte kódu](../ide/navigating-code.md)
- [Dialogové okno Přejít na řádek](../ide/reference/go-to-line.md)
- [Přejít k definici a Náhled definice](../ide/go-to-and-peek-definition.md)