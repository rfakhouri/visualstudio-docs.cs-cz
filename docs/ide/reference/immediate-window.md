---
title: Příkazové podokno
ms.date: 02/25/2019
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e3a8315b087e259e7e1e37dfa8ab30d476bea308
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62995250"
---
# <a name="immediate-window"></a>Příkazové podokno

Použití **okamžité** okno pro ladění a vyhodnocujte výrazy, spusťte příkazy a tisku hodnot proměnných. **Okamžité** okno vyhodnotí výrazy sestavováním a pomocí aktuálně vybraného projektu.

Pro zobrazení **okamžité** okno, otevřete projekt pro úpravy a pak zvolte **ladění** > **Windows** > **příkazového podokna**  nebo stiskněte klávesu **Ctrl**+**Alt**+**můžu**. Můžete také zadat **Debug.Immediate** v **příkaz** okna.

**Okamžité** okna podporuje technologii IntelliSense.

## <a name="display-the-values-of-variables"></a>Zobrazení hodnot proměnných

**Okamžité** okna je zvlášť užitečné při ladění aplikace. Například pro kontrolu hodnoty proměnné `varA`, můžete použít [tisk – příkaz](../../ide/reference/print-command.md):

```cmd
>Debug.Print varA
```

Otazník (?) je alias pro `Debug.Print`, takže tento příkaz lze také zapsat:

```cmd
? varA
```

Obě verze tohoto příkazu vrátit hodnotu proměnné `varA`.

> [!TIP]
> Vydat příkaz v sadě Visual Studio **okamžité** okna, je nutné před příkaz s znaménko (>) větší než. Chcete-li zadat více příkazů, přepněte [příkazové okno](command-window.md).

## <a name="design-time-expression-evaluation"></a>Vyhodnocení výrazu v době návrhu

Můžete použít **okamžité** okna spuštění funkce nebo podprogram v době návrhu.

### <a name="execute-a-function-at-design-time"></a>Provedení funkce v době návrhu

1. Zkopírujte následující kód do konzolové aplikace jazyka Visual Basic:

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

2. Na **ladění** nabídce zvolte **Windows** > **okamžité**.

3. Typ `?MyFunction(2)` v **okamžité** podokna a stiskněte **Enter**.

    **Okamžité** okna ICT `MyFunction` a zobrazí `4`.

Pokud funkce nebo podprogram obsahuje zarážku, sada Visual Studio přeruší provádění v odpovídajícím bodě. Potom můžete ladicí program windows prozkoumat stav vaší aplikace. Další informace najdete v tématu [názorný postup: Ladění v době návrhu](../../debugger/walkthrough-debugging-at-design-time.md).

Vyhodnocení výrazu v době návrhu nelze použít v typech projektů, které vyžadují spuštění prostředí, včetně nástroje sady Visual Studio pro projekty pro Office, webové projekty, projektů Smart Device a projektů SQL.

### <a name="design-time-expression-evaluation-in-multi-project-solutions"></a>Vyhodnocení výrazu v době návrhu v řešení vícenásobného projektu

Při vytváření kontextu pro vyhodnocení výrazu v době návrhu, odkazuje na aktuálně vybraný projekt v Průzkumníku řešení sady Visual Studio. Pokud není vybrán žádný projekt v Průzkumníku řešení, Visual Studio se pokusí zjistit hodnotu funkce podle projektu po spuštění. Pokud funkci nelze vyhodnotit v aktuálním kontextu, obdržíte chybovou zprávu. Pokud obdržíte chybu, kterou se pokoušíte vyhodnotit funkci v projektu, který není projektem po spuštění pro řešení vyberte projekt v Průzkumníku řešení a pokuste se o vyhodnocení znovu.

## <a name="enter-commands"></a>Zadejte příkazy

Zadejte znak větší (>) při vydávání příkazů sady Visual Studio **okamžité** okna. Použití **šipka nahoru** a **šipka dolů** kláves procházejte předchozích příkazů.

|Úloha|Řešení|Příklad|
|----------|--------------|-------------|
|Vyhodnocení výrazu.|Výraz začíná otazníkem (?) otazníkem.|`? a+b`|
|Dočasně vstoupí do příkazového řádku v režimu přímý režim (k provedení jednoho příkazu).|Zadejte příkaz zahájením literálu je větší než znaménko (>).|`>alias`|
|Přepněte do okna příkazu.|Zadejte `cmd` do okna, zahájením literálu je větší než znaménko (>).|`>cmd`|
|Přepněte zpět do okna příkazy.|Zadejte `immed` do okna bez znak větší než (>).|`immed`|

## <a name="mark-mode"></a>Režim označení

Po kliknutí na libovolný předchozí řádek v **okamžité** okna, posunete automaticky do režimu označení. To vám umožňuje vybrat, upravit a zkopírujte text z předchozích příkazů, jako by v libovolném textovém editoru a vložte je do aktuálního řádku.

## <a name="examples"></a>Příklady

Následující příklad ukazuje čtyři výrazy a jejich výsledkem **okamžité** okno pro projekt jazyka Visual Basic.

```cmd
j = 2
Expression has been evaluated and has no value

? j
2

j = DateTime.Now.Day
Expression has been evaluated and has no value

? j
26
```

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
