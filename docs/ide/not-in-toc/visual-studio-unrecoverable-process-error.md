---
title: Chyba neopravitelné procesu Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 02/23/2017
ms.topic: conceptual
helpviewer_keywords:
- editor
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-general
ms.workload:
- multiple
ms.openlocfilehash: 37cb88b9a07728c2e8c263551e9f0aa2e750ec12
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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
