---
title: Proces došlo k neodstranitelné chybě
ms.date: 06/22/2018
ms.topic: troubleshooting
helpviewer_keywords:
- unrecoverable error
- error, process
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.workload:
- multiple
ms.openlocfilehash: ebd530b9db139cb232f735f7d6401199cab2f6fd
ms.sourcegitcommit: e6b13898cfbd89449f786c2e8f3e3e7377afcf25
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/22/2018
ms.locfileid: "36325699"
---
# Chyba neopravitelné procesu Visual Studio

Visual Studio 2017 používá několik out-of-proc procesů ke spuštění úlohy na pozadí požadované, jako je například testování částí za provozu, code analyzátorů a další. Tyto procesy jsou spuštěny out-of-proc umožnit výhody výkonu sady Visual Studio, například povolení rychleji reagovat při spuštění, úlohách náročných sady Visual Studio. Navíc vzhledem k sadě Visual Studio je 32bitový proces, spuštění procesů out-of-proc dává náročné práce paměti větší paměťový prostor, ve kterém se bude pracovat.

Pokud *ServiceHub.RoslynCodeAnalysisService.exe* nebo *ServiceHub.RoslynCodeAnalysisService32.exe* ukončení procesu z nějakého důvodu, se zobrazí automaticky otevírané okno informační panel s následující zprávou:

**"Bohužel procesu, sada Visual Studio má došlo k neodstranitelné chybě. Doporučujeme, abyste ukládání práce a pak zavřením a spustit sadu Visual Studio."**

Pokud se zobrazí tato zpráva, měli uložit práci a pak zavřete a restartujte Visual Studio.

## Seznam procesů

Následuje seznam out-of-proc procesy používané modulem Visual Studio. Tento seznam je včetně procesy, které budou spuštěny v určité pracovní postupy nebo scénářů, a proto ve většině případů všechny neběží ve stejnou dobu.

- Microsoft.Alm.Shared.Remoting.RemoteContainer.dll
- Microsoft.CodeAnalysis.LiveUnitTesting.EntryPoint
- PerfWatson2.exe
- ServiceHub.Host.Node.x86.exe
- ServiceHub.IdentityHost.exe
- ServiceHub.VSDetouredHost.exe
- ServiceHub.SettingsHost.exe
- ServiceHub.Host.CLR.x86.exe
- ServiceHub.RoslynCodeAnalysisService32.exe
- ServiceHub.RoslynCodeAnalysisService.exe
- WindowsAzureGuestAgent.exe
- WindowsAzureTelemetryService.exe
- WaAppAgent.exe

Pokud některé z těchto procesů neočekávaně ukončí, některé funkce v sadě Visual Studio přestane fungovat. U některých procesů může být zanedbatelný ztráty funkčnosti. Ostatní uživatelé má vliv stability sady Visual Studio a zobrazí se chybová zpráva.