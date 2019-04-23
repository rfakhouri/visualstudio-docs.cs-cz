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
ms.openlocfilehash: 22db75783734a695ded937d8e6b93431568acd5b
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59736980"
---
Na vzdáleném zařízení nebo serveru, na kterém chcete ladit na, spíše než počítač s Visual Studio stáhněte a nainstalujte správnou verzi nástrojů remote tools z odkazů v následující tabulce.

- Stáhněte si nejnovější nástroje pro vzdálenou pro vaši verzi sady Visual Studio. Nejnovější verze nástrojů remote tools je kompatibilní s předchozími verzemi sady Visual Studio, ale dřívější verze nástrojů remote tools nejsou kompatibilní s novějšími verzemi sady Visual Studio.
- Stáhněte nástroje remote tools se stejnou architekturu jako počítač už je nainstalujete na. Pokud chcete ladit 32bitovou aplikaci na vzdáleném počítači s 64bitovým operačním systémem, například nainstalujte nástroje pro vzdálenou 64-bit.

::: moniker range=">=vs-2019"

|Version|Odkaz|Poznámky|
|-|-|-|
|Visual Studio 2019|[Vzdálené nástroje](https://visualstudio.microsoft.com/downloads/?q=remote+tools#remote-tools-for-visual-studio-2019)|Kompatibilní se všemi verzemi Visual Studio 2019. Stáhněte si verzi odpovídající operační systém zařízení (x 86, x64 nebo ARM64). V systému Windows Server, naleznete v tématu [odblokovat stahování souborů](../../debugger/remote-debugging-unblock-file-download.md) stažení nástroje pro vzdálenou pomoc.|
|Visual Studio 2017|[Vzdálené nástroje](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202017)|Kompatibilní se všemi verzemi sady Visual Studio 2017. Stáhněte si verzi odpovídající operační systém zařízení (x 86, x64 nebo ARM64). V systému Windows Server, naleznete v tématu [odblokovat stahování souborů](../../debugger/remote-debugging-unblock-file-download.md) stažení nástroje pro vzdálenou pomoc.|
|Visual Studio 2015|[Vzdálené nástroje](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202015)|Nástroje Remote tools for Visual Studio 2015 jsou k dispozici My.VisualStudio.com. Pokud se zobrazí výzva, připojte se k bezplatné [Visual Studio Dev Essentials](https://visualstudio.microsoft.com/dev-essentials/) programu, nebo se přihlaste pomocí ID předplatného sady Visual Studio. V systému Windows Server, naleznete v tématu [odblokovat stahování souborů](../../debugger/remote-debugging-unblock-file-download.md) stažení nástroje pro vzdálenou pomoc.|
|Visual Studio 2013|[Vzdálené nástroje](/previous-versions/visualstudio/visual-studio-2013/bt727f1t(v=vs.120)#installing-the-remote-tools)|Stáhněte si stránku v dokumentaci k sadě Visual Studio 2013|
|Visual Studio 2012|[Vzdálené nástroje](/previous-versions/visualstudio/visual-studio-2012/bt727f1t(v=vs.110)#installing-the-remote-tools)|Stáhněte si stránku v dokumentaci k sadě Visual Studio 2012|

::: moniker-end

::: moniker range="vs-2017"

|Version|Odkaz|Poznámky|
|-|-|-|
|Visual Studio 2017|[Vzdálené nástroje](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202017)|Kompatibilní se všemi verzemi sady Visual Studio 2017. Stáhněte si verzi odpovídající operační systém zařízení (x 86, x64 nebo ARM64). V systému Windows Server, naleznete v tématu [odblokovat stahování souborů](../../debugger/remote-debugging-unblock-file-download.md) stažení nástroje pro vzdálenou pomoc. Překopírujte nejnovější verzi nástrojů remote tools, otevřete [Visual Studio 2019 doc](../../debugger/remote-debugging.md?view=vs-2019).|
|Visual Studio 2015|[Vzdálené nástroje](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202015)|Nástroje Remote tools for Visual Studio 2015 jsou k dispozici My.VisualStudio.com. Pokud se zobrazí výzva, připojte se k bezplatné [Visual Studio Dev Essentials](https://visualstudio.microsoft.com/dev-essentials/) programu, nebo se přihlaste pomocí ID předplatného sady Visual Studio. V systému Windows Server, naleznete v tématu [odblokovat stahování souborů](../../debugger/remote-debugging-unblock-file-download.md) stažení nástroje pro vzdálenou pomoc.|
|Visual Studio 2013|[Vzdálené nástroje](/previous-versions/visualstudio/visual-studio-2013/bt727f1t(v=vs.120)#installing-the-remote-tools)|Stáhněte si stránku v dokumentaci k sadě Visual Studio 2013|
|Visual Studio 2012|[Vzdálené nástroje](/previous-versions/visualstudio/visual-studio-2012/bt727f1t(v=vs.110)#installing-the-remote-tools)|Stáhněte si stránku v dokumentaci k sadě Visual Studio 2012|

::: moniker-end

Můžete spustit vzdálený ladicí program tak, že zkopírujete *msvsmon.exe* do vzdáleného počítače, nikoli instalace vzdálených nástrojů. Ale Průvodce konfigurací vzdáleného ladicího programu (*rdbgwiz.exe*) je k dispozici pouze při instalaci nástrojů remote tools. Budete muset použít Průvodce pro konfiguraci, pokud chcete spustit vzdálený ladicí program jako službu. Další informace najdete v tématu [(volitelné) konfigurovat vzdálený ladicí program jako službu](../../debugger/remote-debugging.md#bkmk_configureService).

>[!NOTE]
>- Chcete-li ladit aplikace pro Windows 10 na zařízeních ARM, použijte ARM64, což je k dispozici v nejnovější verzi nástrojů remote Tools.
>- Chcete-li ladit aplikace pro Windows 10 na zařízení s Windows RT, použijte ARM, která je k dispozici pouze ve Visual Studiu 2015 stažení nástrojů remote tools.
