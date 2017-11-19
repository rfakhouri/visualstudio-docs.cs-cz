---
title: Moduly | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- modules
- debugging [Debugging SDK], modules
ms.assetid: c4cf2809-dbdb-4e75-9273-b3d3d77b67d0
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c363ea8809449118782597e68f60637f296af89f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="modules"></a>Moduly
Z hlediska architektuře ladicího programu **modulu**:  
  
-   Je fyzický kontejner kódu, třeba spustitelný soubor nebo knihovny DLL.  
  
-   Můžete znovu načíst jeho symboly a popisují sám sebe. Modul jsou zobrazovány v okně moduly rozhraní IDE.  
  
-   Je reprezentována [IDebugModule2](../../extensibility/debugger/reference/idebugmodule2.md) rozhraní, modul ladění k popisu modul vytvoří.  
  
## <a name="see-also"></a>Viz také  
 [Koncepty ladicí program](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugModule2](../../extensibility/debugger/reference/idebugmodule2.md)