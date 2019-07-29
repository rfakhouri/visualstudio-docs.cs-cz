---
title: Odeslat zprávy do okna výstup | Microsoft Docs
ms.date: 11/08/2018
ms.topic: conceptual
helpviewer_keywords:
- diagnostic messages [C#]
- System.Diagnostics.Debug class, Output window
- messages, diagnostic
- Debug.Print replacements
- diagnosis
- Output window, diagnostic messages
- System.Diagnostics.Trace class, Output window
- Trace class, diagnostic messages
- diagnostics
- debugger, Output window
- debugging [Visual Studio], diagnostic messages in Output window
- Debug class
ms.assetid: 386e9524-be17-4573-83fb-4f7c5cae0be0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 47b563f58d08a732ec224bb8bbf47ad807c4e81d
ms.sourcegitcommit: ce1ab8a25c66a83e60eab80ed8e1596fe66dd85c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/29/2019
ms.locfileid: "68605374"
---
# <a name="send-messages-to-the-output-window"></a>Odesílání zpráv do okna výstupu

Můžete zapisovat zprávy za běhu do okna **výstup** pomocí <xref:System.Diagnostics.Debug> třídy nebo <xref:System.Diagnostics.Trace> <xref:System.Diagnostics> třídy, která je součástí knihovny tříd. Použijte třídu <xref:System.Diagnostics.Debug> , pokud chcete výstup pouze v *ladicí* verzi programu. Použijte třídu <xref:System.Diagnostics.Trace> , pokud chcete výstup v *ladicí* verzi i ve *verzi Release* .

## <a name="output-methods"></a>Metody výstupu
 Třídy <xref:System.Diagnostics.Trace> a<xref:System.Diagnostics.Debug> poskytují následující metody výstupu:

- Různé `Write` metody, které výstupní informace bez přerušení provádění. Tyto metody nahrazují `Debug.Print` metodu použitou v předchozích verzích Visual Basic.

- <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>a <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> metody, které přeruší spuštění a výstupní informace v případě, že se zadaná podmínka nezdařila. Ve výchozím nastavení `Assert` metoda zobrazí informace v dialogovém okně. Další informace naleznete v tématu [kontrolní výrazy ve spravovaném kódu](../debugger/assertions-in-managed-code.md).

- Metody <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=fullName> a<xref:System.Diagnostics.Trace.Fail%2A?displayProperty=fullName> , které vždy přeruší spuštění a výstupní informace. Ve výchozím nastavení `Fail` metody zobrazují informace v dialogovém okně.

V okně **výstup** se taky můžou zobrazit informace o:

- Moduly, které ladicí program načetl nebo uvolní.

- Výjimky, které jsou vyvolány.

- Procesy, které se ukončí.

- Vlákna, která se ukončí.

## <a name="see-also"></a>Viz také:
- [Zabezpečení ladicího programu](../debugger/debugger-security.md)
- [Okno výstup](../ide/reference/output-window.md)
- [Trasování a instrumentace aplikací](/dotnet/framework/debug-trace-profile/tracing-and-instrumenting-applications)
- [C#typy F#projektů, a Visual Basic](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)
- [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)
