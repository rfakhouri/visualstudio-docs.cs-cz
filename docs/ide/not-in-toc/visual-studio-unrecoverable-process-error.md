---
title: Chyba neopravitelné procesu Visual Studio
ms.date: 02/23/2017
ms.topic: troubleshooting
helpviewer_keywords:
- editor
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.workload:
- multiple
ms.openlocfilehash: 1db7f2729ded01eedda6fff6d18ca1b2ee3607b6
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# Chyba neopravitelné procesu Visual Studio

Visual Studio 2017 používá několik out-of-proc procesů ke spuštění úlohy na pozadí požadované, jako je například testování částí za provozu, code analyzátorů a další. Tyto procesy jsou spuštěny out-of-proc umožnit výhody výkonu sady Visual Studio, například povolení Visual Studio rychleji reagovat při spuštění náročná, dlouhotrvajících úloh. Navíc vzhledem k sadě Visual Studio je 32bitový proces, spuštění procesů out-of-proc dává náročné práce paměti větší paměťový prostor, ve kterém se bude pracovat.

V případě potřeby koncové procesy z nějakého důvodu některý z těchto se zobrazí automaticky otevírané okno informační panel s následující zprávou:

"Bohužel procesu, sada Visual Studio má došlo k neodstranitelné chybě. Doporučujeme, abyste ukládání práce a pak zavřením a spustit sadu Visual Studio."

Pokud se zobrazí tato zpráva, by měl okamžitě uložte si práci a pak zavřete a restartujte Visual Studio. Pokud to neuděláte, může dojít k chybě Visual Studio v každém okamžiku.

## Seznam procesů

Následuje seznam out-of-proc procesy používané modulem Visual Studio, který musí být spuštěn pro sadu Visual Studio správně fungovat.

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