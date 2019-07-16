---
title: Řízení provádění a vyhodnocení stavu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], execution control
- expression evaluation, control of execution
ms.assetid: 55adde38-1622-4b51-83cb-ce1b04c1ca7a
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: bc6476c925f37d70ab45bae129a8b8a379ee519c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68152773"
---
# <a name="execution-control-and-state-evaluation"></a>Řízení provádění a vyhodnocení stavu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

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
