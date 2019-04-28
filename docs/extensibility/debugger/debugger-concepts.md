---
title: Koncepty ladicího programu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK]
ms.assetid: 2d371d38-f1a0-4a9a-8ea3-100e8c0149b7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7e3a9043215c5242246e54dc3e1eb2e85cd26c91
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62925890"
---
# <a name="debugger-concepts"></a>Koncepty ladicího programu
K sestavení v balíčku ladění sady Visual Studio, musíte se seznámit s architektury koncepty použité při navrhování balíček.

## <a name="in-this-section"></a>V tomto oddílu
 [Ladicí relace](../../extensibility/debugger/debug-session.md) vysvětluje roli relaci ladění architektury.

 [Servery](../../extensibility/debugger/servers-visual-studio-sdk.md) definuje, jaký server je z hlediska ladění architekturu, v abstraktní i fyzické podmínky.

 [Dodavatelé portů](../../extensibility/debugger/port-suppliers.md) definuje, jaké dodavatele portu je z hlediska architektury ladění.

 [Porty](../../extensibility/debugger/ports.md) definuje, jaké port je z hlediska architektury ladění.

 [Procesy](../../extensibility/debugger/processes.md) definuje, jaký proces je z hlediska architektury ladění.

 [Program uzly](../../extensibility/debugger/program-nodes.md) definuje uzel programu z hlediska architektury, včetně toho, jak můžete identifikovat samostatně a proces je spuštěn v ladění.

 [Programy](../../extensibility/debugger/programs.md) definuje program z hlediska architektury ladění.

 [Vlákna](../../extensibility/debugger/threads.md) definuje vlastnosti vlákna z hlediska architektury ladění.

 [Rámců zásobníku](../../extensibility/debugger/stack-frames.md) definuje rámec zásobníku z hlediska architektury ladění. Rámec zásobníku je abstrakcí zásobníku, která poskytuje kontext spuštění vlákna.

 [Moduly](../../extensibility/debugger/modules.md) definuje modulu, co se týče ladění architektury, jako fyzický kontejneru kódu, jako je spustitelný soubor nebo knihovny DLL.

 [Zarážky](../../extensibility/debugger/breakpoints-visual-studio-sdk.md) definuje tři typy zarážky – čekající mez a chyba – jde o ladění v architektuře.

## <a name="related-sections"></a>Související oddíly
 [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md) vysvětluje, jak funguje ladicího stroje (DE) současně v kontextech hodnocení kódu, dokumentace a výraz. Popisuje všech třech kontextech, umístění, pozice nebo vyhodnocení relevantní k němu.

 [Komponenty ladicího programu](../../extensibility/debugger/debugger-components.md) obsahuje přehled komponent ladění Visual Studio, mezi které patří ladicího stroje (DE), Chyba při vyhodnocování výrazu (EE) a obslužné rutiny symbolů (SH).

 [Ladění úlohy](../../extensibility/debugger/debugging-tasks.md) obsahuje odkazy na různé úlohy ladění, například spuštění programu a vyhodnocení výrazů.