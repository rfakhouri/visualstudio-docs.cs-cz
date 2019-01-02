---
title: Ladění úloh | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], tasks
ms.assetid: 5d60e9e8-305e-4a48-829f-b9440fc8af7b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: aa719871e075a5448fa2d351c5bd7950a833601a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53900149"
---
# <a name="debug-tasks"></a>Ladění úloh
Chcete-li ladit program, musí být spuštěn a ladicí stroj (DE) musí být připojené k němu, jinak DE musí být připojené k dříve spuštěný program. Po připojení, musíte vygenerovat DE určitých událostí po spuštění. V odpovědi balíček ladění pokusí vytvořit vazbu zarážky nastavené v integrovaném vývojovém prostředí. Když program dosáhne vázaná zarážka, zastaví a počká na vstup uživatele.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Problémy se zabezpečením](../../extensibility/debugger/security-issues.md)  
 Tento článek popisuje kroky zabezpečení, které jsou potřebné k ladění programu.  
  
 [Spuštění programu](../../extensibility/debugger/launching-a-program.md)  
 Obsahuje podrobné pokyny o tom, jak určit DE, která volá operačního systému spustit program.  
  
 [Připojení přímo k programu](../../extensibility/debugger/attaching-directly-to-a-program.md)  
 Popisuje proces pro ladění programu v procesu, který je již spuštěna.  
  
 [Odesílání událostí spuštění po spuštění](../../extensibility/debugger/sending-startup-events-after-a-launch.md)  
 Seznam událostí, které se provedou po DE je připojení k programu, dokud je program v jeho hlavní vstupní bod a je připravený pro ladění.  
  
 [Řízení spouštění](../../extensibility/debugger/control-of-execution.md)  
 Vysvětluje, jak je DE obvykle odešle událost vstupního bodu, na událost dokončení zatížení nebo událostí ukončení, v závislosti na okolnostech.  
  
 [Vytvořit vazbu zarážky](../../extensibility/debugger/binding-breakpoints.md)  
 Popisuje, jak, pokud uživatel nastaví zarážku, rozhraní IDE výrobky zpracovává žádost a zobrazí výzvu ladicí relaci vytvořit zarážku.  
  
 [Vyhodnocení výrazů](../../extensibility/debugger/evaluating-expressions.md)  
 Vysvětluje, jak se vytvářejí výrazy a co se stane při vyhodnocování výrazu.  
  
 [Vizualizace a zobrazení dat](../../extensibility/debugger/visualizing-and-viewing-data.md)  
 Vysvětluje, jak vizualizérů typů a vlastních prohlížečů jsou podporované ve vyhodnocovací filtr výrazů (EE).  
  
## <a name="related-sections"></a>Související oddíly  
 [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)  
 Popisuje hlavní koncepty ladění architektury.  
  
 [Komponenty ladicího programu](../../extensibility/debugger/debugger-components.md)  
 Obsahuje přehled komponent ladění sady Visual Studio, mezi které patří DE, EE a obslužné rutiny symbolů (SH).  
  
 [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md)  
 Vysvětluje, jak je DE pracuje současně v rámci kódu, dokumentace a kontexty vyhodnocení výrazu. Popisuje všech třech kontextech, umístění, pozice nebo vyhodnocení relevantní k němu.  
  
## <a name="see-also"></a>Viz také:  
 [Začínáme](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)