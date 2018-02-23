---
title: "Ladění spravovaného kódu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
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
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 6710f5065622161b60e7a40cc136cdb2ba2b0b72
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2018
---
# <a name="debugging-managed-code"></a>Ladění spravovaného kódu

Tato část popisuje běžné problémy ladění a techniky pro spravované aplikace nebo aplikace napsané v jazyce cílených modul common language runtime, jako je například jazyka Visual Basic, C# a C++. Technik popsaných v tomto poli se vysoké úrovně techniky. Další informace najdete v tématu [používání ladicího programu](../debugger/debugger-basics.md).

## <a name="in-this-section"></a>V tomto oddílu

[Diagnostické zprávy v okně výstupu.](../debugger/diagnostic-messages-in-the-output-window.md)  
Popisuje <xref:System.Diagnostics.Debug> a <xref:System.Diagnostics.Trace> třídy, se kterými můžete napsat běhu zprávy a pokuste se **výstup** okno. Tyto třídy zahrnují výstup metody, které umožní informace výstup, aniž by vás informace o provádění a výstupu, který také dělí spuštění, pokud je zadaná podmínka selže.

[Kontrolní výrazy ve spravovaném kódu](../debugger/assertions-in-managed-code.md)  
Popisuje kontrolní výrazy ve spravovaném kódu, které testovací podmínky, které zadáte jako argumenty pro `Assert` metody. Kromě toho toto téma obsahuje ukázkový kód, informace o používání <xref:System.Diagnostics.Debug> a <xref:System.Diagnostics.Trace> metody třídy, důležité informace o ladění a vydání verze kódu, vedlejší účinky assert argumenty, přizpůsobení assert chování a konfigurační soubory.

[Stop – příkazy v jazyce Visual Basic](../debugger/stop-statements-in-visual-basic.md)  
Popisuje `Stop` příkaz, který poskytuje alternativu k nastavení boru přerušení. Ukázkový kód je také k dispozici, společně s porovnání mezi `Stop` příkaz a `End` příkaz, a také mezi `Stop` a `Assert` příkaz.

[Návod: Ladění formuláře systému Windows](../debugger/walkthrough-debugging-a-windows-form.md)  
Poskytuje podrobné pokyny pro vytvoření formuláře Windows a ladění tohoto formuláře. Formuláři Windows standardní součást spravovaných aplikací systému Windows, je jedním nejběžnější spravovaných aplikací. Tento návod používá Visual C# a Visual Basic, ale jsou obecně podobné techniky pro vytvoření formuláře Windows s jazykem C++.

[Ladění metody OnStart](../debugger/how-to-debug-the-onstart-method.md)  
Obsahuje příklady kódu a umožní vám k ladění `OnStart` metoda spravované služby systému Windows. Chcete-li ladit `OnStart` metoda služby systému Windows, musíte přidat pár řádků kódu k simulaci službu.

[Ladění ve smíšeném režimu](../debugger/debugging-mixed-mode-applications.md)  
Popisuje, ladění aplikací ve smíšeném režimu. To znamená jakékoli aplikace, která kombinuje nativního kódu se spravovaným kódem.

[Chyba: Ladění není možné, protože v systému je povolen ladicí program protokolu Kernel.](../debugger/error-debugging-isn-t-possible-because-a-kernel-debugger-is-enabled-on-the-system.md)  
Popisuje, k níž dojde, pokud se pokusíte ladění spravovaného kódu na chybovou zprávu [!INCLUDE[win7](../debugger/includes/win7_md.md)], [!INCLUDE[wiprlhext](../debugger/includes/wiprlhext_md.md)], [!INCLUDE[winxp](../code-quality/includes/winxp_md.md)], [!INCLUDE[Win2kFamily](../code-quality/includes/win2kfamily_md.md)], nebo systém Windows NT, která byla spuštěna v režimu ladění.

[Optimalizace a ladění JIT](../debugger/jit-optimization-and-debugging.md)  
Popisuje účinky optimalizaci JIT ladění.

[Ladění LINQ a DLINQ](../debugger/debugging-linq.md)  
Popisuje postupy pro ladění dotazů LINQ.

[Návod: Ladění paralelní aplikace](../debugger/walkthrough-debugging-a-parallel-application.md)  
Popisuje postup použití **paralelních úloh** a **paralelní zásobníky** nástroje systému windows k ladění paralelní aplikace.

## <a name="related-sections"></a>Související oddíly

[IntelliTrace](../debugger/intellitrace.md) vyhledání chyby rychlejší a snazší podle zaznamenávání historie provádění vaší aplikace s použitím technologie IntelliTrace. Krok zpět a předávat přes zaznamenaná událostí a zkontrolujte stav vaší aplikace na klíčové body v čase volání. Ladění kódu bez nastavení spoustu zarážky nebo restartování aplikace jako často. Requires Visual Studio Enterprise.

[Trasování a instrumentace aplikací](/dotnet/framework/debug-trace-profile/tracing-and-instrumenting-applications)  
Popisuje trasování, způsob, jak můžete monitorovat aplikace při spuštění a instrumentace, který zahrnuje umístění trasovacích příkazů na strategická místa v kódu. Toto téma obsahuje také odkazy na úvod do instrumentace a trasování, přepínače trasování, naslouchací procesy trasování kódu v aplikaci, přidání příkazů trasování do kódu aplikace a Podmíněná kompilace pomocí trasování <xref:System.Diagnostics.Debug> a <xref:System.Diagnostics.Trace> .

[/ASSEMBLYDEBUG](/cpp/build/reference/assemblydebug-add-debuggableattribute)  
Popisuje možnosti linkeru, který přidává <xref:System.Diagnostics.DebuggableAttribute> na kód zapisovaný s C++. Tento atribut je potřeba k použití ladění funkcí, jako připojení s jazykem C++.

[Ladění aplikace služby systému Windows](/dotnet/framework/windows-services/how-to-debug-windows-service-applications)  
Poskytuje důležité informace pro ladění aplikace služby systému Windows, včetně nastavení, se připojuje k procesu, ladění kódu v rámci služby `OnStart` metoda a kód v metodě hlavní nastavení zarážek a použití služby ovládacího prvku Správce spuštění, zastavení, pozastavení a pokračování služby.

[Ladění a profilování](/dotnet/framework/debug-trace-profile/index)  
Popisuje ladění aplikací rozhraní .NET Framework a požadavky na konfiguraci.

[Ladění skriptu a webových aplikací](../debugger/debugging-web-applications-and-script.md)  
Popisuje běžné problémy ladění a techniky, se můžete setkat při ladění skriptů a webových aplikací.

[Co je nového v ladicím programu sady Visual Studio 2015](../debugger/what-s-new-for-the-debugger-in-visual-studio.md)  
Popis v této verzi se přidaly nové funkce ladění [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].

[Ladění domovské stránky](../debugger/debugger-feature-tour.md)  
Obsahuje odkazy na větší části ladění dokumentaci. Obsahuje informace, co je nového v ladicí program, nastavení a příprava, zarážky, zpracování výjimek, upravit a pokračovat, ladění spravovaného kódu, ladění projektů Visual C++, ladění modelu COM a prvků ActiveX, ladění knihoven DLL, ladění SQL a uživatele odkazy na rozhraní.

## <a name="see-also"></a>Viz také

[Návod: Ladění vlastních Windows Forms – ovládací prvky v době návrhu](/dotnet/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time)
[zabezpečení ladicího programu](../debugger/debugger-security.md)
[ladění v sadě Visual Studio](../debugger/index.md) 
 [ Prohlídka funkce ladicí program](../debugger/debugger-feature-tour.md)