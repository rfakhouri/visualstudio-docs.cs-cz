---
title: "Ladění balíček | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], packages
ms.assetid: 99947fd4-fb87-4c69-b26c-65634e17d285
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: eccd258476f82871732ef7b16f0282d2f945b9ee
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
 [Ladicí program komponenty](../../extensibility/debugger/debugger-components.md)