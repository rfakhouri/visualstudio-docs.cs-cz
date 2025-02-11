---
title: Ladění spravovaného kódu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging managed code
- debugging ASP.NET Web applications, managed code
- managed code, debugging
ms.assetid: fa3aff01-c271-4aa7-b5b1-def560471c84
caps.latest.revision: 37
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 39076459f684aafce4e800ecad6341d120aac480
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65691450"
---
# <a name="debugging-managed-code"></a>Ladění spravovaného kódu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tato část popisuje běžné problémy ladění a techniky pro spravované aplikace nebo aplikace napsané v jazycích, které se zaměřují modul common language runtime, jako je například Visual Basic, C# a C++. Technik popsaných tady jsou základní techniky. Další informace najdete v tématu [pomocí ladicího programu](../debugger/debugger-basics.md).  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Diagnostické zprávy v okně Výstup](../debugger/diagnostic-messages-in-the-output-window.md)  
 Popisuje <xref:System.Diagnostics.Debug> a <xref:System.Diagnostics.Trace> třídy, se kterými můžete napsat zpráv za běhu **výstup** okna. Tyto třídy zahrnují metod výstupu, které umožňují výstup informací bez narušení provádění a informace o výstup, který také přeruší provádění, pokud je zadaná podmínka se nezdaří.  
  
 [Kontrolní výrazy ve spravovaném kódu](../debugger/assertions-in-managed-code.md)  
 Popisuje kontrolní výrazy ve spravovaném kódu, které testování podmínek, které zadáte jako argumenty `Assert` metody. Kromě toho toto téma obsahuje ukázkový kód, informace o použití <xref:System.Diagnostics.Debug> a <xref:System.Diagnostics.Trace> metody třídy, důležité informace v ladění a vydání verzí kódu, vedlejší účinky vyhodnocení argumenty, přizpůsobení vyhodnocení chování a konfigurační soubory.  
  
 [Příkazy Stop v jazyce Visual Basic](../debugger/stop-statements-in-visual-basic.md)  
 Popisuje `Stop` příkaz, který poskytuje alternativu k nastavením zarážky. Ukázkový kód je také k dispozici, spolu s porovnání mezi `Stop` příkazu a `End` příkaz, a také mezi `Stop` a `Assert` příkazu.  
  
 [Návod: Ladění formuláře systému Windows](../debugger/walkthrough-debugging-a-windows-form.md)  
 Poskytuje podrobné pokyny pro vytvoření formuláře Windows a ladění, které tvoří. Formuláře Windows, standardní součástí spravované aplikace pro Windows je jedním z nejběžnějších spravovaných aplikací. Tento návod používá Visual C# a Visual Basic, ale jsou obecně podobné techniky pro vytvoření formuláře Windows pomocí C++.  
  
 [Ladění metody OnStart](../debugger/how-to-debug-the-onstart-method.md)  
 Poskytuje příklady kódu, aby bylo možné ladit `OnStart` metody spravované služby Windows. Chcete-li ladit `OnStart` metody služby Windows, je nutné přidat pár řádků kódu a simulovat služby.  
  
 [Ladění ve smíšeném režimu](../debugger/debugging-mixed-mode-applications.md)  
 Tento článek popisuje ladění ve smíšeném režimu aplikací. To znamená, že všechny aplikace, která kombinuje nativní kód se spravovaným kódem.  
  
 [Chyba: Ladění není možné, protože v systému je povolen ladicí program jádra](../debugger/error-debugging-isn-t-possible-because-a-kernel-debugger-is-enabled-on-the-system.md)  
 Popisuje chybová zpráva, která nastane, pokud se pokusíte ladit spravovaný kód na [!INCLUDE[win7](../includes/win7-md.md)], [!INCLUDE[wiprlhext](../includes/wiprlhext-md.md)], [!INCLUDE[winxp](../includes/winxp-md.md)], [!INCLUDE[Win2kFamily](../includes/win2kfamily-md.md)], nebo systém Windows NT, který se spustil v režimu ladění.  
  
 [Optimalizace a ladění za běhu](../debugger/jit-optimization-and-debugging.md)  
 Popisuje účinky optimalizace JIT pro ladění.  
  
 [Ladění LINQ a DLINQ](../debugger/debugging-linq.md)  
 Tento článek popisuje techniky ladění dotazů LINQ.  
  
 [Návod: Ladění paralelní aplikace](../debugger/walkthrough-debugging-a-parallel-application.md)  
 Popisuje způsob použití **paralelní úlohy** a **paralelní zásobníky** nástroje windows pro ladění paralelní aplikace.  
  
## <a name="related-sections"></a>Související oddíly  
 [IntelliTrace](../debugger/intellitrace.md)  
 Najdete chyby rychleji a snadněji pomocí zaznamenávání historie spouštění vaší aplikace pomocí nástroje IntelliTrace. Krokovat zpět a vpřed mezi zaznamenané události a volání prozkoumat stav vaší aplikace na klíčových místech v čase. Ladění kódu bez nastavování velkého počtu zarážek nebo aplikací tak, jak často se restartuje. Vyžaduje Visual Studio Ultimate.  
  
 [Trasování a instrumentace aplikací](https://msdn.microsoft.com/library/773b6fc4-9013-4322-b728-5dec7a72e743)  
 Popisuje trasování, způsob, jak můžete monitorovat provádění aplikace při spuštění a instrumentaci, která zahrnuje umístění příkazů trasování na strategická místa v kódu. Toto téma obsahuje také odkazy na úvod do instrumentace a trasování, přepínače trasování, trasovat naslouchací procesy trasování kódu v aplikaci, přidání příkazů trasování do kódu aplikace a Podmíněná kompilace pomocí <xref:System.Diagnostics.Debug> a <xref:System.Diagnostics.Trace> .  
  
 [/ ASSEMBLYDEBUG](https://msdn.microsoft.com/library/94443af3-470c-41d7-83a0-7434563d7982)  
 Popisuje linkeru, která přidá <xref:System.Diagnostics.DebuggableAttribute> kód napsaný v jazyce C++. Tento atribut je potřeba pro použití ladění funkcí, jako připojení v jazyce C++.  
  
 [Ladění aplikací služby Windows](https://msdn.microsoft.com/library/63ab0800-0f05-4f1e-88e6-94c73fd920a2)  
 Poskytuje důležité informace týkající se ladění aplikace služby Windows, včetně nastavení, připojování k procesu, ladění kódu v služby `OnStart` metodu a kód v hlavní metodě, nastavovat zarážky a pomocí ovládacího prvku služby Správce spuštění, zastavení, pozastavení a pokračování ve službě.  
  
 [Ladění a profilace](https://msdn.microsoft.com/library/4a04863e-2475-46f4-bc3f-3c11510c2a4b)  
 Tento článek popisuje požadavky na konfiguraci a ladění aplikací rozhraní .NET Framework.  
  
 [Ladění skriptů a webových aplikací](../debugger/debugging-web-applications-and-script.md)  
 Popisuje běžné problémy ladění a postupy, které se můžete setkat při ladění skriptu a webové aplikace.  
 Popis nových funkcí ladění přidán v této verzi [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
 [Ladění domovské stránky](../debugger/debugging-in-visual-studio.md)  
 Obsahuje odkazy na větší části dokumentace ladění. Obsahuje informace, co je nového v ladicím programu, nastavení a příprava, zarážky, zpracování výjimek, upravit a pokračovat, ladění spravovaného kódu, ladění projektů Visual C++, ladění modelu COM a ActiveX, ladění knihoven DLL, ladění SQL a uživatele Reference k rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [Návod: Ovládací prvky ladění vlastního Windows Forms v době návrhu](https://msdn.microsoft.com/library/1fd83ccd-3798-42fc-85a3-6cba99467387)   
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Ladění v sadě Visual Studio](../debugger/debugging-in-visual-studio.md)
