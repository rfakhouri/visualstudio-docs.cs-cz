---
title: Příkazové podokno
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
dev_langs:
- VB
f1_keywords:
- VS.ImmediateWindow
helpviewer_keywords:
- design-time expression evaluation
- Immediate window
- first-chance exception notifications
ms.assetid: d33e7937-73f3-4c69-9df0-777a8713c6f2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 294a68ea3c36f47dad06d9104795b493661c40e9
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097107"
---
# <a name="immediate-window"></a>Příkazové podokno

**Okamžité** okna slouží k ladění a vyhodnocení výrazů, spuštění příkazů, tisku hodnot proměnných a tak dále. Umožňuje zadat výrazy k vyhodnocování nebo provádění ve vývojovém jazyce během ladění.

Pro zobrazení **okamžité** okno, otevřete projekt pro úpravy a pak zvolte **ladění** > **Windows** > **příkazového podokna**  nebo stiskněte klávesu **Ctrl**+**Alt**+**můžu**. Můžete také zadat **Debug.Immediate** v **příkaz** okna.

Můžete použít **okamžité** okno k vydání jednotlivých příkazů sady Visual Studio. Dostupné příkazy zahrnují `EvaluateStatement`, který slouží k přiřazení hodnoty proměnné. **Okamžité** okna také podporuje technologii IntelliSense.

## <a name="display-the-values-of-variables"></a>Zobrazení hodnot proměnných

**Okamžité** okno může být zvláště užitečné při ladění aplikace. Například pro kontrolu hodnoty proměnné `varA`, můžete použít [příkaz Tisk](../../ide/reference/print-command.md):

```cmd
>Debug.Print varA
```

Otazník (?) je alias pro `Debug.Print`, takže tento příkaz lze také zapsat:

```cmd
>? varA
```

Obě verze tohoto příkazu vrátit hodnotu proměnné `varA`.

> [!TIP]
> Vydat příkaz v sadě Visual Studio **okamžité** okna, je nutné před příkaz s znaménko (>) větší než. Chcete-li zadat více příkazů, přepněte **příkaz** okna.

## <a name="design-time-expression-evaluation"></a>Vyhodnocení výrazu v době návrhu

Můžete použít **okamžité** okna spuštění funkce nebo podprogram v době návrhu.

### <a name="execute-a-function-at-design-time"></a>Provedení funkce v době návrhu

1. Zkopírujte následující kód do [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] konzolové aplikace:

   ```vb
   Module Module1

       Sub Main()
           MyFunction(5)
       End Sub

       Function MyFunction(ByVal input as Integer) As Integer
           Return input * 2
       End Function

   End Module
   ```

2. Na **ladění** nabídky, klikněte na tlačítko **Windows**a potom klikněte na tlačítko **okamžité**.

3. Typ `?MyFunction(2)` v **okamžité** podokna a stiskněte **Enter**.

    **Okamžité** okna ICT `MyFunction` a zobrazí `4`.

Pokud funkce nebo podprogram obsahuje zarážku, sada Visual Studio přeruší provádění v odpovídajícím bodě. Potom můžete ladicí program windows prozkoumat stav vaší aplikace. Další informace najdete v části [názorný postup: Ladění v době návrhu](../../debugger/walkthrough-debugging-at-design-time.md).

Vyhodnocení výrazu času návrhu nelze použít v typech projektů, které vyžadují spuštění prostředí, včetně [!INCLUDE[trprVSTOshort](../../ide/reference/includes/trprvstoshort_md.md)] projekty, webových projektů, projektů Smart Device a projektů SQL.

### <a name="design-time-expression-evaluation-in-multi-project-solutions"></a>Vyhodnocení výrazu v době návrhu v řešení vícenásobného projektu

Při vytváření kontextu pro vyhodnocení výrazu pro dobu návrhu, odkazuje na aktuálně vybraný projekt v Průzkumníku řešení sady Visual Studio. Pokud není vybrán žádný projekt v Průzkumníku řešení, Visual Studio se pokusí zjistit hodnotu funkce podle projektu po spuštění. Pokud funkci nelze vyhodnotit v aktuálním kontextu, zobrazí se chybová zpráva. Pokud obdržíte chybu, kterou se pokoušíte vyhodnotit funkci v projektu, který není projektem po spuštění pro řešení vyberte projekt v Průzkumníku řešení a pokuste se o vyhodnocení znovu.

## <a name="enter-commands"></a>Zadejte příkazy

Zadejte znak větší (>) při vydávání příkazů sady Visual Studio **okamžité** okna. Použití **šipka nahoru** a **šipka dolů** kláves procházejte dříve vydané příkazy.

|Úloha|Řešení|Příklad|
|----------|--------------|-------------|
|Vyhodnocení výrazu.|Výraz začíná otazníkem (?) otazníkem.|`? a+b`|
|Dočasně vstoupí do příkazového řádku v režimu přímý režim (k provedení jednoho příkazu).|Zadejte příkaz zahájením literálu je větší než znaménko (>).|`>alias`|
|Přepněte do okna příkazu.|Zadejte `cmd` do okna, zahájením literálu je větší než znaménko (>).|`>cmd`|
|Přepněte zpět do okna příkazy.|Zadejte `immed` do okna bez znak větší než (>).|`immed`|

## <a name="mark-mode"></a>Režim označení

Po kliknutí na libovolný předchozí řádek v **okamžité** okna, posunete automaticky do režimu označení. To vám umožňuje vybrat, upravit a zkopírujte text z předchozích příkazů, jako by v libovolném textovém editoru a vložte je do aktuálního řádku.

## <a name="the-equals-sign"></a>Sign(=) rovná se

V okně použité ke vstupu `EvaluateStatement` příkaz určuje, zda je znak rovná se (=) interpretován jako porovnávací operátor nebo jako operátor přiřazení.

V **okamžité** okně znak rovná se (=) interpretován jako operátor přiřazení. Ano například příkaz

```cmd
>Debug.EvaluateStatement(varA=varB)
```

přiřadí hodnotu proměnné `varB` proměnné `varA`.

V **příkaz** okna, naopak znak rovná se (=) interpretován jako operátor porovnání. Nelze použít operace přiřazení v **příkaz** okna. Tak například, pokud hodnoty proměnných `varA` a `varB` jsou odlišné, pak příkaz

```cmd
>Debug.EvaluateStatement(varA=varB)
```

vrací hodnotu `False`.

## <a name="first-chance-exception-notifications"></a>Oznámení o první odpovídající výjimce

V některých konfiguracích nastavení se zobrazí oznámení o první odpovídající výjimce v **okamžité** okna.

### <a name="toggle-first-chance-exception-notifications-in-the-immediate-window"></a>Přepnout oznámení o první odpovídající výjimce do okna Příkazy

1. Na **zobrazení** nabídky, klikněte na tlačítko **ostatní Windows**a klikněte na tlačítko **výstup**.

2. Klikněte pravým tlačítkem na oblast textu **výstup** okna a potom vyberte nebo zrušte zaškrtnutí možnosti **zprávy o výjimkách**.

## <a name="see-also"></a>Viz také:

- [Procházení kódu s ladicím programem](../../debugger/navigating-through-code-with-the-debugger.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [První seznámení s ladicím programem](../../debugger/debugger-feature-tour.md)
- [Návod: Ladění v průběhu návrhu](../../debugger/walkthrough-debugging-at-design-time.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)
- [Používání regulárních výrazů v sadě Visual Studio](../../ide/using-regular-expressions-in-visual-studio.md)
