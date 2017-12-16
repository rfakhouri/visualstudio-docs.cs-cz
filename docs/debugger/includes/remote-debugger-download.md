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
ms.openlocfilehash: 7e911686d1f8bff191c439f4fc2b92c37d60a31f
ms.sourcegitcommit: 38097344f3ff74ba7b03bcfa45910015ca6bc2be
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/11/2017
---
1.  Na zařízení nebo server počítač, který chcete ladit (spíše než počítač spuštění sady Visual Studio) získáte správnou verzi nástrojů pro vzdálenou.

    |Version|Odkaz|Poznámky|
    |-|-|-|
    |Visual Studio 2017 verze 15,5|[Nástroje pro vzdálenou](https://www.visualstudio.com/downloads/#remote-tools-for-visual-studio-2017)|Vždy stáhněte verzi odpovídající operační systém zařízení (x86 nebo x64). Pokud je povolený režim rozšířené zabezpečení (Windows Server), musíte přidat nový důvěryhodných serverů po zobrazení výzvy.|
    |Visual Studio 2017 (starší)|[Nástroje pro vzdálenou](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202017)|Nástroje pro vzdálenou pro dřívější verze Visual Studio 2017 jsou dostupné z My.VisualStudio.com. Pokud se zobrazí výzva, spojení skupině volné Essentials vývojáře Visual Studio nebo Přihlaste se pomocí vašeho předplatného sady Visual Studio ID. Pokud je povolený režim rozšířené zabezpečení (Windows Server), musíte přidat nový důvěryhodných serverů po zobrazení výzvy.|
    |Visual Studio 2015 Update 3|[Nástroje pro vzdálenou](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202015)|Pokud se zobrazí výzva, spojení skupině volné Essentials vývojáře Visual Studio nebo Přihlaste se pomocí vašeho předplatného sady Visual Studio ID. Pokud je povolený režim rozšířené zabezpečení (Windows Server), musíte přidat nový důvěryhodných serverů po zobrazení výzvy.|
    |Visual Studio 2015 (starší)|[Nástroje pro vzdálenou](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202015)|Pokud se zobrazí výzva, spojení skupině volné Essentials vývojáře Visual Studio nebo Přihlaste se pomocí vašeho předplatného sady Visual Studio ID. Pokud je povolený režim rozšířené zabezpečení (Windows Server), musíte přidat nový důvěryhodných serverů po zobrazení výzvy.|
    |Visual Studio 2013|[Nástroje pro vzdálenou](https://msdn.microsoft.com/library/bt727f1t(v=vs.120).aspx#BKMK_Installing_the_Remote_Tools)|Stáhněte si stránku v dokumentaci k sadě Visual Studio 2013|
    |Visual Studio 2012|[Nástroje pro vzdálenou](https://msdn.microsoft.com/library/bt727f1t(v=vs.110).aspx#BKMK_Installing_the_Remote_Tools)|Stáhněte si stránku v dokumentaci sady Visual Studio 2012|
  
2.  Na této stránce zvolte verzi těchto nástrojů, který odpovídá operačního systému (x 86, x64 nebo ARM) a stažení nástrojů pro vzdálenou.
  
    > [!IMPORTANT]
    >  Doporučujeme že nainstalovat nejnovější verzi nástrojů pro vzdálenou, který se shoduje s vaší verzí sady Visual Studio. Neshoda verze se nedoporučují. Kromě toho musíte nainstalovat vzdálenou nástroje, které mají stejnou architekturu jako operační systém, na kterém chcete nainstalovat. Jinými slovy Pokud chcete ladit 32bitovou aplikaci na vzdáleném počítači s operačním systémem 64-bit, nainstalujte 64bitovou verzi nástrojů pro vzdálenou na vzdáleném počítači. 
    >   
    >  Prostor 3 přechod z ARM na x64 architektura. Na ARM verzi nástrojů pro vzdálenou není k dispozici pro Visual Studio 2017. Pro Visual Studio 2015 najít verzi ARM v Visual Studio 2015 RTW stahování.
  
3.  Po dokončení stahování spustitelný soubor, přejděte k další části a postupujte podle pokynů pro instalaci.

Pokud se pokusíte zkopírovat vzdáleného ladicího programu (msvsmon.exe) ke vzdálenému počítači a potom ho spusťte, mějte na paměti, **Průvodce konfigurace vzdáleného ladicího programu** (**rdbgwiz.exe**) je nainstalována pouze, když si stáhnete nástroje. Musíte použít Průvodce pro konfiguraci později, zejména pokud chcete, aby vzdálený ladicí program ke spuštění jako služba. Další informace najdete v tématu [(volitelné) konfigurovat vzdálený ladicí program jako služba](../../debugger/remote-debugging.md#bkmk_configureService).