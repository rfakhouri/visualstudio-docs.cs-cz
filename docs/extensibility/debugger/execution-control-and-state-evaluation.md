---
title: Řízení provádění a vyhodnocení stavu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], execution control
- expression evaluation, control of execution
ms.assetid: 55adde38-1622-4b51-83cb-ce1b04c1ca7a
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bda531e94bdea07ee37eed2b0b79e6f0667ba28e
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66315240"
---
# <a name="execution-control-and-state-evaluation"></a>Ovládací prvek a stav zkušební spuštění
Ladění aplikace vyžaduje implementaci funkce řízení provádění, jako krokování do funkce, zastavování na zarážkách a pokračování v provádění. Ladění základních tříd sady Visual Studio jeho řízení provádění na události se posílají mezi komponenty ladicího programu.

## <a name="in-this-section"></a>V tomto oddílu
 [Ovládací prvek programu](../../extensibility/debugger/program-control.md) uvádí následující rutiny, ke kterým dochází na úrovni programu: nastavení dalšího příkazu, provádění, krokování, budete pokračovat, pozastavení a obnovení.

 [Metody související se zarážkou](../../extensibility/debugger/breakpoint-related-methods.md) definuje je mez a čeká se na typy zarážek, které podporuje Visual Studio.

 [Vyhodnocení zásobníku volání](../../extensibility/debugger/call-stack-evaluation.md) Popisuje implementaci metody, které umožňují zobrazení rámců zásobníku volání během režimu pozastavení.

 [Vyhodnocení výrazu](../../extensibility/debugger/expression-evaluation-visual-studio-debugging-sdk.md) vysvětluje, jak se podílejí ladicího stroje (DE), vyhodnocení výrazu (EE) a správce ladění relace v analýze a hodnocení výrazu zadali do jednoho okna v rozhraní IDE.

 [Ovládací prvek události](../../extensibility/debugger/control-events.md) popisuje rozhraní použité k odesílání událostí během řízené provádění programu.