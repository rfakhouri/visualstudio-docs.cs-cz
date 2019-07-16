---
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.openlocfilehash: 2e5782c49f26925d9eda81f04653b1a20666c6b1
ms.sourcegitcommit: 748d9cd7328a30f8c80ce42198a94a4b5e869f26
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/15/2019
ms.locfileid: "68149180"
---
1. Na vzdáleném počítači, najít a spustit **vzdálený ladicí program** z **Start** nabídky. 
   
   Pokud nemáte oprávnění správce na vzdáleném počítači, klikněte pravým tlačítkem myši **vzdálený ladicí program** aplikaci a vyberte **spustit jako správce**. V opačném případě stačí spusťte normálně.

   Pokud se chystáte připojit k procesu, který je spuštěn jako správce nebo běží pod jiným uživatelským účtem (jako je například IIS), klikněte pravým tlačítkem na **vzdálený ladicí program** aplikaci a vyberte **spustit jako správce**. Další informace najdete v tématu [spustit vzdálený ladicí program jako správce](../remote-debugging-errors-and-troubleshooting.md#run-the-remote-debugger-as-an-administrator).
   
1. Při prvním spuštění vzdáleného ladicího programu (nebo předtím, než jste nakonfigurovali) **konfigurace vzdáleného ladění** zobrazí se dialogové okno.  
  
    ![Konfigurace vzdáleného ladicího programu](../media/remotedebuggerconfwizardpage.png "konfigurace vzdáleného ladicího programu")  
  
1. Pokud rozhraní API webových služeb Windows není nainstalována, který se pouze v systému Windows Server 2008 R2, vyberte **nainstalovat** tlačítko.  
  
1. Vyberte alespoň jeden síťový typ, který chcete použít nástroje remote tools na. Pokud jsou počítače připojené do domény, je třeba zvolit první položku. Pokud jsou tyto počítače připojeny přes domácí nebo pracovní skupině, vyberte druhý nebo třetí položka podle potřeby.  
  
1. Vyberte **konfigurovat vzdálené ladění** nakonfigurovat bránu firewall a spustit vzdálený ladicí program.  
  
1. Po dokončení konfigurace **vzdálený ladicí program** zobrazí se okno.
  
    ![Vzdálený ladicí program okno](../media/remotedebuggerwindow.png "okna vzdáleného ladicího programu")
  
    Vzdálený ladicí program je nyní čeká na připojení. Použijte název serveru a port číslo zobrazené nastavit konfiguraci vzdáleného připojení v sadě Visual Studio.  
  
Chcete-li zastavit vzdáleného ladicího programu, vyberte **souboru** > **ukončovací**. Můžete restartovat z **Start** nabídky, nebo z příkazového řádku:  
  
```cmd
<Remote debugger installation directory>\msvsmon.exe
```
