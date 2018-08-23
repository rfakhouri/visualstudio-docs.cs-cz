---
title: Ladění balíčku | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], packages
ms.assetid: 99947fd4-fb87-4c69-b26c-65634e17d285
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e4bc7ce9bbef75badb1003f18bf65c5248f279bb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667988"
---
# <a name="debug-package"></a>Ladění balíčku
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [ladění balíčku](https://docs.microsoft.com/visualstudio/extensibility/debugger/debug-package).  
  
Ladění balíčku běží v prostředí sady Visual Studio a zpracovává všechny uživatelské rozhraní. Využívá rozhraní pro ladění sady Visual Studio a komunikuje se službou Správce ladění relace (SDM).  
  
 Konec události odesílat prostřednictvím SDM přepnout režim přerušení a změnit zaměření na aplikace, kde došlo k přerušení ladicího programu v režimu spuštění. Ladění balíčku sleduje rámec zásobníku a vlákna z informace odeslané události.  
  
 Ladění balíčku nemá žádný jazyk nebo závislosti běhového prostředí. Není nutné k implementaci nebo upravit balíček ladění.  
  
 Balíček ladění je implementováno vsdebug.dll.  
  
## <a name="see-also"></a>Viz také  
 [Správce ladění relace](../../extensibility/debugger/session-debug-manager.md)   
 [Rámce zásobníku](../../extensibility/debugger/stack-frames.md)   
 [Vlákna](../../extensibility/debugger/threads.md)   
 [Komponenty ladicího programu](../../extensibility/debugger/debugger-components.md)

