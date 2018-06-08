---
title: Okno Výstup
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vs.build.output
- vs.debug.output
- vs.output
helpviewer_keywords:
- Output window, about Output window
- Output window
- Toolbox, removing controls
ms.assetid: d8931d88-250e-4db4-963f-2c5b3e99b45f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8e9af45262649473f9676bff80b4a238fdd642ac
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/07/2018
ms.locfileid: "34844209"
---
# <a name="output-window"></a>Výstup – okno

**Výstup** okně se zobrazí stavové zprávy pro různé funkce v integrované vývojové prostředí (IDE). Chcete-li otevřít **výstup** okně na řádku nabídek zvolte **zobrazení** > **výstup**, nebo stiskněte klávesu **Ctrl** +  **ALT**+**O**.

## <a name="toolbar"></a>Panel nástrojů

Zobrazí se následující ovládací prvky na panelu nástrojů **výstup** okno.

### <a name="show-output-from"></a>Zobrazit výstup z

Zobrazí jeden nebo více podokna výstup zobrazíte. Několika podoken informací může být k dispozici, v závislosti na tom, které nástroje v prostředí IDE použili **výstup** okna pro doručování zpráv pro uživatele.

### <a name="find-message-in-code"></a>Vyhledat zprávu v kódu

Přesune kurzor v editoru kódu na řádek, který obsahuje chyby vybrané sestavení.

### <a name="go-to-previous-message"></a>Přejít na předchozí zpráva

Změní fokus v **výstup** časové období pro předchozí chyby sestavení a Posune kurzor na řádek, který obsahuje sestavení Chyba v editoru kódu.

### <a name="go-to-next-message"></a>Přejděte na další zprávu

Změní fokus v **výstup** okno na další chyby sestavení a Posune kurzor na řádek, který obsahuje sestavení Chyba v editoru kódu.

### <a name="clear-all"></a>Vymazat vše

Vymaže celý text z **výstup** podokně.

### <a name="toggle-word-wrap"></a>Přepnout zalamování řádků

Vypíná a zapíná funkci zalamování **výstup** podokně. Pokud je na zalamování, je text v delší položky, která překračuje oblasti zobrazení zobrazí na následující řádek.

## <a name="output-pane"></a>V podokně výstupu

**Výstup** vybrané v podokně **zobrazit výstup z** seznamu zobrazí výstup ze zdroje uvedené.

## <a name="route-messages-to-the-output-window"></a>Směrování zpráv do okna výstupu

K zobrazení **výstup** vždy, když vytváříte projekt, v okně **možnosti** v dialogovém **projekty a řešení** > **obecné**  vyberte **okno zobrazit výstup při spuštění sestavení**. Zvolte souborem kódu otevřete pro úpravy, **přejít na další zprávu** a **přejít na předchozí zpráva** na **výstup** nástrojů v okně vyberte položek v  **Výstup** podokně. Když to uděláte, kurzoru v přeskočí editoru kódu na řádek kódu, kde dojde k vybraný problém.

Některé funkce IDE a příkazy v vyvolat [příkazové okno](../../ide/reference/command-window.md) poskytovat jejich výstup do **výstup** okno. Výstup z externího nástroje, jako *.bat* a *.com* soubory, které se obvykle v příkazovém okně zobrazí, se směruje na **výstup** podokně při výběru  **Použijte okno výstup** možnost [Správa externích nástrojů](../../ide/managing-external-tools.md). Mnoho dalších druhy zprávy lze zobrazit v **výstup** také podokna. Například když syntaxe Transact-SQL v uložené proceduře bude zkontrolován, cílová databáze, výsledky se zobrazí v **výstup** okno.

Můžete také programu vaše vlastní aplikace k zápisu diagnostické zprávy v době běhu **výstup** podokně. K tomu použít členy <xref:System.Diagnostics.Debug> třídy nebo <xref:System.Diagnostics.Trace> třídy v <xref:System.Diagnostics> obor názvů knihovně tříd rozhraní .NET Framework. Členové <xref:System.Diagnostics.Debug> – třída zobrazit výstup při sestavování ladění konfigurace vašeho řešení nebo produktu project; členy <xref:System.Diagnostics.Trace> třída zobrazit výstup při vytváření ladění nebo verze konfigurace. Další informace najdete v tématu [diagnostické zprávy v okně výstupu](../../debugger/diagnostic-messages-in-the-output-window.md).

V jazyce C++, můžete vytvořit vlastní kroky sestavení a události sestavení, jejichž upozornění a chyby se zobrazují a kteří se započítávají do **výstup** podokně. Stisknutím kombinace kláves **F1** na řádek výstupu, můžete zobrazit příslušné téma nápovědy. Další informace najdete v tématu [formátování výstupu vlastního kroku sestavení](/cpp/ide/formatting-the-output-of-a-custom-build-step-or-build-event).

## <a name="scroll-behavior"></a>Posuv chování

Pokud používáte automatické procházení v **výstup** okna a potom přejděte pomocí myši nebo šipka, zastaví automatické procházení. Chcete-li pokračovat v automatické procházení, stiskněte **Ctrl**+**End**.

## <a name="see-also"></a>Viz také:

- [Diagnostické zprávy v okně výstupu.](../../debugger/diagnostic-messages-in-the-output-window.md)
- [Postupy: řízení ve výstupním okně](http://msdn.microsoft.com/Library/91aebd15-8854-4a7a-9f7d-57376fb4e858)
- [Kompilace a sestavení](../../ide/compiling-and-building-in-visual-studio.md)
- [Pochopení konfigurace sestavení](../../ide/understanding-build-configurations.md)
- [Přehled knihovny tříd](/dotnet/standard/class-library-overview)