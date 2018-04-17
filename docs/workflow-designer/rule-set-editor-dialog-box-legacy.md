---
title: Pravidlo nastavte dialogové okno Editor (zastaralé) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Workflow.Activities.Rules.Design.RuleSetDialog.UI
helpviewer_keywords:
- Rule Set Editor dialog box
ms.assetid: 7cfd5df1-1115-4e5c-9b72-121f39419e83
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7284b4a318f1d6c182f1d7d27e41f6c77092ad00
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="rule-set-editor-dialog-box-legacy"></a>Pravidlo nastavte dialogové okno Editor (zastaralé)
Toto téma popisuje, jak používat **Editor nastavit pravidla** dialogové okno v Návrháři pracovních postupů starší verze systému Windows. Pomocí starší verze [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] když potřebujete cílit buď [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].

 **Editor nastavit pravidla** dialogové okno se používá k vytvoření a změna [aktivitě PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019) pravidla sad, které se serializují .rules souboru.

> [!NOTE]
> Pokud chcete otevřít soubor .rules s **Editor XML s kódováním**, nejprve je třeba nejprve zavřít okno přidružené návrháře pro pracovní postup nebo aktivity.

 Informace o tom, jak získat přístup **Editor nastavit pravidla** dialogové okno, najdete v části [postupy: vytvoření aktivitě PolicyActivity pravidlo sady (zastaralé)](../workflow-designer/how-to-create-a-policyactivity-rule-set-legacy.md).

> [!WARNING]
> Pravidla editoru starší verze [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] používané cílit buď [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)] nepodporuje cílení na více verzí.

 Následující tabulka popisuje prvky uživatelského rozhraní (UI) **Editor nastavit pravidla** dialogové okno.

|Prvek uživatelského rozhraní (UI)|Popis|
|----------------|-----------------|
|**Přidat pravidlo**|Přidá novou definici pravidla sady pravidel.|
|**Odstranit**|Odstraní vybrané pravidlo ze sady pravidel.|
|**Řetězení**|Určuje, jaký typ dál řetězení pro použití s sadu pravidel. Jsou dostupné možnosti:<br /><br /> -   **Úplné zřetězení**, která určuje používat všechny dopředného řetězení mechanismy: implicitní, metoda zapisujících a explicitní pomocí **aktualizace** funkce.<br />-   **Sekvenční**, která určuje nepoužívat dopředného řetězení.<br />-   **Pouze explicitní aktualizace**, která určuje umožní provádět jenom dál řetězení na **aktualizace** akce.<br /><br /> Další informace o dopředného řetězení najdete v tématu [pomocí aktivity aktivitě PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65004).|
|**Jméno**|Záhlaví sloupce seznamu sady pravidel. Klikněte na seznam pravidel seřadit podle názvu.|
|**Priorita**|Záhlaví sloupce seznamu sady pravidel. Klikněte na seznam pravidel seřadit podle priority.|
|**Přehodnocení**|Záhlaví sloupce seznamu sady pravidel. Klikněte na tlačítko Seřadit seznam pravidel podle typu přehodnocení.|
|**Náhled pravidla**|Záhlaví sloupce seznamu sady pravidel. Kliknutím na tlačítko Seřadit seznam pravidel ve verzi preview pravidlo podmínku a akce.|
|**Jméno:**|Zadejte název pravidla.|
|**Priorita:**|Zadejte prioritu pro pravidlo. Výchozí priorita je 0.|
|**Přehodnocení:**|Určuje, jaký typ pravidla přehodnocení používat s tímto pravidlem. Jsou dostupné možnosti:<br /><br /> -   **Vždy**, což způsobí, že pravidlo znovu vyhodnocena podle potřeby.<br />-   **Nikdy**, což způsobí, že pravidlo nikdy znovu vyhodnocena. V takovém případě pravidlo spustí jenom jednou.|
|**Aktivní**|Zkontrolujte pravidlo aktivní.|
|**Podmínky:**|Zadejte výraz podmínka pro pravidlo. Informace o syntaxi výrazu najdete v části "Zadat podmínku akce výrazy a" části této stránky.|
|**Potom akce:**|Zadejte výraz pro potom akce. Informace o syntaxi výrazu najdete v části "Zadat podmínku akce výrazy a" části této stránky.|
|**Else akce:**|Zadejte výraz Else akce. Informace o syntaxi výrazu najdete v části "Zadat podmínku akce výrazy a" části této stránky.|
|**OK**|Klikněte na tlačítko Uložit do souboru .rules sadu pravidel.|

 Další informace o sady pravidel najdete v tématu [pomocí aktivity aktivitě PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65004).

## <a name="entering-condition-and-action-expressions"></a>Zadání podmínky a akce výrazy
 Zadejte výrazy pro podmínku a pak a jinak se akce jako text v jejich odpovídajících textu oknech **Editor nastavit pravidla** dialogové okno. Můžete zadat **to.** do editoru, chcete-li pole, vlastnosti a metody používané v pracovním postupu pomocí IntelliSense – typ nabídky. Nebo můžete přímo zadat název člena pracovního postupu. Statické metody můžete volat na odkazované typy tak, že zadáte název třídy, za nímž následuje název metody.

 Logické operátory můžete přidat podmínky, jako je například AND, OR a NOT. Můžete také přidat predikáty. Predikát je binární operátor a dva operandy. Binární operátory podporována jsou ==, >, \<, > =, a < =. Podporované operandy jsou konstantní hodnoty, aritmetické funkce a oboru veřejné členy.

 Můžete určit typ pro porovnání, a můžete porovnat s **null** nebo prázdný řetězec. Lze vnořit volání členům na proměnné, která obsahuje komplexní typ, například `this.Address.State == "WA"`.

 Výrazy podporují následující operátory:

-   Relační operátory: ==, =,! =

-   Operátory porovnání: <, \<=, >, > =

-   Aritmetické operátory: +, -, *, /, MOD

-   Logické operátory: A, & &, OR a &#124; &#124;, ne,!

-   Bitové operátory: &,&#124;

 Priorita operátorů výraz dodržuje pravidla priorit operátor C#.

 Další informace o podmínkách najdete v tématu [podmínky použití v pracovních postupech](http://msdn.microsoft.com/en-us/541211f5-d382-4810-894f-71f00b34fa77).

### <a name="halt-and-update-functions"></a>Zastavení a aktualizovat funkce
 **Potom akce:** a **Else akce:** výrazy podporují **zastavení** a **aktualizace** funkce. Použít **zastavení** fungovat, zadejte **zastavení** do **pak akce:** nebo **Else akce:** textové pole. **Zastavení** akce způsobí spuštění sady pravidel zastavit okamžitě, a vrátí ovládací prvek volání kódu. Můžete použít **aktualizace** funkce se dál řetězení.

 **Aktualizace** příkaz může být vyjádřený v editoru v jednom ze dvou formách; obě forms jsou uvedeny v následujícím příkladu:

```
Update(this.Address.State)
Update("this/Address/State")
```

 Další informace o používání **aktualizace** s dopředného řetězení, přečtěte si téma [pomocí aktivity aktivitě PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65004).

## <a name="see-also"></a>Viz také

- [Aktivitě PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019)
- [Dialogové okno Vybrat sadu pravidel (starší verze)](../workflow-designer/select-rule-set-dialog-box-legacy.md)
- [Pomocí aktivity aktivitě PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65004)
- [Pomocí podmínek v pracovních postupech](http://go.microsoft.com/fwlink?LinkID=65009)