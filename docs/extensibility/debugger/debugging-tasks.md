---
title: Ladění úloh | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], tasks
ms.assetid: 5d60e9e8-305e-4a48-829f-b9440fc8af7b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 299db84fb06679bfbf9dff92234c944cbdec6295
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62925814"
---
# <a name="debug-tasks"></a>Ladění úloh
Chcete-li ladit program, musí být spuštěn a ladicí stroj (DE) musí být připojené k němu, jinak DE musí být připojené k dříve spuštěný program. Po připojení, musíte vygenerovat DE určitých událostí po spuštění. V odpovědi balíček ladění pokusí vytvořit vazbu zarážky nastavené v integrovaném vývojovém prostředí. Když program dosáhne vázaná zarážka, zastaví a počká na vstup uživatele.

## <a name="in-this-section"></a>V tomto oddílu
 [Problémy se zabezpečením](../../extensibility/debugger/security-issues.md) popisuje kroky zabezpečení, které jsou potřebné k ladění programu.

 [Spusťte program](../../extensibility/debugger/launching-a-program.md) obsahuje podrobné pokyny o tom, jak určit DE, která volá operačního systému spustit program.

 [Připojení přímo k programu](../../extensibility/debugger/attaching-directly-to-a-program.md) popisuje proces pro ladění programu v procesu, který je již spuštěna.

 [Odesílání událostí spuštění po spuštění](../../extensibility/debugger/sending-startup-events-after-a-launch.md) uvádí události, které se provedou po DE je připojení k programu, dokud je program v jeho hlavní vstupní bod a je připravený pro ladění.

 [Řízení spouštění](../../extensibility/debugger/control-of-execution.md) vysvětluje, jak je DE obvykle odešle událost vstupního bodu, na událost dokončení zatížení nebo událostí ukončení, v závislosti na okolnostech.

 [Vytvořit vazbu zarážky](../../extensibility/debugger/binding-breakpoints.md) popisuje, jak, pokud uživatel nastaví zarážku, rozhraní IDE výrobky zpracovává žádost a zobrazí výzvu ladicí relaci vytvořit zarážku.

 [Vyhodnocení výrazů](../../extensibility/debugger/evaluating-expressions.md) vysvětluje, jak vytvořit výrazy a co se stane při vyhodnocování výrazu.

 [Vizualizace a zobrazení dat](../../extensibility/debugger/visualizing-and-viewing-data.md) vysvětluje, jak vizualizérů typů a vlastních prohlížečů jsou podporované ve vyhodnocovací filtr výrazů (EE).

## <a name="related-sections"></a>Související oddíly
 [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md) popisuje hlavní koncepty ladění architektury.

 [Komponenty ladicího programu](../../extensibility/debugger/debugger-components.md) obsahuje základní informace o ladění komponenty, které zahrnují DE, EE a obslužné rutiny symbolů (SH) sady Visual Studio.

 [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md) vysvětluje, jak funguje DE současně v kontextech hodnocení kódu, dokumentace a výraz. Popisuje všech třech kontextech, umístění, pozice nebo vyhodnocení relevantní k němu.

## <a name="see-also"></a>Viz také:
 [Začínáme](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)