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
ms.openlocfilehash: cfb41cf6274238fef2de9b74496a33fba110e04f
ms.sourcegitcommit: fb73b56d45ebc0386cd4de1a706ba9e20c59daf1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/03/2018
---
Musíte mít oprávnění správce na vzdáleném počítači.  
  
1.  Vyhledejte aplikaci vzdáleného ladicího programu. (Msvsmon.exe najít v umístění, kde je nainstalován, nebo otevřete nabídku Start a vyhledejte **vzdáleného ladicího programu**.)
  
     Pokud používáte vzdálený ladicí program na vzdáleném serveru, budete moct klikněte pravým tlačítkem na aplikaci vzdáleného ladicího programu a vybrat **spustit jako správce**. Pokud jste neběží na vzdáleném serveru, právě spusťte normálně.
  
3.  Při spuštění nástrojů pro vzdálenou poprvé (nebo předtím, než jste ji nakonfigurovali), **konfigurace vzdáleného ladění** zobrazí se dialogové okno.  
  
     ![RemoteDebuggerConfWizardPage](../media/remotedebuggerconfwizardpage.png "RemoteDebuggerConfWizardPage")  
  
4.  Pokud API služby systému Windows není nainstalována (která se dělá jenom v systému Windows Server 2008 R2), vyberte **nainstalovat** tlačítko.  
  
5.  Vyberte typy síťových chcete pomocí nástrojů pro vzdálenou na. Musí být vybrán alespoň jeden typ sítě. Pokud jsou počítače připojené přes domény, musíte zvolit první položka. Pokud jsou počítače připojené přes domácí nebo pracovní skupině, musíte vybrat druhý a třetí položku podle potřeby.  
  
6.  Zvolte **konfigurace vzdálené ladění** nakonfigurovat bránu firewall, a spusťte nástroj.  
  
7.  Po dokončení konfigurace, zobrazí se okno vzdáleného ladicího programu.
  
     ![RemoteDebuggerWindow](../media/remotedebuggerwindow.png "RemoteDebuggerWindow")
  
     Vzdálený ladicí program nyní čeká na připojení. Poznamenejte si název serveru a portu číslo, které se zobrazí, protože tento název musí odpovídat konfiguraci, kterou použijete později v sadě Visual Studio.  
  
 Po dokončení ladění a muset zastavit vzdáleného ladicího programu, klikněte na tlačítko **soubor > ukončení** v okně. Můžete restartovat z **spustit** nabídky nebo z příkazového řádku:  
  
 **\<Visual Studio Instalační adresář > \Common7\IDE\Remote ladicí program\\< x86, x64 nebo Appx > \msvsmon.exe**.  
