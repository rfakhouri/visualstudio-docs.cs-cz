---
title: Ladění balíčku | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], packages
ms.assetid: 99947fd4-fb87-4c69-b26c-65634e17d285
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4eb843e63dbc4ff711b56ff457ca930dc9df0207
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55010178"
---
# <a name="debug-package"></a>Ladění balíčku
Ladění balíčku běží v prostředí sady Visual Studio a zpracovává všechny uživatelské rozhraní. Využívá rozhraní pro ladění sady Visual Studio a komunikuje se službou Správce ladění relace (SDM).  
  
 Konec události odesílat prostřednictvím SDM přepnout režim přerušení a změnit zaměření na aplikace, kde došlo k přerušení ladicího programu v režimu spuštění. Ladění balíčku sleduje rámec zásobníku a vlákna z informace odeslané události.  
  
 Ladění balíčku nemá žádný jazyk nebo závislosti běhového prostředí. Není nutné k implementaci nebo upravit balíček ladění.  
  
 Balíček ladění je implementováno *vsdebug.dll*.  
  
## <a name="see-also"></a>Viz také:  
 [Správce ladění relace](../../extensibility/debugger/session-debug-manager.md)   
 [Rámce zásobníku](../../extensibility/debugger/stack-frames.md)   
 [Vlákna](../../extensibility/debugger/threads.md)   
 [Komponenty ladicího programu](../../extensibility/debugger/debugger-components.md)