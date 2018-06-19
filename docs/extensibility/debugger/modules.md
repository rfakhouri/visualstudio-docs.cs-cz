---
title: Moduly | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- modules
- debugging [Debugging SDK], modules
ms.assetid: c4cf2809-dbdb-4e75-9273-b3d3d77b67d0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f587e015263336436588d14edeeb5c6935872950
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31098141"
---
# <a name="modules"></a>Moduly
Z hlediska architektuře ladicího programu **modulu**:  
  
-   Je fyzický kontejner kódu, třeba spustitelný soubor nebo knihovny DLL.  
  
-   Můžete znovu načíst jeho symboly a popisují sám sebe. Modul jsou zobrazovány v okně moduly rozhraní IDE.  
  
-   Je reprezentována [IDebugModule2](../../extensibility/debugger/reference/idebugmodule2.md) rozhraní, modul ladění k popisu modul vytvoří.  
  
## <a name="see-also"></a>Viz také  
 [Koncepty ladicí program](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugModule2](../../extensibility/debugger/reference/idebugmodule2.md)