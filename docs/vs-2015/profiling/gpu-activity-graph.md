---
title: Graf aktivity GPU | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.cpu.graph.gpu
ms.assetid: d7c769af-95fb-49a3-b5ab-deafecee46fa
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: f4546c3be480349f3e2cb36f483fa8711bc2ac49
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62434212"
---
# <a name="gpu-activity-graph"></a>Graf aktivity GPU
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Graf aktivity GPU ve vizualizátoru souběžnosti zobrazí danou úroveň aktivity DirectX v systému, jak se měří podle počtu DirectX moduly, které se používají v čase.  Grafu nezobrazí, které konkrétní moduly byly použity.  Modul se považuje za používán pokud zpracovává veškerou práci GPU.  
  
## <a name="gpu-activity-graph-colors"></a>Barvy graf aktivity GPU  
 Zelená značí konzumace aktuální proces modulů rozhraní DirectX.  
  
 Světle šedá označuje využití strojů rozhraní DirectX s jinými procesy v systému. Ke snížení spotřeby modulů DirectX s jinými procesy, snižte počet dalších procesů spuštěných v systému.  
  
 Prázdné označuje dostupnosti nepoužité DirectX stroje v systému. Tyto moduly jsou k dispozici pro váš proces, pokud nemůžete najít další příležitosti k jejich zneužití. Některé moduly jde použít jenom pro určité druhy úloh.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení využití](../profiling/utilization-view.md)
