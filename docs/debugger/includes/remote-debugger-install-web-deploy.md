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
ms.openlocfilehash: c22ba73b464f91bf3036541304cdf94e8660970d
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2018
---
1. Pokud máte v úmyslu nasadit aplikace pomocí nástroje nasazení webu v sadě Visual Studio, nainstalujte nejnovější verzi nástroje nasazení webu na serveru.

    Instalovat nasazení webu, použijte [instalačního programu webové platformy (WebPI)](https://www.microsoft.com/web/downloads/platform.aspx). (Odkaz Web Platform Installer ze služby IIS, vyberete **IIS** v levém podokně Správce serveru. Pravým tlačítkem na server a vyberte **Správce Internetové informační služby (IIS)**.)

    Ve webové platformy zjistíte na kartě aplikací nasazení webu. Můžete také získat instalační program přímo z [Microsoft Download Center](https://www.microsoft.com/search/result.aspx?q=webdeploy&form=dlc). 

2. Ověřte, zda Web Deploy je spuštěna správně otevřením **ovládací panely > systém a zabezpečení > Nástroje pro správu > služby** a ujistěte se, že **Služba agenta pro nasazení webu** běží (na název služby se liší v starší verze).

    Pokud není spuštěna Služba agenta, spusťte ji. Pokud není přítomen vůbec, přejděte na **ovládací panely > programy > odinstalovat program**, Najít **Microsoft Web Deploy <version>** . Zvolit **změnu** instalaci a ujistěte se, že zvolíte **bude nainstalována na místní pevný disk** pro součásti nástroje nasazení webu. Proveďte kroky instalace změnu.