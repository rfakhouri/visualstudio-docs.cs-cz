---
title: Ladění kódu GPU | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: c7e77a5a-cb57-4b11-9187-ecc89acc8775
caps.latest.revision: 23
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: bb5342dc2b5da3d1192aadbbea186b5b21f179f3
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65691554"
---
# <a name="debugging-gpu-code"></a>Ladění kódu GPU
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete ladit kód jazyka C++, na kterém běží na grafický procesor (GPU). Podpora v sadě Visual Studio pro ladění GPU zahrnuje závodu detekce spouštění procesů a připojení, a integraci do ladění systému windows.  
  
## <a name="supported-platforms"></a>Podporované platformy  
 Ladění se podporuje na [!INCLUDE[win7](../includes/win7-md.md)], [!INCLUDE[win8](../includes/win8-md.md)], [!INCLUDE[winsvr08_r2](../includes/winsvr08-r2-md.md)], a [!INCLUDE[winserver8](../includes/winserver8-md.md)]. Pro ladění v softwarovém emulátoru [!INCLUDE[win8](../includes/win8-md.md)], nebo [!INCLUDE[winserver8](../includes/winserver8-md.md)] je povinný. Pro ladění na hardwaru, je nutné nainstalovat ovladače pro grafickou kartu. Ne všichni dodavatelé hardwaru implementuje všechny funkce ladicího programu. Omezení v dokumentaci dodavatele.  
  
> [!NOTE]
> Nezávislí dodavatelé hardwaru, kteří požadují pro podporu ladění GPU v sadě Visual Studio vytvořit knihovnu DLL, která implementuje rozhraní VSD3DDebug a cíle své vlastní ovladače.  
  
## <a name="configuring-gpu-debugging"></a>Konfigurace ladění GPU  
 Ladicí program nelze přerušit na kód CPU a GPU kódu v rámci stejné aplikace. Ve výchozím nastavení ladicí program přeruší na procesoru kódu. Ladění kódu GPU, použijte jeden z následujících dvou kroků:  
  
- V **ladění typu** seznamu **standardní** nástrojů, zvolte **pouze GPU**.  
  
- V **Průzkumníka řešení**, v místní nabídce projektu zvolte **vlastnosti**. V **stránky vlastností** dialogu **ladění**a pak vyberte **pouze GPU** v **typ ladicího programu** seznamu.  
  
## <a name="launching-and-attaching-to-applications"></a>Spuštění a připojení k aplikacím  
 Příkazy ladění sady Visual Studio můžete použít ke spuštění a zastavení ladění GPU. Další informace najdete v tématu [procházení kódu s ladicím programem](../debugger/navigating-through-code-with-the-debugger.md). Ladicí program GPU můžete také připojit ke spuštěnému procesu, ale pouze pokud tento proces spouští kód GPU. Další informace najdete v tématu [připojení k běžící procesy](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
## <a name="run-current-tile-to-cursor-and-run-to-cursor"></a>Spustit aktuální blok ke kurzoru a spustit ke kurzoru  
 Při ladění na GPU, máte dvě možnosti, provést do pozice kurzoru. Příkazy pro obě možnosti jsou dostupné v místní nabídce editoru kódu.  
  
1. **Spustit ke kurzoru** příkaz spustí vaši aplikaci, až dosáhne umístění kurzoru a poté se přeruší. To neznamená, že aktuální vlákno je spuštěn na kurzoru; Místo toho, znamená to, že první vlákno, kterou půjde používat bod kurzor aktivuje přerušení. Zobrazit [procházení kódu s ladicím programem](../debugger/navigating-through-code-with-the-debugger.md)  
  
2. **Spustit aktuální dlaždici ke kurzoru** příkaz spustí vaši aplikaci, dokud všechna vlákna v aktuálním bloku nedosáhnou kurzoru a konce.  
  
## <a name="debugging-windows"></a>Ladění Windows  
 S použitím určitých ladění systému windows, můžete zkoumat, příznak a zablokovat vlákna GPU. Další informace naleznete v tématu:  
  
- [Použití okna Paralelní zásobníky](../debugger/using-the-parallel-stacks-window.md)  
  
- [Použití okna úloh](../debugger/using-the-tasks-window.md)  
  
- [Postupy: Použití okna Paralelní sledování](../debugger/how-to-use-the-parallel-watch-window.md)  
  
- [Ladění vláken a procesů](../debugger/debug-threads-and-processes.md) (panelu nástrojů umístění ladění)  
  
- [Postupy: Použití okna vláken GPU](../debugger/how-to-use-the-gpu-threads-window.md)  
  
## <a name="data-synchronization-exceptions"></a>Výjimky synchronizace dat  
 Ladicí program můžete identifikovat několik podmínek synchronizace dat během provádění. Když se zjistí podmínku, ladicí program přejde do stavu přerušení. Máte dvě možnosti –**přerušit** nebo **pokračovat**. S použitím **výjimky** dialogovém okně můžete nakonfigurovat, zda ladicí program zjistí tyto podmínky a také jakých podmínek se přeruší pro. Další informace najdete v tématu [Správa výjimek pomocí ladicího programu](../debugger/managing-exceptions-with-the-debugger.md). Můžete také použít **možnosti** dialogové okno k určení, že ladicí program by měl Ignorovat výjimky, pokud se data, která je napsána nemění hodnotu data. Další informace najdete v tématu [Obecné, ladění, dialogové okno Možnosti](../debugger/general-debugging-options-dialog-box.md).  
  
## <a name="troubleshooting"></a>Poradce při potížích  
  
### <a name="specifying-an-accelerator"></a>Určení akcelerátoru  
 Zarážky v kódu GPU jsou pouze přístupů, pokud je kód spuštěn [Accelerator::direct3d_ref –](https://msdn.microsoft.com/library/a514b1a7-3b3f-4011-be6c-f7b0d9a42663) akcelerátorů (odkaz). Pokud nezadáte akcelerátoru ve vašem kódu, je automaticky vybrán jako akcelerátor REF **typ akcelerátoru ladění** ve vlastnostech projektu. Pokud váš kód explicitně vybere akcelerátoru, akcelerátor REF se nepoužije během ladění a nebudou fungovat zarážky, pokud váš hardware GPU neobsahuje podporu ladění. Můžete to napravit napsáním kódu tak, aby používala akcelerátor REF během ladění. Další informace najdete ve vlastnostech projektu a [používání akcelerátoru a objektů accelerator_view](https://msdn.microsoft.com/library/18f0dc66-8236-4420-9f46-1a14f2c3fba1) a [nastavení projektu pro C++ konfiguraci ladění](../debugger/project-settings-for-a-cpp-debug-configuration.md).  
  
### <a name="conditional-breakpoints"></a>Podmíněné zarážky  
 Podmíněné zarážky v kódu GPU jsou podporované, ale ne každý výraz lze vyhodnotit na zařízení. Výraz nejde vyhodnotit na zařízení, se vyhodnotí na ladicí program. Ladicí program je pravděpodobně poběží pomaleji než zařízení.  
  
### <a name="error-there-is-a-configuration-issue-with-the-selected-debugging-accelerator-type"></a>Chyba: Existuje problém konfigurace u vybraný typ akcelerátoru ladění.  
 K této chybě dochází, když existuje nekonzistence mezi nastavení projektu a konfigurace, který právě ladíte na počítač. Další informace najdete v tématu [nastavení projektu pro konfiguraci ladění jazyka C++](../debugger/project-settings-for-a-cpp-debug-configuration.md).  
  
### <a name="error-the-debug-driver-for-the-selected-debugging-accelerator-type-is-not-installed-on-the-target-machine"></a>Chyba: Na cílovém počítači není nainstalován ovladač ladicího programu pro vybraný typ akcelerátoru ladění.  
 K této chybě dochází, když provádíte ladění na vzdáleném počítači. Ladicí program nemůže určit až do doby běhu, zda jsou ovladače nainstalované ve vzdáleném počítači. Jsou k dispozici u výrobce grafickou kartu ovladače.  
  
### <a name="error-timeout-detection-and-recovery-tdr-must-be-disabled-at-the-remote-site"></a>Chyba: Časový limit zjišťování a obnovení (TDR) musí být zakázáno ve vzdálené lokalitě.  
 Je možné pro výpočtů C++ AMP překročit výchozí časový interval, který je nastaven tak, že Windows časový limit zjišťování a procesu obnovení (TDR). Pokud k tomu dojde, výpočet je zrušen a data budou ztracena. Další informace najdete v tématu [TDRs zpracování v jazyce C++ AMP](http://go.microsoft.com/fwlink/p/?LinkId=249154).  
  
## <a name="see-also"></a>Viz také  
 [Návod: Ladění aplikace C++ AMP](https://msdn.microsoft.com/library/40e92ecc-f6ba-411c-960c-b3047b854fb5)   
 [Nastavení projektu pro konfiguraci ladění jazyka C++](../debugger/project-settings-for-a-cpp-debug-configuration.md)   
 [Spustit ladění GPU v sadě Visual Studio](http://go.microsoft.com/fwlink/p/?LinkId=255381)
