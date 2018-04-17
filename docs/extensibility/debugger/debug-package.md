---
title: Ladění balíček | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], packages
ms.assetid: 99947fd4-fb87-4c69-b26c-65634e17d285
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6ca438b7ed8c9b6a4b84693f975144040f998f01
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="debug-package"></a>Ladění balíčku
Balíček ladění běží v prostředí sady Visual Studio a zpracovává všechny uživatelské rozhraní. Ho využívá ladění v rozhraní sady Visual Studio a komunikuje s správce ladicí relace (SDM).  
  
 Rozdělení událostí odeslaných prostřednictvím SDM přepínače ladicí program z režimu spuštění do režimu pozastavení a změna výběru programu, kde došlo k přerušení. Balíček ladění sleduje informace odeslané události rámce zásobníku a přístup z více vláken.  
  
 Ladění balíček nemá žádný jazyk nebo běhové prostředí závislosti. Není nutné implementovat nebo upravit balíček ladění.  
  
 Ladění balíčku je implementováno modulem vsdebug.dll.  
  
## <a name="see-also"></a>Viz také  
 [Správce ladicí relace](../../extensibility/debugger/session-debug-manager.md)   
 [Rámce zásobníku](../../extensibility/debugger/stack-frames.md)   
 [Vláken](../../extensibility/debugger/threads.md)   
 [Komponenty ladicího programu](../../extensibility/debugger/debugger-components.md)