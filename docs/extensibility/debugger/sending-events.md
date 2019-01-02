---
title: Odesílání událostí | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], sending events
ms.assetid: 064231e7-59b5-4437-8240-a23c0a7ec2a9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8f4ee7ab58f95ede913536102573a8c6061f860a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53959982"
---
# <a name="send-events"></a>Odesílání událostí
Mechanismus pro komunikaci mezi ladicí program a ladicí stroj (DE) je model událostí založené na modelu DCOM. Události jsou odeslány jako objekty modelu COM a každou událost obsahuje parametry, které určují:  
  
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