---
title: Odesílání událostí | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], sending events
ms.assetid: 064231e7-59b5-4437-8240-a23c0a7ec2a9
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 98247b894d2db628d508713875ba0ea7d0642729
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68204742"
---
# <a name="sending-events"></a>Odesílání událostí
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Mechanismus pro komunikaci mezi ladicí program a ladicí stroj (DE) je model událostí založené na modelu DCOM. Události jsou odeslány jako objekty modelu COM a každou událost obsahuje parametry, které zadejte následující informace:  
  
- DE, která volá událost.  
  
- Popis co se stalo.  
  
- Proces, program a informace o podprocesu, který identifikuje kontextu, kde k události došlo. Události odeslané z Zavedenými neodešle procesu.  
  
- Typ události, která určuje, zda je událost synchronní nebo asynchronní.  
  
  Všechny výjimky ladění jsou odeslány pomocí metody [IDebugEventCallback2::Event](../../extensibility/debugger/reference/idebugeventcallback2-event.md).  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Zdroje událostí](../../extensibility/debugger/event-sources-visual-studio-sdk.md)  
 Popisuje dva zdroje událostí: ladicí stroj (DE) a relace ladění správci.  
  
 [Podporované typy událostí](../../extensibility/debugger/supported-event-types.md)  
 Tento článek popisuje typy událostí aktuálně se podporují: asynchronní a synchronní.  
  
 [Popisy událostí](../../extensibility/debugger/event-descriptions.md)  
 Definuje události a důvody pro jejich použití.  
  
## <a name="related-sections"></a>Související oddíly  
 [Vytvoření vlastního ladicího stroje](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
 Popisuje, jak se Zavedenými pracuje s překladač nebo operačního systému k poskytování služeb ladění.
