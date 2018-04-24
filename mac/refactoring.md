---
title: Refaktoring kódu v sadě Visual Studio pro Mac
description: Opětovné uspořádání kódu v sadě Visual Studio pro Mac přišla jednoduché prostřednictvím analýzy zdroje.
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.assetid: C7782BF3-016F-4B41-8A81-85FC540A1A8F
ms.openlocfilehash: 325c2c5ab244e9e4fc0aae4dafae7425580c2762
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="refactoring"></a>Refaktoring

Refaktoring kódu je způsob, jak změnit uspořádání, změny struktury a vysvětlení, a zajistit existující kód, který nemění celkové chování kód.

Refaktoring vytvoří zdravějších základu kódu, což funkční, čtení a udržovatelný pro jste nebo ostatní vývojáře nebo uživatele, který může získáte pomocí kódu.

Visual Studio pro Mac pro integraci s Roslyn, platformy Microsoft open source .NET kompilátoru umožňuje pro další operace refaktoringu.

## <a name="renaming"></a>Přejmenování 

*Přejmenovat* refaktoring příkaz lze použít na všechny identifikátor kód (například název třídy, název vlastnosti atd.) a najít všechny výskyty tento identifikátor je změnit. Přejmenování symbol, klikněte na něj pravým tlačítkem myši a zvolte **Refaktorovat > přejmenujte**, nebo **Cmd + R** klíče vazby:

![Přejmenování položky nabídky](media/refactoring-renaming1.png)

To bude zvýrazněte symbol a všechny odkazy na ni. Když spustíte zadáním názvu nové automaticky změní všechny odkazy ve vašem kódu a můžete signál váš dokončení přejmenováním stisknutím **Enter**:

 ![Přejmenování a identifikátor](media/refactoring-renaming2.png)

## <a name="context-actions"></a>Kontext akce

Kontext akce vám umožní prohlédnout žádný kód C# a zobrazit všechny možné refaktoringu volby. 

**Vyřešit** a **Refaktorovat** položek kontextové jsou sloučeny do jednoho *Quick Fix...*  položky, které vám poskytne všechny dostupné akce kontextu:

![Zobrazí položky kontextu](media/refactoring-context-action.png)

Ukazatele myši na některou z kontextu akcí vám poskytne náhled co bude přidat nebo odebrat z vašeho kódu.

Alternativně můžete stisknout **Alt + Enter** kdekoli v kódu:

![Možnost zadejte kontextu položky](media/refactoring-image2a.png)

Pokud chcete povolit tyto možnosti, je nutné vybrat *povolit zdroj analysis otevřených souborů* v možnostech **Visual Studio pro Mac > Předvolby > textový Editor > zdroj Analysis**:

 ![Povolení zdroje analýzy](media/refactoring-options.png)

Existuje více než 100 možných akcí, které může být navrhované, které jsou zapnutá nebo vypnutá procházením **Visual Studio pro Mac > Předvolby > zdroj Analysis > C# > kódu akce** a vyberete nebo unselecting políčko vedle položky akce:

 ![C# zdroje Analysis akce](media/refactoring-image3a.png)

### <a name="common-context-actions"></a>Běžné kontext akce

Některé z nejčastěji běžně používané kontext akce, které jsou vysvětleny níže.

#### <a name="extract-method"></a>Extrahování metody

Operace refaktoringu metoda extrakce umožňuje vytvoření nové metody extrahováním výběr kódu existujícího člena. Tato akce bude udělat dvě věci:

* Vytvoří novou metodu obsahující na vybraný úsek kódu
* Volá metodu nové na místě, kde byl vybraný úsek kódu.

##### <a name="example"></a>Příklad

1. Přidejte následující kód:

```
    class MainClass
    {

        double CalculatePyramidVolume(double baseArea, double height)
        {

            double volume = (baseArea * height) / 3;

            return volume;
        }
    }
```

2. Zvýrazněte řádek `double volume = (baseArea * height) / 3;`, klikněte na něj pravým tlačítkem a vyberte **Refaktorovat > extrahovat metodu**.

3. Vyberte, kde má být umístěn nová metoda ve vašem kódu, použijte klávesy se šipkami.


#### <a name="encapsulate-field"></a>Zapouzdření pole

Zapouzdření pole operaci vám umožní vytvořit vlastnosti z existující pole a aktualizuje kódu tak, aby odkazovaly nově vytvořený vlastnost. Vytvořením vlastnosti, který zapouzdřuje vaše pole jsou zakazuje přímý přístup k veřejné pole, což znamená, že další objekty ho nelze změnit.

Tato akce bude postupujte takto:

* Změny – modifikátor přístupu soukromé.
* Generuje metody getter a setter pro pole (Pokud je toto pole je jen pro čtení, v takovém případě bude pouze vytvářet příjemce).


## <a name="source-analysis"></a>Analýza zdroje

Analýza zdroj bude analyzovat kód za chodu potenciální chyby podtržení a porušení stylu a poskytnutí automatické opravy jako kontext akce. 

Kdykoli můžete zobrazit všechny výsledky analýzy zdroje pro všechny soubory, zobrazením posuvníku na pravé straně textového editoru:

 ![Zdroj bočním panelu analýzy](media/refactoring-image4a.png)

Pokud kliknete na kruh v horní části, můžete iterovat každý návrh s nejvyšší závažnost problémy zobrazující první. Ukazatele myši na jednotlivé výsledek nebo řádek zobrazí problém, který může být připojen prostřednictvím kontextu akce:

 ![Zdrojová položka analýzy](media/refactoring-image5.png)

