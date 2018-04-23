---
title: Ladění kódu GPU | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: c7e77a5a-cb57-4b11-9187-ecc89acc8775
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4e423a36fd9477c01354c23f31afd686d79a3ba4
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="debugging-gpu-code"></a>Ladění kódu GPU
Můžete ladit kód C++, která běží na grafický procesor (GPU). Grafický procesor ladění podpory v sadě Visual Studio zahrnuje soupeření detekce spouštění procesů a připojení, a integrace do ladění systému windows.  
  
## <a name="supported-platforms"></a>Podporované platformy  
 Ladění je podporována v [!INCLUDE[win7](../debugger/includes/win7_md.md)], [!INCLUDE[win8](../debugger/includes/win8_md.md)], [!INCLUDE[winsvr08_r2](../debugger/includes/winsvr08_r2_md.md)], a [!INCLUDE[winserver8](../debugger/includes/winserver8_md.md)]. Pro ladění na emulátoru softwaru [!INCLUDE[win8](../debugger/includes/win8_md.md)], nebo [!INCLUDE[winserver8](../debugger/includes/winserver8_md.md)] je vyžadován. Pro ladění na hardware, je nutné nainstalovat ovladače grafické karty. Ne všichni dodavatelé hardwaru implementuje všechny funkce ladicího programu. Najdete v dokumentaci dodavatele pro omezení.  
  
> [!NOTE]
>  Hardware nezávislých dodavatelů, kteří chcete podporovat GPU ladění v sadě Visual Studio musíte vytvořit vlastní ovladače knihovny DLL, která implementuje rozhraní VSD3DDebug a cíle.  
  
## <a name="configuring-gpu-debugging"></a>Konfigurace ladění GPU  
 Ladicí program nelze rozdělit na procesoru kódu a kódu GPU ve stejné spuštění aplikace. Ve výchozím nastavení ladicího programu dělí na kód procesoru. Ladění kódu GPU, použijte jednu z těchto dvou kroků:  
  
-   V **ladění typ** seznam na **standardní** nástrojů vyberte **GPU pouze**.  
  
-   V **Průzkumníku řešení**, v místní nabídce pro projekt, vyberte **vlastnosti**. V **stránky vlastností** dialogové okno, vyberte **ladění**a potom vyberte **GPU pouze** v **ladicí program typu** seznamu.  
  
## <a name="launching-and-attaching-to-applications"></a>Spuštění a připojení k aplikacím  
 Ladění příkazy sady Visual Studio můžete spustit a zastavit GPU ladění. Další informace najdete v tématu [procházení kódu s ladicím programem](../debugger/navigating-through-code-with-the-debugger.md). Můžete také připojit ladicí program GPU k spuštěných procesů, ale pouze pokud se tento proces provede kódu GPU. Další informace najdete v tématu [přiřadit běžící procesy](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
## <a name="run-current-tile-to-cursor-and-run-to-cursor"></a>Spustit aktuální dlaždice kurzor a spusťte kurzoru  
 Při ladění na GPU, máte dvě možnosti pro spuštění na umístění kurzoru. Příkazy pro obě možnosti jsou dostupné v místní nabídce editoru kódu.  
  
1.  **Spustit ke kurzoru** příkaz spustí aplikaci, dokud není dosaženo umístění kurzoru pak dělí. To neznamená, že aktuální vlákno běží na pozici kurzoru; místo znamená to, že první vlákno, které dosáhne bodu kurzoru aktivuje rozdělení. V tématu [procházení kódu s ladicím programem](../debugger/navigating-through-code-with-the-debugger.md)  
  
2.  **Spustit aktuální dlaždice pro kurzor** příkaz spustí aplikaci, dokud všechny podprocesy v dlaždici aktuální nezobrazí kurzor a konce.  
  
## <a name="debugging-windows"></a>Ladění Windows  
 Pomocí určitých ladění windows můžete prozkoumat, příznak a zmrazení vláken GPU. Další informace naleznete v tématu:  
  
-   [Použití okna paralelní zásobníky](../debugger/using-the-parallel-stacks-window.md)  
  
-   [Používání okna úloh](../debugger/using-the-tasks-window.md)  
  
-   [Postupy: použití okna paralelního sledování](../debugger/how-to-use-the-parallel-watch-window.md)  
  
-   [Ladění vláken a procesů](../debugger/debug-threads-and-processes.md) (ladění umístění panelu nástrojů)  
  
-   [Postupy: použití okna vláken GPU](../debugger/how-to-use-the-gpu-threads-window.md)  
  
## <a name="data-synchronization-exceptions"></a>Výjimky synchronizace dat  
 Ladicí program můžete identifikovat několik podmínek synchronizace dat během provádění. Pokud je zjištěn stav, ladicího programu vstupuje do stavu pozastavení. Máte dvě možnosti –**rozdělit** nebo **pokračovat**. Pomocí **výjimky** dialogové okno, můžete nakonfigurovat, jestli ladicí program rozpozná tyto podmínky a také podmínky, které ho budou zalomit pro. Další informace najdete v tématu [Správa výjimek pomocí ladicího programu](../debugger/managing-exceptions-with-the-debugger.md). Můžete také **možnosti** dialogové okno k určení, že by měl ladicího programu Pokud nemění data, která je zapsán hodnota dat Ignorovat výjimky. Další informace najdete v tématu [Obecné, ladění, dialogové okno Možnosti](../debugger/general-debugging-options-dialog-box.md).  
  
## <a name="troubleshooting"></a>Poradce při potížích  
  
### <a name="specifying-an-accelerator"></a>Určení akcelerátoru  
 V kódu GPU pouze zarážek Pokud kód běží na [Accelerator::direct3d_ref –](/cpp/parallel/amp/reference/accelerator-class.md#accelerator__direct3d_ref_Data_Member) akcelerátoru (REF). Pokud nezadáte akcelerátor ve vašem kódu, akcelerátoru REF je automaticky vybraný jako **ladění typu akcelerátoru** ve vlastnostech projektu. Pokud váš kód explicitně vybere akcelerátor, akcelerátoru REF se nepoužijí během ladění a že nebude možné zarážky Pokud váš hardware GPU nemá, podpora ladění. Můžete to napravit napsáním kódu tak, aby používala akcelerátoru REF během ladění. Další informace najdete v tématu vlastnosti projektu a [používání akcelerátoru a objektů accelerator_view](/cpp/parallel/amp/using-accelerator-and-accelerator-view-objects) a [nastavení projektu pro konfiguraci ladění C++](../debugger/project-settings-for-a-cpp-debug-configuration.md).  
  
### <a name="conditional-breakpoints"></a>Podmíněné zarážky  
 Podmíněné zarážky v kódu GPU jsou podporované, ale ne každý výraz lze vyhodnotit na zařízení. Když výraz nelze vyhodnotit v zařízení, vyhodnotí se ladicí program. Ladicí program bude pravděpodobně pracovat pomaleji než zařízení.  
  
### <a name="error-there-is-a-configuration-issue-with-the-selected-debugging-accelerator-type"></a>Chyba: Není problém konfigurace u vybraného typu akcelerátoru ladění.  
 K této chybě dojde, když existuje nekonzistence mezi nastavení projektu a konfigurace v počítači, které jsou ladění na. Další informace najdete v tématu [nastavení projektu pro konfiguraci ladění C++](../debugger/project-settings-for-a-cpp-debug-configuration.md).  
  
### <a name="error-the-debug-driver-for-the-selected-debugging-accelerator-type-is-not-installed-on-the-target-machine"></a>Chyba: Ladění ovladač pro vybraný typ akcelerátoru ladění není nainstalován v cílovém počítači.  
 Tato chyba se stane, když jsou ladění na vzdálený počítač. Ladicí program nemůže zjistit až při spuštění, zda instalaci ovladačů na vzdáleném počítači. Ovladače jsou k dispozici od výrobce grafické karty.  
  
### <a name="error-timeout-detection-and-recovery-tdr-must-be-disabled-at-the-remote-site"></a>Chyba: Zjišťování časový limit a obnovení (TDR) musí být zakázáno na vzdálené lokality.  
 Je možné pro výpočty C++ AMP delší než výchozí časový interval, který je nastavený časový limit detekce Windows a procesu obnovení (TDR). Pokud k tomu dojde, je zrušená výpočet a data budou ztracena. Další informace najdete v tématu [zpracování TDRs v C++ AMP](http://go.microsoft.com/fwlink/p/?LinkId=249154).  
  
## <a name="see-also"></a>Viz také  
 [Návod: Ladění aplikace C++ AMP](/cpp/parallel/amp/walkthrough-debugging-a-cpp-amp-application)   
 [Nastavení projektu pro konfiguraci ladění jazyka C++](../debugger/project-settings-for-a-cpp-debug-configuration.md)   
 [Spustit GPU ladění v sadě Visual Studio](http://go.microsoft.com/fwlink/p/?LinkId=255381)