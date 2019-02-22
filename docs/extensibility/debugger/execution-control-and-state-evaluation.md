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
ms.openlocfilehash: bd04cfa1e271f94f1b37aa0fbd62e9b846d9a70d
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56714683"
---
# <a name="execution-control-and-state-evaluation"></a>Ovládací prvek a stav zkušební spuštění
Ladění aplikace vyžaduje implementaci funkce řízení provádění, jako krokování do funkce, zastavování na zarážkách a pokračování v provádění. Ladění základních tříd sady Visual Studio jeho řízení provádění na události se posílají mezi komponenty ladicího programu.

## <a name="in-this-section"></a>V tomto oddílu
 [Ovládací prvek programu](../../extensibility/debugger/program-control.md) uvádí následující rutiny, ke kterým dochází na úrovni programu: nastavení dalšího příkazu, provádění, krokování, budete pokračovat, pozastavení a obnovení.

 [Metody související se zarážkou](../../extensibility/debugger/breakpoint-related-methods.md) definuje je mez a čeká se na typy zarážek, které podporuje Visual Studio.

 [Vyhodnocení zásobníku volání](../../extensibility/debugger/call-stack-evaluation.md) Popisuje implementaci metody, které umožňují zobrazení rámců zásobníku volání během režimu pozastavení.

 [Vyhodnocení výrazu](../../extensibility/debugger/expression-evaluation-visual-studio-debugging-sdk.md) vysvětluje, jak se podílejí ladicího stroje (DE), vyhodnocení výrazu (EE) a správce ladění relace v analýze a hodnocení výrazu zadali do jednoho okna v rozhraní IDE.

 [Ovládací prvek události](../../extensibility/debugger/control-events.md) popisuje rozhraní použité k odesílání událostí během řízené provádění programu.