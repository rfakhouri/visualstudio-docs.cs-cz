---
title: Graf aktivity GPU | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.cpu.graph.gpu
ms.assetid: d7c769af-95fb-49a3-b5ab-deafecee46fa
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5734b9eb1b4307f7c32dcb8a170f7c6c571f46ca
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56617558"
---
# <a name="gpu-activity-graph"></a>Graf aktivity GPU
Graf aktivity GPU ve vizualizátoru souběžnosti zobrazí danou úroveň aktivity DirectX v systému, jak se měří podle počtu DirectX moduly, které se používají v čase.  Grafu nezobrazí, které konkrétní moduly byly použity.  Modul se považuje za používán pokud zpracovává veškerou práci GPU.

## <a name="gpu-activity-graph-colors"></a>Barvy graf aktivity GPU
 Zelená značí konzumace aktuální proces modulů rozhraní DirectX.

 Světle šedá označuje využití strojů rozhraní DirectX s jinými procesy v systému. Ke snížení spotřeby modulů DirectX s jinými procesy, snižte počet dalších procesů spuštěných v systému.

 Prázdné označuje dostupnosti nepoužité DirectX stroje v systému. Tyto moduly jsou k dispozici pro váš proces, pokud nemůžete najít další příležitosti k jejich zneužití. Některé moduly jde použít jenom pro určité druhy úloh.

## <a name="see-also"></a>Viz také:
- [Zobrazení využití](../profiling/utilization-view.md)