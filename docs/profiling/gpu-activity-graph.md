---
title: Graf aktivity GPU | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.cpu.graph.gpu
ms.assetid: d7c769af-95fb-49a3-b5ab-deafecee46fa
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 03a25abc24e7b0312f0cd0dc7fd9eb66e5dd3fc6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="gpu-activity-graph"></a>Graf aktivity GPU
Graf aktivity GPU v Concurrency Visualizer zobrazí danou úroveň aktivity rozhraní DirectX v systému, jako je počet modulů DirectX, které se používají v čase.  Graf nezobrazí, které konkrétní moduly byly použity.  Modul považován za používá, pokud se zpracovává všechny pracovní GPU.  
  
## <a name="gpu-activity-graph-colors"></a>Barvy graf aktivity GPU  
 Zelená značí spotřeby modulů rozhraní DirectX v aktuálním procesu.  
  
 Světle šedé označuje spotřeby modulů DirectX jinými procesy v systému. Ke snížení spotřeby modulů DirectX jinými procesy, snižte počet dalších procesů spuštěných v systému.  
  
 Prázdné označuje dostupnost modulů nepoužívá rozhraní DirectX v systému. Tyto moduly jsou k dispozici pro váš proces, pokud zjistíte většího počtu možností je zneužít. Některé moduly lze použít pouze pro specifické druhy úloh.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení využití](../profiling/utilization-view.md)