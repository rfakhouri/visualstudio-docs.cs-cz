---
title: Řízení provádění a vyhodnocení stavu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], execution control
- expression evaluation, control of execution
ms.assetid: 55adde38-1622-4b51-83cb-ce1b04c1ca7a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e71fb57a4890c29652473338391a0f7181d19ac0
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55010412"
---
# <a name="execution-control-and-state-evaluation"></a>Ovládací prvek a stav zkušební spuštění
Ladění aplikace vyžaduje implementaci funkce řízení provádění, jako krokování do funkce, zastavování na zarážkách a pokračování v provádění. Ladění základních tříd sady Visual Studio jeho řízení provádění na události se posílají mezi komponenty ladicího programu.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Řízení programu](../../extensibility/debugger/program-control.md)  
 Obsahuje tyto rutiny, ke kterým dochází na úrovni programu: nastavení dalšího příkazu, provádění, krokování, budete pokračovat, pozastavení a obnovení.  
  
 [Metody související se zarážkou](../../extensibility/debugger/breakpoint-related-methods.md)  
 Definuje je mez a čeká se na typy zarážek, které podporuje Visual Studio.  
  
 [Vyhodnocení zásobníku volání](../../extensibility/debugger/call-stack-evaluation.md)  
 Tento článek popisuje implementaci metody, které umožňují zobrazení rámců zásobníku volání během režimu pozastavení.  
  
 [Vyhodnocení výrazu](../../extensibility/debugger/expression-evaluation-visual-studio-debugging-sdk.md)  
 Vysvětluje, jak ladicího stroje (DE) Správce výraz vyhodnocení (EE) a relace ladění se podílejí analýze a hodnocení výrazu zadali do jedné ze systému windows z integrovaného vývojového prostředí.  
  
 [Události ovládacích prvků](../../extensibility/debugger/control-events.md)  
 Tento článek popisuje rozhraní použité k odesílání událostí během řízené provádění programu.