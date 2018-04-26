---
title: Ladicí program uživatelské rozhraní (XSLT)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: reference
ms.assetid: 846fdabd-e5c3-4688-9b0d-a93fbeea1b96
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 56b2767a952c566359b1c61bbdc83060bf905e99
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="debugger-user-interface-xslt"></a>Ladicí program uživatelské rozhraní (XSLT)

Toto téma popisuje ladicího programu a dialogových oken. Popisuje pouze uživateli části rozhraní, které mají ladění chování specifické XSLT.

Další informace najdete v tématu [ladění Reference k uživatelskému rozhraní](../debugger/debugging-user-interface-reference.md).

## <a name="locals-window"></a>Místní hodnoty – okno
 Místní hodnoty – okno zobrazí informace o veškeré proměnné definované v šabloně stylů. Místní hodnoty – okno obsahuje tři sloupce informací:

 **Jméno**

 Tento sloupec obsahuje názvy všech místních proměnných v aktuálním oboru. Uzel sady mají ovládacího prvku strom, který vám může procházení zobrazíte její podsložky.

 **Hodnota**

 V tomto sloupci se zobrazuje hodnota obsažených každou proměnnou. Atribut, zpracování instrukcí, komentáře, text a CData uzly zobrazení textovou hodnotu uzlu. Namespace uzly zobrazit identifikátor URI oboru názvů.

 **Typ**

 Identifikuje datový typ pro každou proměnnou, uvedené v tomto sloupci **název** sloupce.

 Místní hodnoty – okno se zobrazí také předdefinované kontextu proměnné, které sledují kontextu transformace XSLT. Následující tabulka popisuje předdefinované kontextu proměnné používané ladicí program XSLT.

|Název|Popis|
|----------|-----------------|
|`last()`|Velikost kontextu.|
|`position()`|Pozice, nebo číslo indexu uzlu, vzhledem k velikosti kontextu.|
|`self::node()`|Hodnota uzlu kontextu.|

## <a name="output-window"></a>Okno Výstup
 Ve výstupním okně zobrazí všechny chybové zprávy nebo výjimky zabezpečení, ke kterým došlo během ladění.

 Ladicí program XSLT samostatném okně používá k zobrazení výstupu ladicí program. Toto je použít k zobrazení výstupu z téhož okna **zobrazit výstup XSL** příkaz.

## <a name="task-list"></a>Seznam úloh
 V seznamu úkolů jsou uvedeny všechny chyby kompilace v šabloně stylů. Poklepáním chybu trvá kurzor na řádku došlo k chybě.

 Seznam úkolů zahrnuje všechny chyby, ke kterým došlo v blocích skriptu v souboru XSLT.

> [!NOTE]
> Ladicí program XSLT nemá žádná varování, proto se nikdy objeví v seznamu úloh.

## <a name="breakpoints-window"></a>Okno zarážky
 Zarážky, zobrazí se všechny zarážky nastavit v aktuálním projektu. Pokud toto okno se v zobrazení je přidána zarážku, okno se automaticky aktualizuje zobrazíte nové zarážek.

 Okno zarážky, by se měl chovat stejným způsobem jako ostatní ladicí programy Visual Studio.

## <a name="command-windowimmediate-window"></a>Příkaz okno/příkazové podokno
 V této verzi ladicí program XSLT není implementováno.

## <a name="watch-window"></a>Kukátko – okno
 Okno kukátka slouží k vyhodnocení proměnné. Můžete také změnit hodnoty proměnných.

 Zobrazí v okně sledovat proměnné jsou pro aktuální kontext (nejvyšší položku v zásobníku volání). Pokud změníte kontextu, okno kukátka aktualizuje a zobrazí proměnné nastavené pro tento kontext.

## <a name="call-stack-window"></a>Okno zásobník volání
 Okno zásobník volání slouží k zobrazení názvů funkce v zásobníku volání, parametry a hodnoty parametrů. Informace v zásobníku volání se zobrazí, jenom když program laděné je ve stavu pozastavení.

 Zásobník volání představuje různé kontexty, které provádění XSLT je projít. Například, pokud je volání z šablony "a" do šablony "b", šablona "a" a šablony "b" se zobrazí v okně zásobník volání s aktuální kontext na začátek seznamu. Uživatel je uvidí dotaz, který je aktuálně spuštěné.

 Pokud šablony nemají název v souboru XSLT, se používají názvy generované procesoru XSLT.

 Kliknutím na položku než v horní části seznamu označuje do prohlížeče, kde větev provádění XSLT bylo provedeno pomocí standardní zelená zvýraznění a zelená šipky.

## <a name="quickwatch-dialog-box"></a>Dialogové okno QuickWatch
 **QuickWatch** dialogové okno se používá k vyhodnocení výrazů jazyka XPath 1.0. Uzel kontextu ( `self::node()` uzlu z místní hodnoty – okno) poskytuje kontext provádění výraz XPath. Výsledek provedení výraz XPath se zobrazí v okně sledovat.

 Následující seznam popisuje určitá omezení na vyhodnocení výrazu XPath.

-   Jsou povoleny pouze integrované funkce jazyka XPath.

-   Předdefinované XSLT funkce, jako `document()`, `key()`a tak dále nejsou povoleny.

-   Uživatelem definované funkce nejsou povoleny.

Další informace najdete v tématu [postup: vyhodnocení výrazu jazyka XPath](../xml-tools/how-to-evaluate-an-xpath-expression.md).

## <a name="disassembly-window"></a>Okno zpětný překlad
 Okno zpětný překlad zobrazuje sestavení kód, který je generován kompilátoru XSLT. Toto okno lze použít stejným způsobem jako všechny ostatní windows zpětný překlad Visual Studio.

 Další informace najdete [postupy: použití okna zpětného překladu](../debugger/how-to-use-the-disassembly-window.md).

## <a name="see-also"></a>Viz také

- [Ladění XSLT](../xml-tools/debugging-xslt.md)
- [Základy ladicího programu](../debugger/debugger-basics.md)
- [Zkontrolovat proměnné v automobily a místní hodnoty – Windows v sadě Visual Studio](../debugger/autos-and-locals-windows.md)