---
title: Odesílání událostí | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], sending events
ms.assetid: 064231e7-59b5-4437-8240-a23c0a7ec2a9
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: cd282dd38d322a5b7d9821406d30a303fabb02bb
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56685063"
---
# <a name="send-events"></a>Odesílání událostí
Mechanismus pro komunikaci mezi ladicí program a ladicí stroj (DE) je model událostí založené na modelu DCOM. Události jsou odeslány jako objekty modelu COM a každou událost obsahuje parametry, které určují:

- DE, která volá událost.

- Popis co se stalo.

- Proces, program a informace o podprocesu, který identifikuje kontextu, kde k události došlo. Události odeslané z Zavedenými neodešle procesu.

- Typ události, která určuje, zda je událost synchronní nebo asynchronní.

  Všechny výjimky ladění jsou odeslány pomocí metody [IDebugEventCallback2::Event](../../extensibility/debugger/reference/idebugeventcallback2-event.md).

## <a name="in-this-section"></a>V tomto oddílu
 [Zdroje událostí](../../extensibility/debugger/event-sources-visual-studio-sdk.md) vysvětluje dva zdroje událostí: ladicí stroj (DE) a relace ladění správci.

 [Podporované typy událostí](../../extensibility/debugger/supported-event-types.md) popisuje událostí aktuálně podporované typy: asynchronní a synchronní.

 [Popisy událostí](../../extensibility/debugger/event-descriptions.md) definuje události a důvody pro jejich použití.

## <a name="related-sections"></a>Související oddíly
 [Vytvoření vlastního ladicího stroje](../../extensibility/debugger/creating-a-custom-debug-engine.md) popisuje, jak se Zavedenými pracuje s překladač nebo operačního systému k poskytování služeb ladění.