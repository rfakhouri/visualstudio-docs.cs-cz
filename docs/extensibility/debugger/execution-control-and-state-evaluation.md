---
title: Řízení provádění a stavu vyhodnocení | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], execution control
- expression evaluation, control of execution
ms.assetid: 55adde38-1622-4b51-83cb-ce1b04c1ca7a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d306ffe484605a081afa81afdcdcaa1a70339c84
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="execution-control-and-state-evaluation"></a>Řízení provádění a stavu vyhodnocení
Ladění aplikace vyžaduje implementace funkce řízení provádění, jako zanoříte se do funkce, zastavování na zarážkách a pokračování provádění. Visual Studio ladění základů jeho řízení provádění na události odeslané mezi součástmi ladicí program.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Řízení programu](../../extensibility/debugger/program-control.md)  
 Uvádí následující rutiny, které probíhat na úrovni program: příkaz Další nastavení, provádění, krokování, budete pokračovat, pozastavení a obnovení.  
  
 [Metody související se zarážkou](../../extensibility/debugger/breakpoint-related-methods.md)  
 Definuje hranice a čeká se na typy zarážky, které podporuje Visual Studio.  
  
 [Vyhodnocení zásobníku volání](../../extensibility/debugger/call-stack-evaluation.md)  
 Popisuje provádění metody, které umožňují zobrazení rámce zásobníku zásobníku volání při režimu pozastavení.  
  
 [Vyhodnocení výrazu](../../extensibility/debugger/expression-evaluation-visual-studio-debugging-sdk.md)  
 Vysvětluje, jak modul ladění (DE) manager výraz vyhodnocení (EE) a relace ladění se účastní analýzu a vyhodnocení výrazu zadali do jedné ze systému windows rozhraní IDE.  
  
 [Události ovládacích prvků](../../extensibility/debugger/control-events.md)  
 Popisuje rozhraní používá k odesílání událostí během řízené provádění tohoto programu.