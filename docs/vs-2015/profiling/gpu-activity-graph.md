---
title: Graf aktivity GPU | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.cv.cpu.graph.gpu
ms.assetid: d7c769af-95fb-49a3-b5ab-deafecee46fa
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d5a0ef828b221219c3abae0e46ec40d21b6b045c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42680753"
---
# <a name="gpu-activity-graph"></a>Graf aktivity GPU
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [graf aktivity GPU](https://docs.microsoft.com/visualstudio/profiling/gpu-activity-graph).  
  
Graf aktivity GPU ve vizualizátoru souběžnosti zobrazí danou úroveň aktivity DirectX v systému, jak se měří podle počtu DirectX moduly, které se používají v čase.  Grafu nezobrazí, které konkrétní moduly byly použity.  Modul se považuje za používán pokud zpracovává veškerou práci GPU.  
  
## <a name="gpu-activity-graph-colors"></a>Barvy graf aktivity GPU  
 Zelená značí konzumace aktuální proces modulů rozhraní DirectX.  
  
 Světle šedá označuje využití strojů rozhraní DirectX s jinými procesy v systému. Ke snížení spotřeby modulů DirectX s jinými procesy, snižte počet dalších procesů spuštěných v systému.  
  
 Prázdné označuje dostupnosti nepoužité DirectX stroje v systému. Tyto moduly jsou k dispozici pro váš proces, pokud nemůžete najít další příležitosti k jejich zneužití. Některé moduly jde použít jenom pro určité druhy úloh.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení využití](../profiling/utilization-view.md)



