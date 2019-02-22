---
title: Aktivita GPU (Tento proces) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.gpuexecution
- vs.cv.threads.timeline.gpuactivity
ms.assetid: 0956edbf-9bcd-4afe-9287-fda628648ca0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 68e85fc44977a3d9756965de12e25d13d62dbb89
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56625137"
---
# <a name="gpu-activity-this-process"></a>Aktivita GPU (tento proces)
**Aktivita GPU (Tento proces)** segmenty v zobrazení vláken ve vizualizátoru souběžnosti představují časy, kdy GPU zpracovává požadavky jménem aktuální proces. Tyto požadavky se odesílají do GPU jako pakety paměti (DMA) přístup. Délka segment, který představuje čas, GPU zpracování paketů DMA jménem aktuální proces.

 Když vyberete na segment aktivity GPU, sestava **aktuální** karta zobrazuje informace o paketu DMA, který byl zpracován. Tyto informace zahrnují množství času, které paket čekání ve frontě hardwaru, který je spojen s modul rozhraní DirectX, proces, který odešle paket a čas, který je potřebný ke zpracování paketu. Procesu než aktuální proces může fyzicky odeslání paketů DMA do GPU. Vizualizátor souběžnosti lze rozpoznat, kdy se jiný proces odeslání práce GPU jménem aktuální proces.