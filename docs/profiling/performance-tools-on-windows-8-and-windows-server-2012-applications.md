---
title: Nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012 | Microsoft Docs
ms.custom: ''
ms.date: 06/19/2017
ms.technology:
- vs-ide-debug
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a3787b8741f78b0761b65a5e92fc24f55249767a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="performance-tools-on-windows-8-and-windows-server-2012-applications"></a>Nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012

Funkce Rozšířené zabezpečení od verze Windows 8 a Windows Server 2012 požadované významné změny v nástroje pro sledování výkonu sady Visual Studio způsob shromažďování dat na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. Toto téma popisuje změny pro spouštění na platformy Windows 8 a Windows Server 2012 nástroje pro sledování výkonu.

> [!NOTE]
> Nástroje pro sledování výkonu pro jiné podporované verze systému Windows (Windows 7, Windows Server 2008 R2) nezměnily.

## <a name="BKMK_Profiling_Windows_Store_apps_from_the_Visual_Studio_IDE"></a> Shromažďování dat pro aplikace UWP v prostředí Visual Studio IDE

Profil aplikace pro UPW, který je napsán v jazyce JavaScript a HTML 5 shromažďujete data instrumentace pro kód jazyka JavaScript. Pokud je profil aplikace pro UPW nebo součásti, která je napsán v jazyce Visual C++, Visual C# nebo Visual Basic, shromažďování dat vzorkování pro nativního a spravovaného kódu. Aplikace můžete profil místně nebo ve vzdáleném počítači.

Při vytváření profilů aplikací UWP nejsou podporovány tyto profilování funkce a možnosti:

- Profilace aplikací JavaScript pomocí metody vzorkování.
- Profilace spravovaná a nativní kód pomocí metody instrumentace.
- Profilace souběžného zpracování
- Profilace paměti .NET
- (TIP) profilace sledováním interakce vrstev
- Vzorkování možnosti, například nastavení událostí vzorkování a časování interval nebo shromažďování dat čítačů výkonu Další.
- Instrumentace možnosti, jako je shromažďování dat čítačů windows a výkonu, nebo zadáte další možnosti příkazového řádku.

Další informace o vytváření profilů aplikací UWP najdete v následujících článcích:

- [Spouštění aplikací pro UWP v místním počítači](../debugger/run-windows-store-apps-on-the-local-machine.md)
- [Spouštění aplikací pro UWP ve vzdáleném počítači](../debugger/run-windows-store-apps-on-a-remote-machine.md)
- [Nástroje pro profilaci](profiling-tools.md)
- [Paměť jazyka JavaScript](../profiling/javascript-memory.md)
- [Kód profil Visual C++, Visual C# a Visual Basic v aplikacích pro UPW v místním počítači](http://msdn.microsoft.com/en-us/2d0c939e-0bac-48c5-b727-46f6c6113060)
- [Kód profil Visual C++, Visual C# a Visual Basic v aplikacích pro UPW na vzdáleném zařízení](http://msdn.microsoft.com/en-us/b932a2be-11b0-40fd-b996-75c6b6a79d22)
- [Analýza dat výkonu pro kód jazyka Visual C++, Visual C# a Visual Basic v aplikacích pro UPW](http://msdn.microsoft.com/en-us/5de4a413-d924-425f-afc4-e1ecfb0fca18)

## <a name="BKMK_Profiling_apps_running_on_the_Windows_8_desktop_or_on_Windows_Server_2012_from_the_Visual_Studio_IDE"></a> Shromažďování dat na aplikace běžící na ploše systému Windows 8 nebo Windows Server 2012 z prostředí Visual Studio IDE

Profilace pomocí metody instrumentace nezměnil pro systém Windows 8.

(TIP) profilace sledováním interakce vrstev není k dispozici pomocí metody vzorkování.

## <a name="BKMK_Profiling_apps_running_on_the_Windows_8_desktop_or_on_Windows_Server_2012_by_using_sampling_from_the_Visual_Studio_IDE"></a> Shromažďování dat na aplikace běžící na ploše systému Windows 8 nebo Windows Server 2012 s použitím vzorkování v prostředí Visual Studio IDE

Při vytváření profilů aplikací klasické pracovní plochy Windows 8 nebo Windows Server 2012 aplikací pomocí metody vzorkování, nejsou podporovány tyto profilování funkce a možnosti:

- Profilace sledováním interakce vrstev (TIP). Shromažďování dat TIP je podporována pomocí instrumentace.

- Možnosti vzorkování například nastavit událostí vzorkování a vypršení časového intervalu nebo shromažďování dat čítačů výkonu Další.

## <a name="BKMK_Profiling_from_the_command_line"></a> Profilace z příkazového řádku

Shromažďovat data profilování na zařízeních s Windows 8 a Windows Server 2012, včetně zařízení, které nemají instalace sady Visual Studio pomocí dvou nástrojů příkazového řádku:

|Název nástroje|Popis|
|---------------|-----------------|
|[VSPerf](../profiling/vsperf.md)|Shromažďuje data profilování z aplikace UWP a shromažďuje data profilování ukázka od aplikací klasické pracovní plochy Windows 8 a Windows Server 2012 aplikací...|
|[VSPerfCmd](../profiling/vsperfcmd.md)|Shromažďuje instrumentace, souběžnosti a data z aplikací, které jsou spuštěny na ploše sadě Windows 8 nebo Windows Server 2012 profilace sledováním interakce vrstev. Shromažďuje všechny typy data profilování z předchozích verzí systému Windows.|

Oba nástroje jsou nainstalované s Visual Studio pro použití v místním počítači.

Do profilu aplikace na zařízeních, které nemají v sadě Visual Studio nainstalována, proveďte jednu z následujících:

- Stažení nástroje jako součást nástrojů pro vzdálenou pro sadu Visual Studio pomocí [webu MSDN](http://go.microsoft.com/fwlink/?LinkID=219549).

- Kopírování a spusťte instalační program nástroje samostatného profileru z vašeho počítače Visual Studio. Instalační programy jsou v *VSInstallDir %* **\Team Tools\Performance Tools\Setups** složky. Vyberte instalační program pro operační systém (x86/x64) vzdáleného počítače.

> [!NOTE]
> Shromažďování dat profilaci TIP, musí instalace samostatného profileru z počítače Visual Studio na vzdáleném počítači.

Tyto profilování funkce a možnosti nejsou podporovány, pokud profilace aplikací Windows 8 a Windows Server 2012 z příkazového řádku:

- Shromažďování dat ze systému Windows 8 a Windows Server 2012 webové aplikace pomocí vzorkování režimu s [VSPerfASPNetCmd](../profiling/vsperfaspnetcmd.md).

- Shromažďování dat vzorkování pomocí VsPerfCmd.exe.

- Možnosti vzorkování například nastavit událostí vzorkování a vypršení časového intervalu nebo shromažďování dat čítačů výkonu Další.

## <a name="BKMK_Collecting_tier_interaction__TIP__data"></a> Shromažďování dat interakce (TIP) vrstev

Profilace interakce vrstvy poskytuje další informace o dobu provádění funkcí víceúrovňových aplikací, které komunikují s databází prostřednictvím služeb ADO.NET. Data jsou shromažďována jenom pro funkce synchronní volání.

**Edice Visual Studio**

Pomocí libovolná edice sady Visual Studio se můžou shromažďovat data profilace sledováním interakce vrstev. Data profilace sledováním interakce vrstev však lze zobrazit pouze ve Visual Studio Enterprise.

**Windows 8 a Windows Server 2012**

1. Shromažďování dat interakce vrstev z aplikací, které jsou spuštěny na ploše systému Windows 8 nebo Windows Server 2012, musíte použít metodu instrumentace.

2. Nelze shromažďování dat interakce vrstev pro aplikace UWP.

3. Můžete zahrnout dat interakce vrstev všechny metody profilování jiné podporované verze systému Windows.

**Průvodce výkonu a prohlížeč výkonu**

Možnost kolekce dat interakce vrstvy je nutné přidat na spuštění profilování z Průzkumníka výkonu. Musíte taky přidat projekt, spustitelný soubor nebo webu do cílového uzlu prohlížeč výkonu. V tématu [shromažďování dat interakce vrstev](../profiling/collecting-tier-interaction-data.md).

**Shromažďování dat TIP ve vzdáleném počítači**

Shromažďování dat interakce vrstev ve vzdáleném počítači, je nutné zkopírovat **vs_profiler_***\<platformy >***_***\<jazyk >***.exe** souboru z *%VSInstallDir%***\Team nástroje Tools\Setups** složky sady Visual Studio počítač ke vzdálenému počítači a nainstalujte ji. Nelze použít v nástroji pro profilaci [vzdálené ladění](../debugger/remote-debugging.md) stažení balíčku.

Můžete použít [VSPerfCmd](../profiling/vsperfcmd.md) nebo [VSPerfASPNetCmd](../profiling/vsperfaspnetcmd.md) shromažďovat data profilování.

**TIP pro sestavy**

Dat interakce vrstev lze zobrazit pouze ve Visual Studio Enterprise. Sledováním interakce vrstev založená na souborech sestavy prostřednictvím [vsperfreport –](../profiling/vsperfreport.md) nejsou k dispozici.

## <a name="see-also"></a>Viz také

[Prohlížeč výkonu](../profiling/performance-explorer.md)
[konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)
[profilace z příkazového řádku](../profiling/using-the-profiling-tools-from-the-command-line.md)