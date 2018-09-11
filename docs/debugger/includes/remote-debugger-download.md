---
title: Vzdálený ladicí program ke stažení
description: Stáhněte si odkazy pro vzdálený ladicí program
services: ''
author: mikejo5000
ms.service: ''
ms.topic: include
ms.date: 05/23/2018
ms.author: mikejo
ms.custom: include file
ms.openlocfilehash: a9867acf2a0877322b85d25c3af781ccfdd3f58c
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2018
ms.locfileid: "44343189"
---
1.  Na zařízení nebo server počítač, který chcete ladit (nikoli na počítači sadu Visual Studio) získáte správná verze nástrojů remote tools.

    |Version|Odkaz|Poznámky|
    |-|-|-|
    |Visual Studio 2017 (nejnovější verze)|[Vzdálené nástroje](https://visualstudio.microsoft.com/downloads/?q=remote+tools#remote-tools-for-visual-studio-2017)|Nejnovější verze nástrojů remote tools je kompatibilní se všemi verzemi sady Visual Studio 2017. Kdykoli stáhněte verzi, která odpovídá operačního systému zařízení (x 86, x64 nebo ARM64). V systému Windows Server, naleznete v tématu [odblokovat stahování souborů](../../debugger/remote-debugging-unblock-file-download.md) nápovědu ke stažení nástroje remote tools.|
    |Visual Studio 2015|[Vzdálené nástroje](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202015)|Nástroje Remote tools for Visual Studio 2015 jsou k dispozici My.VisualStudio.com. Pokud se zobrazí výzva, připojte se k bezplatné [Visual Studio Dev Essentials](https://visualstudio.microsoft.com/dev-essentials/) programu, nebo se přihlaste pomocí ID předplatného sady Visual Studio. V systému Windows Server, naleznete v tématu [odblokovat stahování souborů](../../debugger/remote-debugging-unblock-file-download.md) nápovědu ke stažení nástroje remote tools.|
    |Visual Studio 2013|[Vzdálené nástroje](/previous-versions/visualstudio/visual-studio-2013/bt727f1t(v=vs.120)#Installing_the_Remote_Tools)|Stáhněte si stránku v dokumentaci k sadě Visual Studio 2013|
    |Visual Studio 2012|[Vzdálené nástroje](/previous-versions/visualstudio/visual-studio-2012/bt727f1t(v=vs.110)#BKMK_Installing_the_Remote_Tools)|Stáhněte si stránku v dokumentaci k sadě Visual Studio 2012|

2.  Na stránce pro stahování zvolte verzi nástrojů, který odpovídá operačnímu systému (x86, x64, ARM a ARM64) a stáhněte si nástroje remote tools.

    > [!IMPORTANT]
    >  Doporučujeme nainstalovat nejnovější verzi nástrojů remote tools pro vaši verzi sady Visual Studio. Nejnovější verze (například 15.8) je kompatibilní s předchozími verzemi (například 15.0); starší verze však nejsou kompatibilní s novější verzí. Kromě toho musíte nainstalovat nástroje remote tools, které mají stejnou architekturu jako operační systém, na kterém chcete nainstalovat. Jinými slovy Pokud chcete ladit 32bitovou aplikaci na vzdáleném počítači s 64bitovým operačním systémem, musíte nainstalovat 64bitová verze produktu remote tools na vzdáleném počítači.
    >
    >  Pro ladění ve Windows 10 na zařízeních ARM, klikněte na tlačítko ARM64 stáhnout k dispozici v nejnovější verzi nástrojů remote Tools.  Pro zařízení s Windows RT zvolte verzi ARM, která je k dispozici soubor ke stažení Visual Studio 2015 RTW.

3.  Po dokončení stahování spustitelného souboru, přejděte k další části a postupujte podle pokynů.

Pokud se pokusíte zkopírovat vzdálený ladící program (msvsmon.exe) ke vzdálenému počítači a spusťte ho, mějte na paměti, která **Průvodce konfigurací vzdáleného ladicího programu** (**rdbgwiz.exe**) je nainstalována pouze v případě, že si stáhnout nástroje. Budete muset použít Průvodce pro konfiguraci později, zejména v případě, že chcete, aby vzdálený ladicí program ke spuštění jako služba. Další informace najdete v tématu [(volitelné) konfigurovat vzdálený ladicí program jako službu](../../debugger/remote-debugging.md#bkmk_configureService).
