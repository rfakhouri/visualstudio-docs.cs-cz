---
title: "Rámce zásobníku | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- stack frames, debugging
- debugging [Debugging SDK], stack frames
- stack frames
ms.assetid: b5e439d4-1e9d-4e13-9cad-bb8b136d4ca8
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 110a68d737ac2f194c7a318c41d05801d69511c3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="stack-frames"></a>Rámce zásobníku
Z hlediska architektuře ladicího programu **rámce zásobníku**:  
  
-   Je abstrakcí zásobníku, která poskytuje kontext provádění vlákna. Vlákno vždy spouští v rámci funkce. Rámec zásobníku obsahuje místní proměnné funkce a argumenty do ní. Pokud chcete ladit pomocí sady Visual Studio, musí podporovat jazyk nebo prostředí laděné rámce zásobníku.  
  
-   Může i identifikovat a popisují sám a může vrátit související vlákno. Rámec zásobníku také vrátit kontext kód, který představuje aktuální ukazatel instrukce, a také související dokumentaci a kontexty vyhodnocení výrazu.  
  
-   Obsahuje vlastnosti, které popisují název, typ a hodnotu místní proměnné a argumenty, a které jsou uvedeny v různých windows ladění IDE.  
  
-   Je reprezentována [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md) rozhraní, obvykle vytvoří virtuální počítač v důsledku podproces nebo ladění modulu (DE).  
  
## <a name="see-also"></a>Viz také  
 [Kontexty ladicí program](../../extensibility/debugger/debugger-contexts.md)   
 [Koncepty ladicí program](../../extensibility/debugger/debugger-concepts.md)   
 [Ladění modulu](../../extensibility/debugger/debug-engine.md)   
 [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md)