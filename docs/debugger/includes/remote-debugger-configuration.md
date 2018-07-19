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
ms.openlocfilehash: b6e312f7e1913a8b4533c0127b966dc3ac0d981d
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/11/2018
ms.locfileid: "38809256"
---
Musí mít oprávnění správce na vzdáleném počítači.  
  
1.  Vyhledejte aplikaci vzdálený ladicí program. (Najít msvsmon.exe do umístění, ve kterém je nainstalovaný, nebo otevřete nabídku Start a vyhledejte **vzdálený ladicí program**.)
  
     Pokud používáte vzdálený ladicí program na vzdáleném serveru, můžete klikněte pravým tlačítkem na aplikaci vzdálený ladicí program a zvolte **spustit jako správce**. Pokud vy nespouštíte na vzdáleném serveru, stačí spusťte normálně.
  
3.  Při spuštění nástroje remote tools poprvé (nebo předtím, než jste ji nakonfigurovali), **konfigurace vzdáleného ladění** zobrazí se dialogové okno.  
  
     ![RemoteDebuggerConfWizardPage](../media/remotedebuggerconfwizardpage.png "RemoteDebuggerConfWizardPage")  
  
4.  Pokud není nainstalováno rozhraní API služby Windows (který se stane pouze v systému Windows Server 2008 R2), zvolte **nainstalovat** tlačítko.  
  
5.  Vyberte typy sítí, chcete, aby na použití nástrojů remote tools. Musí být vybrán alespoň jeden typ sítě. Pokud jsou počítače připojené do domény, je třeba zvolit první položku. Pokud jsou tyto počítače připojeny přes domácí nebo pracovní skupině, musíte zvolit druhý nebo třetí položka podle potřeby.  
  
6.  Zvolte **konfigurovat vzdálené ladění** ke konfiguraci brány firewall a spusťte nástroj.  
  
7.  Po dokončení konfigurace se zobrazí v okně vzdáleného ladicího programu.
  
     ![RemoteDebuggerWindow](../media/remotedebuggerwindow.png "RemoteDebuggerWindow")
  
     Vzdálený ladicí program je nyní čeká na připojení. Poznamenejte si název serveru a port číslo, které se zobrazí, protože tento název musí odpovídat konfiguraci, kterou použijete později v sadě Visual Studio.  
  
 Po dokončení ladění a potřeba zastavit vzdáleného ladicího programu, klikněte na tlačítko **soubor > ukončení** v okně. Můžete restartovat z **Start** nabídky nebo z příkazového řádku:  
  
 **\<Vzdálený ladicí program instalační adresář >\\< x86, x64, ARM, ARM64 nebo Appx > \msvsmon.exe**.  
