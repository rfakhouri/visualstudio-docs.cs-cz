---
title: Rámce zásobníku | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- stack frames, debugging
- debugging [Debugging SDK], stack frames
- stack frames
ms.assetid: b5e439d4-1e9d-4e13-9cad-bb8b136d4ca8
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: feb2bc9d87486b6f83cf4b19ecec24c8c03edee5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31127996"
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