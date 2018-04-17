---
title: Upozornění mobility | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.MobilityRules
helpviewer_keywords:
- managed code analysis warnings, mobility warnings
- mobility warnings
- warnings, mobility
ms.assetid: 9808054c-593b-4fc3-92cc-1fc45f41569c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9833b4ef197419b8a20c3758bcc4dca71d1f10e4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="mobility-warnings"></a>Upozornění mobility
Upozornění mobility podporovat efektivní spotřeby energie.  
  
## <a name="in-this-section"></a>V tomto oddílu  
  
|Pravidlo|Popis|  
|----------|-----------------|  
|[CA1600: Nepoužívejte prioritu nečinného procesu](../code-quality/ca1600-do-not-use-idle-process-priority.md)|Nenastavujte prioritu procesu na Neaktivní. Procesy, které mají nastaveny System.Diagnostics.ProcessPriorityClass.Idle, budou zaměstnávat procesor, pokud by jinak byl nečinný, a tím budou blokovat úsporný režim.|  
|[CA1601: Nepoužívejte časovače, které zabraňují změně stavu napájení](../code-quality/ca1601-do-not-use-timers-that-prevent-power-state-changes.md)|Vyšší frekvence periodické aktivity budou udržovat procesor zaneprázdněný a ovlivňovat časovače úspory energie nečinnosti, které vypnou zobrazení a pevné disky.|