---
title: Ladění balíčku | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], packages
ms.assetid: 99947fd4-fb87-4c69-b26c-65634e17d285
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: dda8b1ac6eaa2cd5352d441600ae720c3aac321c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68181301"
---
# <a name="debug-package"></a>Ladění balíčku
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Ladění balíčku běží v prostředí sady Visual Studio a zpracovává všechny uživatelské rozhraní. Využívá rozhraní pro ladění sady Visual Studio a komunikuje se službou Správce ladění relace (SDM).  
  
 Konec události odesílat prostřednictvím SDM přepnout režim přerušení a změnit zaměření na aplikace, kde došlo k přerušení ladicího programu v režimu spuštění. Ladění balíčku sleduje rámec zásobníku a vlákna z informace odeslané události.  
  
 Ladění balíčku nemá žádný jazyk nebo závislosti běhového prostředí. Není nutné k implementaci nebo upravit balíček ladění.  
  
 Balíček ladění je implementováno vsdebug.dll.  
  
## <a name="see-also"></a>Viz také  
 [Správce ladění relace](../../extensibility/debugger/session-debug-manager.md)   
 [Rámce zásobníku](../../extensibility/debugger/stack-frames.md)   
 [Vlákna](../../extensibility/debugger/threads.md)   
 [Komponenty ladicího programu](../../extensibility/debugger/debugger-components.md)
