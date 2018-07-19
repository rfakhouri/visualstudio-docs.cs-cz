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
ms.openlocfilehash: 987193cb7f78947087c6d387e16261d83a20e7c2
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/11/2018
ms.locfileid: "38809237"
---
1.  Na zařízení nebo server počítač, který chcete ladit (nikoli na počítači sadu Visual Studio) získáte správná verze nástrojů remote tools.

    |Version|Odkaz|Poznámky|
    |-|-|-|
    |Visual Studio 2017 (nejnovější verze)|[Vzdálené nástroje](https://visualstudio.microsoft.com/downloads/?q=remote+tools#remote-tools-for-visual-studio-2017)|Kdykoli stáhněte verzi, která odpovídá operačního systému zařízení (x 86, x64 nebo ARM64). V systému Windows Server, naleznete v tématu [odblokovat stahování souborů](../../debugger/remote-debugging.md#unblock_msvsmon) nápovědu ke stažení nástroje remote tools.|
    |Visual Studio 2017 (starší)|[Vzdálené nástroje](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202017)|Remote tools pro dřívější verze sady Visual Studio 2017 jsou k dispozici My.VisualStudio.com. Pokud se zobrazí výzva, spojení skupině Visual Studio Dev Essentials zdarma, nebo se přihlaste pomocí předplatného sady Visual Studio ID. V systému Windows Server, naleznete v tématu [odblokovat stahování souborů](../../debugger/remote-debugging.md#unblock_msvsmon) nápovědu ke stažení nástroje remote tools.|
    |Visual Studio 2015 (starší)|[Vzdálené nástroje](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202015)|Pokud se zobrazí výzva, spojení skupině Visual Studio Dev Essentials zdarma, nebo se přihlaste pomocí předplatného sady Visual Studio ID. V systému Windows Server, naleznete v tématu [odblokovat stahování souborů](../../debugger/remote-debugging.md#unblock_msvsmon) nápovědu ke stažení nástroje remote tools.|
    |Visual Studio 2013|[Vzdálené nástroje](https://msdn.microsoft.com/library/bt727f1t(v=vs.120).aspx#BKMK_Installing_the_Remote_Tools)|Stáhněte si stránku v dokumentaci k sadě Visual Studio 2013|
    |Visual Studio 2012|[Vzdálené nástroje](https://msdn.microsoft.com/library/bt727f1t(v=vs.110).aspx#BKMK_Installing_the_Remote_Tools)|Stáhněte si stránku v dokumentaci k sadě Visual Studio 2012|

2.  Na stránce pro stahování zvolte verzi nástrojů, který odpovídá operačnímu systému (x86, x64, ARM a ARM64) a stáhněte si nástroje remote tools.

    > [!IMPORTANT]
    >  Doporučujeme že nainstalovat nejnovější verzi nástrojů remote tools, která odpovídá verzi sady Visual Studio. Verze se nedoporučuje. Kromě toho musíte nainstalovat nástroje remote tools, které mají stejnou architekturu jako operační systém, na kterém chcete nainstalovat. Jinými slovy Pokud chcete ladit 32bitovou aplikaci na vzdáleném počítači s 64bitovým operačním systémem, musíte nainstalovat 64bitová verze produktu remote tools na vzdáleném počítači.
    >
    >  Pro ladění ve Windows 10 na zařízeních ARM, klikněte na tlačítko ARM64 stáhnout k dispozici v nejnovější verzi nástrojů remote Tools.  Pro zařízení s Windows RT zvolte verzi ARM, která je k dispozici soubor ke stažení Visual Studio 2015 RTW.

3.  Po dokončení stahování spustitelného souboru, přejděte k další části a postupujte podle pokynů.

Pokud se pokusíte zkopírovat vzdálený ladící program (msvsmon.exe) ke vzdálenému počítači a spusťte ho, mějte na paměti, která **Průvodce konfigurací vzdáleného ladicího programu** (**rdbgwiz.exe**) je nainstalována pouze v případě, že si stáhnout nástroje. Budete muset použít Průvodce pro konfiguraci později, zejména v případě, že chcete, aby vzdálený ladicí program ke spuštění jako služba. Další informace najdete v tématu [(volitelné) konfigurovat vzdálený ladicí program jako službu](../../debugger/remote-debugging.md#bkmk_configureService).
