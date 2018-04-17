---
title: Odesílání událostí | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], sending events
ms.assetid: 064231e7-59b5-4437-8240-a23c0a7ec2a9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 9bbe7946b866cd751be1f0dac2dba5b8dea57e04
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="sending-events"></a>Odesílání událostí
Tento mechanismus pro komunikaci mezi ladicího programu a modul ladění (DE) je model událostí podle modelu DCOM. Události se odesílají jako objekty modelu COM a jednotlivých událostí obsahuje parametry, které zadejte následující informace:  
  
-   Německo, která volá událost.  
  
-   Popis co se stalo.  
  
-   Proces, program a vlákno informace, které identifikují kontextu kde k události došlo. Proces se neposílají odeslaný Zavedenými události.  
  
-   Typ události, který určuje, zda je událost synchronní nebo asynchronní.  
  
 Všechny události ladění se posílají pomocí metody [IDebugEventCallback2::Event](../../extensibility/debugger/reference/idebugeventcallback2-event.md).  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Zdroje událostí](../../extensibility/debugger/event-sources-visual-studio-sdk.md)  
 Popisuje dva zdroje událostí: ladění modulu (DE) a relace ladění manager (SDM).  
  
 [Podporované typy událostí](../../extensibility/debugger/supported-event-types.md)  
 Popisuje typy aktuálně podporované událostí: asynchronní a synchronní.  
  
 [Popisy událostí](../../extensibility/debugger/event-descriptions.md)  
 Definuje události a důvody pro jejich použití.  
  
## <a name="related-sections"></a>Související oddíly  
 [Vytvoření vlastního ladicího stroje](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
 Popisuje, jak funguje Zavedenými s překladač nebo operačního systému k poskytování ladění služeb.