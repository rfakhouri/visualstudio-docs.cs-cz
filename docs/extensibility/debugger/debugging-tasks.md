---
title: "Ladění úlohy | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], tasks
ms.assetid: 5d60e9e8-305e-4a48-829f-b9440fc8af7b
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c8bd22d71753a8bf86adbe2b437407481388c48d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="debugging-tasks"></a>Ladění úlohy
Chcete-li ladit program, musí být spuštěn a modul ladění (DE) musí být připojené k němu, jinak DE musí být připojené k dříve spuštěného programu. Po připojení, musí je DE generovat určité události spuštění. V odpovědi balíček ladění pokusí navázat zarážky nastavení v IDE. Pokud se program dotkne vázané breakpoint, zastaví a čeká na vstup uživatele.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Problémy se zabezpečením](../../extensibility/debugger/security-issues.md)  
 Popisuje kroky zabezpečení, které jsou nutné k ladění programu.  
  
 [Spuštění programu](../../extensibility/debugger/launching-a-program.md)  
 Obsahuje podrobné pokyny o tom, jak určit DE, který volá operačního systému spustit program.  
  
 [Připojení přímo k programu](../../extensibility/debugger/attaching-directly-to-a-program.md)  
 Popisuje postup používá k ladění programu v procesu, který je již spuštěn.  
  
 [Odesílání událostí spuštění po spuštění](../../extensibility/debugger/sending-startup-events-after-a-launch.md)  
 Seznam událostí, které probíhat jednou DE je připojen k programu, dokud program jeho hlavní vstupní bod a je připravený pro ladění.  
  
 [Řízení spouštění](../../extensibility/debugger/control-of-execution.md)  
 Vysvětluje, jak je DE obvykle odesílá událost vstupního bodu, o dokončení zatížení událost nebo zastavení událostí, v závislosti na v případech.  
  
 [Vazba zarážky](../../extensibility/debugger/binding-breakpoints.md)  
 Popisuje, jak, pokud uživatel nastaví zarážku, rozhraní IDE výrobky zpracovává žádosti a vyzve k relaci ladění k vytvoření zarážce.  
  
 [Vyhodnocení výrazů](../../extensibility/debugger/evaluating-expressions.md)  
 Vysvětluje, jak se vytvářejí výrazy, co se stane při vyhodnocování výrazu.  
  
 [Vizualizace a zobrazení dat](../../extensibility/debugger/visualizing-and-viewing-data.md)  
 Vysvětluje, jak vizualizérech typu a vlastní prohlížeče jsou podporovány nástrojem vyhodnocovací filtr výrazů (EE).  
  
## <a name="related-sections"></a>Související oddíly  
 [Koncepty ladicí program](../../extensibility/debugger/debugger-concepts.md)  
 Popisuje hlavní koncepty ladění architektury.  
  
 [Ladicí program komponenty](../../extensibility/debugger/debugger-components.md)  
 Poskytuje přehled ladění součásti sady Visual Studio, mezi které patří DE, EE a symbol obslužné rutiny (SH).  
  
 [Kontexty ladicí program](../../extensibility/debugger/debugger-contexts.md)  
 Vysvětluje, jak funguje DE současně v kódu, dokumentace a kontexty vyhodnocení výrazu. Popisuje, pro každou tři kontexty, umístění, pozice nebo vyhodnocení relevantní k němu.  
  
## <a name="see-also"></a>Viz také  
 [Začínáme](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)