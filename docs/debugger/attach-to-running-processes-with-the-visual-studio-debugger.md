---
title: Připojení ke spuštěným procesům pomocí ladicího programu v sadě Visual Studio | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 05/18/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.processes.attach
- vs.debug.process
- vs.debug.programs
- vs.debug.detaching
- vs.debug.processes
- vs.debug.error.attach
- vs.debug.remotemachine
dev_langs:
- CSharp
- FSharp
- C++
- VB
helpviewer_keywords:
- remote debugging, attaching to programs
- processes, attaching to running processes
- Attach to Process dialog box
- debugging [Visual Studio], attaching to processes
- debugger, processes
ms.assetid: 27900e58-090c-4211-a309-b3e1496d5824
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fe345773cfa4a91789681969623e2174db60c54c
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="attach-to-running-processes-with-the-visual-studio-debugger"></a>Připojení ke spuštěným procesům pomocí ladicího programu sady Visual Studio
Ladicí program Visual Studio můžete připojit k spuštěných procesů na místním nebo vzdáleném počítači. Jakmile je proces spuštěný, klikněte na tlačítko **ladění > připojit k procesu** (nebo stiskněte klávesu **CTRL + ALT + P**) otevřete **připojit k procesu** dialogové okno.

Tato funkce slouží k ladění aplikací, které jsou spuštěny v místním nebo vzdáleném počítači, ladění více procesů současně nebo ladění aplikace, která nebyla vytvořena v sadě Visual Studio. Je často užitečné, pokud chcete ladit aplikace, ale (z jakéhokoli důvodu) nebyla spuštěna aplikace ze sady Visual Studio s ladicím programem připojen. Například pokud běží aplikace bez ladicího programu a stiskněte tlačítko výjimku, může potom připojíte k procesu spuštění aplikace zahájíte ladění.

> [!TIP]
> Nejste si jistí jestli budete muset použít **připojit k procesu** pro váš scénář ladění? V tématu [běžné scénáře ladění](#BKMK_Scenarios). Pokud chcete k ladění aplikací ASP.NET, které byly nasazeny do služby IIS najdete v tématu [vzdáleného ladění ASP.NET ve vzdáleném počítači IIS](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md).

##  <a name="BKMK_Attach_to_a_running_process"></a> Připojit k spuštěných procesů v místním počítači  
 Aby bylo možné se připojit k procesu, musíte znát název procesu (najdete v části [běžné scénáře ladění](#BKMK_Scenarios) několik běžné názvy proces).
  
1.  V sadě Visual Studio, vyberte **ladění > připojit k procesu** (nebo stiskněte klávesu **CTRL + ALT + P**).

    Pokud chcete rychle připojte k procesu místo, přečtěte si téma [připojte k procesu](#BKMK_reattach).
  
2.  V **připojit k procesu** dialogové okno pole, vyhledejte program, který chcete připojit z **dostupné procesy** seznamu.  

     Pokud chcete rychle vybrat proces, který chcete, zadejte první písmeno názvu procesu. Pokud neznáte název procesu, přečtěte si téma [běžné scénáře ladění](#BKMK_Scenarios).
     
     ![DBG_Basics_Attach_To_Process](../debugger/media/DBG_Basics_Attach_To_Process.png "DBG_Basics_Attach_To_Process") 
  
     Pokud je proces spuštěný v rámci jiného uživatelského účtu, vyberte **Zobrazit procesy od všech uživatelů** zaškrtávací políčko.
  
3.  V **přiřadit** Ujistěte se, zda je uveden typ bude ladění kódu. Výchozí hodnota **automatické** nastavení se pokusí určit, jaký typ kódu, kterou chcete ladit. Chcete-li typ kódu nastavit ručně, proveďte následující  
  
    1.  V **připojit k** pole, klikněte na tlačítko **vyberte**.  
  
    2.  V **vybrat typ kódu** dialogové okno, klikněte na tlačítko **ladění tyto typy kódu** a vyberte typy k ladění.  
  
    3.  Click **OK**.  
  
4.  Klikněte na tlačítko **připojit**.

##  <a name="BKMK_Attach_to_a_process_on_a_remote_computer"></a> Připojit k procesu ve vzdáleném počítači  
 Aby bylo možné se připojit k procesu, musíte znát název procesu (najdete v části [běžné scénáře ladění](#BKMK_Scenarios) několik běžné názvy proces). Podrobnější pokyny pro aplikace ASP.NET, které jsou nasazené do služby IIS najdete v tématu [vzdáleného ladění ASP.NET ve vzdáleném počítači IIS](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md). Pro jiné aplikace bude pravděpodobně možné k hledání názvu procesu ve Správci úloh.
  
 Při použití **připojit k procesu** dialogové okno, můžete vybrat jiný počítač, který je nastaven pro vzdálené ladění. Další informace najdete v tématu [vzdálené ladění](../debugger/remote-debugging.md). Pokud jste vybrali vzdálený počítač, můžete zobrazit seznam dostupných procesů spuštěných na tomto počítači a připojit k jednomu nebo více procesů pro ladění.
  
 **Výběr vzdáleného počítače:**  

1. V sadě Visual Studio, vyberte **ladění > připojit k procesu** (nebo stiskněte klávesu **CTRL + ALT + P**).

    Pokud chcete rychle připojte k procesu místo, přečtěte si téma [připojte k procesu](#BKMK_reattach).

2.  V **připojit k procesu** dialogové okno, vyberte odpovídající připojení typu z **přenosu** seznamu. **Výchozí** správné nastavení většině případů je.

    **Přenosu** nastavení přetrvá mezi relace ladění. 
  
3.  Použití **kvalifikátor** pole se seznamem zvolte název vzdáleného počítače pomocí jedné z následujících metod:  
  
    1.  Zadejte název do **kvalifikátor** pole se seznamem.
    
        >**Poznámka:** Pokud v dalších krocích, nemůžete připojit pomocí název vzdáleného počítače, použijte IP adresu. (Číslo portu mohou být zobrazeny automaticky po výběru proces. Můžete také ji mohou zadat ručně. Na následující ilustraci 4020 je výchozí port pro vzdálený ladicí program.)  

        Pokud chcete použít **najít** tlačítko, budete muset [otevřete UDP port 3702](../debugger/remote-debugger-port-assignments.md) na serveru.
  
    2.  Klikněte na šipku rozevíracího seznamu, který je připojen k **kvalifikátor** seznamu pole a v rozevíracím seznamu vyberte název počítače.  
  
    3.  Klikněte **najít** vedle položky**kvalifikátor** seznamu otevřete **vyberte připojení vzdáleného ladicího programu** dialogové okno. **Vyberte připojení vzdáleného ladicího programu** dialogové okno seznam všech zařízení, které jsou na vaše místní dílčí net a jakékoli zařízení, které je přímo připojený k počítači pomocí kabelu Ethernet. Klikněte na počítač nebo zařízení a pak klikněte na tlačítko **vyberte**. 
  
     **Kvalifikátor** nastavení přetrvá mezi ladění relací pouze v případě úspěšného připojení ladění vyskytuje v této kvalifikátor.
     
4.  Klikněte na tlačítko **aktualizovat**.

      **Dostupné procesy** seznamu se zobrazí automaticky při otevření **procesy** dialogové okno. Procesy můžete spustit a zastavit na pozadí při otevřené dialogové okno. Však obsah nejsou vždy aktuální. V seznamu můžete obnovit kdykoli chcete zobrazit aktuální seznam procesů, kliknutím na **aktualizovat**. 
     
4.  V **připojit k procesu** dialogové okno pole, vyhledejte program, který chcete připojit z **dostupné procesy** seznamu.

     Pokud chcete rychle vybrat proces, který chcete, zadejte první písmeno názvu procesu. Pokud neznáte název procesu, přečtěte si téma [běžné scénáře ladění](#BKMK_Scenarios).
  
     Pokud je proces spuštěný v rámci jiného uživatelského účtu, vyberte **Zobrazit procesy od všech uživatelů** zaškrtávací políčko.
     
5.  Klikněte na tlačítko **připojit**.

## <a name="BKMK_reattach"></a> Připojte k procesu

Můžete rychle připojte k procesy, které byly dříve přiřazená výběrem **ladění > připojte k procesu...** (**Shift + Alt + P**). Když zvolíte tento příkaz, ladicí program se hned pokusí připojit k poslednímu procesy, které jste připojili pomocí **připojit k procesu** dialogové okno.

Ladicí program se znovu připojit při prvním pokusu shodovat s předchozí ID procesu a poté, pokud to nepomůže, pomocí odpovídajících na předchozí název procesu. Pokud nejsou nalezeny žádné shody, nebo pokud máte více procesů nalezen se stejným názvem, pak se **připojit k procesu** dialogové okno se zobrazí, ve kterém můžete vybrat proces správné.

> [!NOTE]
> **Připojte k procesu** příkaz je nového ve Visual Studio 2017.

## <a name="additional-info"></a>Další informace

Můžete se dá připojit k více programy při ladění, ale pouze jeden program je aktivní v ladicím programu kdykoli. Můžete nastavit v aktivní aplikaci **ladění umístění** panelu nástrojů nebo **procesy** okno.  
  
Pokud se pokusíte připojit k procesu vlastníkem nedůvěryhodné uživatelský účet, zobrazí se pole potvrzovací dialogové okno upozornění zabezpečení. Další informace najdete v části [upozornění zabezpečení: připojení k procesu vlastněných nedůvěryhodné uživatelem může být nebezpečný. Pokud tyto informace nezdá nebo si nejste jistí, nepřipojujte tohoto procesu](../debugger/security-warning-attaching-to-a-process-owned-by-an-untrusted-user-can-be-dangerous-if-the-following-information-looks-suspicious-or-you-are-unsure-do-not-attach-to-this-process.md).  
  
V některých případech při ladění v relaci vzdálené plochy (Terminálové služby) **dostupné procesy** seznamu nezobrazí všechny dostupné procesy. Pokud používáte Visual Studio jako uživatel, který má omezená uživatelský účet, **dostupné procesy** seznamu nezobrazí procesy, které jsou spuštěné v relaci 0, který se používá pro služby a jiné procesy serveru, včetně w3wp.exe. Problém můžete vyřešit tak, že spustíte [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] pod účtem správce nebo spuštěním [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] v konzole serveru místo relaci Terminálové služby. Pokud ani jedno z těchto řešení je možné, třetí možnost je k připojení do procesu spuštěním `vsjitdebugger.exe -p` *ProcessId* z příkazového řádku systému Windows. Můžete určit pomocí tlist.exe id procesu. Pokud chcete získat tlist.exe, stáhněte a nainstalujte ladicích nástrojů pro systém Windows, k dispozici na [WDK a WinDbg stahování](http://go.microsoft.com/fwlink/?LinkId=168279).

## <a name="BKMK_Scenarios"></a> Běžné scénáře ladění

Můžete zjistit, jestli budete muset použít **připojit k procesu** a jaký proces připojit, několik běžných scénářů ladění zde se zobrazují (seznam není vyčerpávající). Kde další pokyny jsou k dispozici, poskytujeme odkazy.

Pro některé typy aplikací (jako jsou aplikace UWP), nemusíte připojit přímo k název procesu, ale použít **ladění nainstalován balíček aplikace** nabídky možnost místo (viz tabulka).

> [!NOTE]
> Informace o základní ladění v sadě Visual Studio najdete v tématu [Začínáme s ladicím programem](../debugger/getting-started-with-the-debugger.md).

|Scénář|Ladění – metoda|Název procesu|Poznámky a odkazy|
|-|-|-|-|
|Ladění spravovaným nebo nativním aplikace v místním počítači|Použití připojit k procesu nebo [standardní ladění](../debugger/getting-started-with-the-debugger.md)|*AppName*.exe|Rychle se dostat k dialogových oken, použijte **CTRL + ALT + P** a pak zadejte první písmeno názvu procesu.|
|Ladění aplikací ASP.NET v místním počítači po spuštění aplikace bez ladicí program|Použití připojit k procesu|iiexpress.exe|To může být užitečné k vytvoření fungující aplikace načíst rychlejší, jako třeba (např.) při vytváření profilu. |
|Vzdálené ladění rozhraní ASP.NET 4 nebo 4.5 na serveru se službou IIS|Pomocí nástrojů pro vzdálenou a připojit k procesu|W3wp.exe|V tématu [vzdáleného ladění ASP.NET ve vzdáleném počítači služby IIS](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)|
|Vzdálené ladění ASP.NET Core na server služby IIS|Pomocí nástrojů pro vzdálenou a připojit k procesu|DotNet.exe|Nasazování aplikací, najdete v části [publikování do služby IIS](https://docs.asp.net/en/latest/publishing/iis.html). Ladění, najdete v části [vzdáleného ladění ASP.NET Core ve vzdáleném počítači služby IIS](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)|
|Ladění jiné typy podporované aplikace na proces serveru|Pomocí nástrojů pro vzdálenou (Pokud je vzdálený server) a připojit k procesu|Iexplore.exe nebo jinými procesy|V případě potřeby použijte Správce úloh k identifikaci procesu. V tématu [vzdálené ladění](../debugger/remote-debugging.md) a v dalších částech v tomto tématu|
|Vzdálené ladění aplikace na ploše systému Windows|Nástroje pro vzdálenou a F5|Není k dispozici| V tématu [vzdálené ladění](../debugger/remote-debugging.md)|
|Vzdálené ladění aplikace Universal (UWP), OneCore, HoloLens a IoT|Ladění nainstalovanou aplikaci balíčku|Není k dispozici|V tématu [ladění balíčku aplikace nainstalována](debug-installed-app-package.md) místo použití **připojit k procesu**|
|Ladění aplikace univerzální aplikace pro Windows (UWP), OneCore, HoloLens a IoT, které jste nezahájili ze sady Visual Studio|Ladění nainstalovanou aplikaci balíčku|Není k dispozici|V tématu [ladění balíčku aplikace nainstalována](debug-installed-app-package.md) místo použití **připojit k procesu**|  
  
> [!NOTE]
>  V ladicím programu pro připojení k kód napsaný v jazyce C++ kód potřebuje pro vydávání `DebuggableAttribute`. Můžete přidat to kódu automaticky pomocí propojení s [/ASSEMBLYDEBUG](/cpp/build/reference/assemblydebug-add-debuggableattribute) – možnost linkeru.

## <a name="what-debugger-features-can-i-use"></a>Jaké funkce ladicí program můžete použít?

Úplné funkce ladicího programu sady Visual Studio (např. zarážek) používat při připojování k procesu, spustitelný soubor se musí přesně shodovat místního zdroje a symboly (tedy ladicí program musí být schopen načíst správný [symbolů soubory (.pbd) ](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)). Ve výchozím nastavení to vyžaduje sestavení ladicí verze.

Pro vzdálené ladění scénáře musí mít zdrojový kód (nebo kopii zdrojový kód) otevřený v sadě Visual Studio. Binární soubory kompilované aplikace ve vzdáleném počítači musí pocházet ze ve stejném sestavení jako v místním počítači.

V některých místní ladění scénářích můžete ladit v sadě Visual Studio s žádný přístup ke zdroji Pokud správný symbol soubory k dispozici v aplikaci (ve výchozím nastavení, vyžaduje sestavení ladicí verze). Další informace najdete v tématu [zadejte symbolů a zdrojové soubory](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).
  
##  <a name="BKMK_Troubleshoot_attach_errors"></a> Řešení potíží s chybami připojení  
 Když ladicí program připojí k spuštěných procesů, tento proces může obsahovat jeden nebo více typů kódu. Zobrazí a vybrán v typy kódu k můžete připojit ladicí program **vybrat typ kódu** dialogové okno.  
  
 V některých případech můžete úspěšně připojit ladicí program na typ jeden kód, ale ne k jinému typu kódu. Tomu může dojít, pokud se pokoušíte připojit k procesu, který je spuštěn ve vzdáleném počítači. Vzdálený počítač může mít vzdáleného ladění nainstalovány pro některé typy kódu, ale ne pro ostatní součásti. Může dojít také pokud se pokusíte připojit k minimálně dva procesy pro ladění přímé databáze. Ladění SQL podporuje připojení jenom jednoho procesu.  
  
 Pokud ladicího programu připojit k některé, ale ne všechny typy kódu, zobrazí se zpráva, identifikace typy, které se nepodařilo připojit.  
  
 Pokud ladicí program úspěšně připojí k alespoň jeden kód typu, můžete přejít k ladění procesu. Bude moct ladění pouze typy kódu, které byly úspěšně připojil. Předchozí zpráva příklad ukazuje, že typ kód skriptu se nepodařilo připojit. Proto nebude moci ladit kód skriptu v rámci procesu. Kód skriptu v procesu bude i nadále spustit, ale nebude moci nastavit zarážky, zobrazení dat nebo provádění jiných operací ladění ve skriptu.  
  
 Pokud chcete podrobnější informace o Proč se nepodařilo připojit k typu kód ladicího programu, můžete zkusit znovu připojit pouze tento typ kódu.  
  
 **Konkrétní informace o Proč se nepodařilo připojit typ kódu**  
  
1.  Odpojení od proces. Na **ladění** nabídky, klikněte na tlačítko **odpojte všechny**.  
  
2.  Připojte se k procesu výběru pouze jeden kódem typu.  
  
    1.  V **připojit k procesu** dialogovém okně vyberte procesu **procesy k dispozici** seznamu.  
  
    2.  Klikněte na tlačítko **vyberte**.  
  
    3.  V **vybrat typ kódu** dialogové okno, vyberte **ladění tyto typy kódu** a typ kódu, který se nepodařilo připojit. Vymažte jakýkoli jiný kód.  
  
    4.  Click **OK**. **Vybrat typ kódu** dialog se zavře.  
  
    5.  V **připojit k procesu** dialogové okno, klikněte na tlačítko **Attach**.  
  
     Tento čas, připojení se nezdaří úplně a zobrazí se konkrétní chybová zpráva.  
  
## <a name="see-also"></a>Viz také  
 [Ladění více procesů](../debugger/debug-multiple-processes.md)   
 [Ladění za běhu](../debugger/just-in-time-debugging-in-visual-studio.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)