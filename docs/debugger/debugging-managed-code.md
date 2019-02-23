---
title: Ladění spravovaného kódu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging managed code
- debugging ASP.NET Web applications, managed code
- managed code, debugging
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 14dc53413f646718b85ec9ea43d968dc9f64a96f
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56719312"
---
# <a name="debugging-managed-code"></a>Ladění spravovaného kódu

Tato část popisuje běžné problémy ladění a techniky pro spravované aplikace nebo aplikace napsané v jazycích, které se zaměřují modul common language runtime, jako je například Visual Basic, C# a C++. Technik popsaných tady jsou základní techniky. [Nejdřív se podívejte na ladicí program](../debugger/debugger-feature-tour.md).

## <a name="in-this-section"></a>V tomto oddílu

[Diagnostické zprávy v okně výstupu](../debugger/diagnostic-messages-in-the-output-window.md) popisuje <xref:System.Diagnostics.Debug> a <xref:System.Diagnostics.Trace> třídy, se kterými můžete napsat zpráv za běhu **výstup** okna. Tyto třídy zahrnují metod výstupu, které umožňují výstup informací bez narušení provádění a informace o výstup, který také přeruší provádění, pokud je zadaná podmínka se nezdaří.

[Kontrolní výrazy ve spravovaného kódu](../debugger/assertions-in-managed-code.md) popisuje kontrolní výrazy ve spravovaném kódu, které testování podmínek, které zadáte jako argumenty `Assert` metody. Kromě toho toto téma obsahuje ukázkový kód, informace o použití <xref:System.Diagnostics.Debug> a <xref:System.Diagnostics.Trace> metody třídy, důležité informace v ladění a vydání verzí kódu, vedlejší účinky vyhodnocení argumenty, přizpůsobení vyhodnocení chování a konfigurační soubory.

[Příkazy Stop v jazyce Visual Basic](../debugger/stop-statements-in-visual-basic.md) popisuje `Stop` příkaz, který poskytuje alternativu k nastavením zarážky. Ukázkový kód je také k dispozici, spolu s porovnání mezi `Stop` příkazu a `End` příkaz, a také mezi `Stop` a `Assert` příkazu.

[Návod: Ladění formuláře Windows](../debugger/walkthrough-debugging-a-windows-form.md) poskytuje podrobné pokyny pro vytvoření formuláře Windows a ladění, které tvoří. Formuláře Windows, standardní součástí spravované aplikace pro Windows je jedním z nejběžnějších spravovaných aplikací. Tento návod používá Visual C# a Visual Basic, ale jsou obecně podobné techniky pro vytvoření formuláře Windows pomocí C++.

[Ladění metody OnStart](../debugger/how-to-debug-the-onstart-method.md) poskytuje příklady kódu, aby bylo možné ladit `OnStart` metody spravované služby Windows. Chcete-li ladit `OnStart` metody služby Windows, je nutné přidat pár řádků kódu a simulovat služby.

[Ladění ve smíšeném režimu](../debugger/debugging-mixed-mode-applications.md) popisuje ladění ve smíšeném režimu aplikací. To znamená, že všechny aplikace, která kombinuje nativní kód se spravovaným kódem.

[Chyba: Ladění není možné, protože v systému je povolen ladicí program jádra](../debugger/error-debugging-isn-t-possible-because-a-kernel-debugger-is-enabled-on-the-system.md) popisuje chybová zpráva, která nastane, pokud se pokusíte ladit spravovaný kód na [!INCLUDE[win7](../debugger/includes/win7_md.md)], [!INCLUDE[wiprlhext](../debugger/includes/wiprlhext_md.md)], [!INCLUDE[winxp](../code-quality/includes/winxp_md.md)], [!INCLUDE[Win2kFamily](../code-quality/includes/win2kfamily_md.md)], nebo systém Windows NT, který obsahuje byl spuštěn v režimu ladění.

[Optimalizace JIT a ladění](../debugger/jit-optimization-and-debugging.md) popisuje účinky optimalizace JIT pro ladění.

[Ladění LINQ a DLINQ](../debugger/debugging-linq.md) popisuje techniky ladění dotazů LINQ.

[Návod: Ladění paralelní aplikace](../debugger/walkthrough-debugging-a-parallel-application.md) popisuje způsob použití **paralelní úlohy** a **paralelní zásobníky** nástroje windows pro ladění paralelní aplikace.

## <a name="related-sections"></a>Související oddíly

[IntelliTrace](../debugger/intellitrace.md) najít chyby rychleji a snadněji pomocí zaznamenávání historie spouštění vaší aplikace pomocí nástroje IntelliTrace. Krokovat zpět a vpřed mezi zaznamenané události a volání prozkoumat stav vaší aplikace na klíčových místech v čase. Ladění kódu bez nastavování velkého počtu zarážek nebo aplikací tak, jak často se restartuje. Vyžaduje Visual Studio Enterprise.

[Trasování a instrumentace aplikací](/dotnet/framework/debug-trace-profile/tracing-and-instrumenting-applications) popisuje trasování, způsob, jak můžete monitorovat provádění aplikace při spuštění a instrumentaci, která zahrnuje umístění příkazů trasování na strategická místa v kódu. Toto téma obsahuje také odkazy na úvod do instrumentace a trasování, přepínače trasování, trasovat naslouchací procesy trasování kódu v aplikaci, přidání příkazů trasování do kódu aplikace a Podmíněná kompilace pomocí <xref:System.Diagnostics.Debug> a <xref:System.Diagnostics.Trace> .

[/ ASSEMBLYDEBUG](/cpp/build/reference/assemblydebug-add-debuggableattribute) popisuje linkeru, která přidá <xref:System.Diagnostics.DebuggableAttribute> kód napsaný v jazyce C++. Tento atribut je potřeba pro použití ladění funkcí, jako připojení v jazyce C++.

[Ladění aplikace služby Windows](/dotnet/framework/windows-services/how-to-debug-windows-service-applications) poskytuje důležité informace týkající se ladění aplikace služby Windows, včetně nastavení, připojování k procesu, ladění kódu v služby `OnStart` metodu a kód v hlavní Metoda, nastavovat zarážky a pomocí Správce řízení služeb spustit, zastavit, pozastavení a pokračování ve službě.

[Ladění a profilování](/dotnet/framework/debug-trace-profile/index) popisuje požadavky na konfiguraci a ladění aplikací rozhraní .NET Framework.

[Ladění skriptů a webových aplikací](/visualstudio/debugger/how-to-enable-debugging-for-aspnet-applications) popisuje běžné ladění problémů a techniky, které můžete narazit při ladění skriptu a webové aplikace.

[Co je nového v ladicím programu sady Visual Studio 2015](../debugger/what-s-new-for-the-debugger-in-visual-studio.md) Popis nových funkcí ladění přidán v této verzi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].

[Ladění domovské stránky](../debugger/debugger-feature-tour.md) obsahuje odkazy na větší části dokumentace ladění. Obsahuje informace, co je nového v ladicím programu, nastavení a příprava, zarážky, zpracování výjimek, upravit a pokračovat, ladění spravovaného kódu, ladění projektů Visual C++, ladění modelu COM a ActiveX, ladění knihoven DLL, ladění SQL a uživatele Reference k rozhraní.

## <a name="see-also"></a>Viz také:

[Návod: Ovládací prvky ladění vlastního Windows Forms v době návrhu](/dotnet/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time)
[zabezpečení ladicího programu](../debugger/debugger-security.md)
[ladění v sadě Visual Studio](../debugger/index.md) 
 [ První pohled na ladicí program](../debugger/debugger-feature-tour.md)