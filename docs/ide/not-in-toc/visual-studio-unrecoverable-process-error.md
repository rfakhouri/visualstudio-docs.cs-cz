---
title: "Chyba neopravitelné procesu Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 02/23/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords: editor
ms.assetid: 2263956f-3ae0-4bdc-9d3a-4991dfaf4ddb
caps.latest.revision: "29"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-general
ms.openlocfilehash: 8750d16a485de062e66041e66e28fa591e957efd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
