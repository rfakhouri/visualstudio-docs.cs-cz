---
title: Rámců zásobníku | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- stack frames, debugging
- debugging [Debugging SDK], stack frames
- stack frames
ms.assetid: b5e439d4-1e9d-4e13-9cad-bb8b136d4ca8
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 54a9af8134ff729fe229b3ce551a4f30f104c09b
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54765410"
---
# <a name="stack-frames"></a>Bloky zásobníku
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Z hlediska architektury ladicího programu **rámec zásobníku**:  
  
-   Je abstrakcí zásobníku, která poskytuje kontext spuštění vlákna. Vlákno vždy provede v rámci funkce. Rámec zásobníku obsahuje místní proměnné, funkce a argumenty do něj. Pokud chcete ladit pomocí sady Visual Studio, musí podporovat rámce zásobníku jazyka nebo prostředí, které jsou právě laděny.  
  
-   Můžete identifikovat a popsat sám sebe i může vrátit přidružené vlákno. Rámec zásobníku může také vrátit kontext kódu, který představuje aktuální ukazatele na instrukci, jakož i související dokumentaci a kontext vyhodnocení výrazu.  
  
-   Obsahuje vlastnosti, které popisují název, typ a hodnotu místní proměnné a argumenty a které jsou uvedeny v různých ladicích oknech integrovaného vývojového prostředí.  
  
-   Je reprezentován [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md) rozhraní, obvykle vytvoří pomocí ladicího stroje (DE) nebo virtuální počítač následkem podproces.  
  
## <a name="see-also"></a>Viz také  
 [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md)   
 [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)   
 [Ladicí stroj](../../extensibility/debugger/debug-engine.md)   
 [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md)
