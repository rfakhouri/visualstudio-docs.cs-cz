---
title: "Chyba neopravitelné procesu Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 02/23/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editor
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-general
ms.openlocfilehash: 6964c9e0e1202623d535724f6bc3faff018d948a
ms.sourcegitcommit: f36eb7f989efbdbed0d0a087afea8ffe27d8ca15
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/14/2017
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
- WindowsAzureGuestAgent.exe
- WindowsAzureTelemetryService.exe
- WaAppAgent.exe
