---
title: Graf aktivity GPU | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.cv.cpu.graph.gpu
ms.assetid: d7c769af-95fb-49a3-b5ab-deafecee46fa
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ed2b2d86300106f432e1202c9061676ed3aacc0b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="gpu-activity-graph"></a>Graf aktivity GPU
Graf aktivity GPU v Concurrency Visualizer zobrazí danou úroveň aktivity rozhraní DirectX v systému, jako je počet modulů DirectX, které se používají v čase.  Graf nezobrazí, které konkrétní moduly byly použity.  Modul považován za používá, pokud se zpracovává všechny pracovní GPU.  
  
## <a name="gpu-activity-graph-colors"></a>Barvy graf aktivity GPU  
 Zelená značí spotřeby modulů rozhraní DirectX v aktuálním procesu.  
  
 Světle šedé označuje spotřeby modulů DirectX jinými procesy v systému. Ke snížení spotřeby modulů DirectX jinými procesy, snižte počet dalších procesů spuštěných v systému.  
  
 Prázdné označuje dostupnost modulů nepoužívá rozhraní DirectX v systému. Tyto moduly jsou k dispozici pro váš proces, pokud zjistíte většího počtu možností je zneužít. Některé moduly lze použít pouze pro specifické druhy úloh.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení využití](../profiling/utilization-view.md)