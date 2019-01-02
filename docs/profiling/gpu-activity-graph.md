---
title: Graf aktivity GPU | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.cpu.graph.gpu
ms.assetid: d7c769af-95fb-49a3-b5ab-deafecee46fa
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c274bc5c98a856e5d2f921f2967d8ee474f06274
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53833310"
---
# <a name="gpu-activity-graph"></a>Graf aktivity GPU
Graf aktivity GPU ve vizualizátoru souběžnosti zobrazí danou úroveň aktivity DirectX v systému, jak se měří podle počtu DirectX moduly, které se používají v čase.  Grafu nezobrazí, které konkrétní moduly byly použity.  Modul se považuje za používán pokud zpracovává veškerou práci GPU.  
  
## <a name="gpu-activity-graph-colors"></a>Barvy graf aktivity GPU  
 Zelená značí konzumace aktuální proces modulů rozhraní DirectX.  
  
 Světle šedá označuje využití strojů rozhraní DirectX s jinými procesy v systému. Ke snížení spotřeby modulů DirectX s jinými procesy, snižte počet dalších procesů spuštěných v systému.  
  
 Prázdné označuje dostupnosti nepoužité DirectX stroje v systému. Tyto moduly jsou k dispozici pro váš proces, pokud nemůžete najít další příležitosti k jejich zneužití. Některé moduly jde použít jenom pro určité druhy úloh.  
  
## <a name="see-also"></a>Viz také:  
 [Zobrazení využití](../profiling/utilization-view.md)