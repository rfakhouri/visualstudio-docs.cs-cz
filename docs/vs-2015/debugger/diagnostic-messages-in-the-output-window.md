---
title: Diagnostické zprávy v okně výstupu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.output
dev_langs:
- FSharp
- VB
- CSharp
- C++
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
caps.latest.revision: 19
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 60f8da2430e1c84af3c26be31c6de561291c8c6e
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65695299"
---
# <a name="diagnostic-messages-in-the-output-window"></a>Diagnostické zprávy v okně Výstup
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete napsat zpráv za běhu do okna výstup pomocí třídy ladění a trasování, které jsou součástí <xref:System.Diagnostics> knihovny tříd. Pokud pouze výstup v ladicí verzi programu používejte třídu ladění. Použijte trasovací třídu, pokud chcete výstup v ladění i vydání verze.  
  
## <a name="output-methods"></a>Výstup metody  
 <xref:System.Diagnostics.Trace> a <xref:System.Diagnostics.Debug> třídy poskytují metody pro následující výstup:  
  
- Různé `Write` metody, které výstup s informacemi bez narušení provádění. Nahraďte tyto metody `Debug.Print` metodu použitou v předchozích verzích jazyka Visual Basic.  
  
- <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> a <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> metody, které přeruší informace o provádění a výstupy, pokud je zadaná podmínka se nezdaří. Ve výchozím nastavení `Assert` metoda zobrazí informace v dialogovém okně. Další informace najdete v tématu [kontrolní výrazy ve spravovaného kódu](../debugger/assertions-in-managed-code.md).  
  
- <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=fullName> a <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=fullName> metody, které vždy přeruší a vypíše informace. Ve výchozím nastavení `Fail` metody zobrazení informací v dialogovém okně.  
  
  Kromě programu si z vaší aplikace **výstup** okna můžete zobrazit informace o:  
  
- Moduly ladicí program má načten nebo byla uvolněna.  
  
- Výjimky, které jsou vyvolány.  
  
- Procesy, které ukončíte.  
  
- Vlákna, která ukončíte.  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Okno výstup](../ide/reference/output-window.md)   
 [Trasování a instrumentace aplikací](https://msdn.microsoft.com/library/773b6fc4-9013-4322-b728-5dec7a72e743)   
 [Úvod do trasování a instrumentace](https://msdn.microsoft.com/e924e57c-33cf-4b0e-9e7f-a45d13e38f2c)   
 [C#, F#a typy projektů jazyka Visual Basic](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)
