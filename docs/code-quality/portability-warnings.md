---
title: "Upozornění přenositelnosti | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.PortabilityRules
helpviewer_keywords:
- portability warnings
- managed code analysis warnings, portability warnings
- warnings, portability
ms.assetid: 902e859a-2153-4970-baaa-8a5b4a11806f
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: efd2d56700c70b27771623e618f61675b174da01
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="portability-warnings"></a>Upozornění přenositelnosti
Upozornění přenositelnosti podpora přenositelnost v rámci různých operačních systémech.  
  
## <a name="in-this-section"></a>V tomto oddílu  
  
|Pravidlo|Popis|  
|----------|-----------------|  
|[CA1900: Pole hodnot by měla být přenosná](../code-quality/ca1900-value-type-fields-should-be-portable.md)|Toto pravidlo zkontroluje, že struktury, které jsou deklarovány s použitím atribut explicitní rozložení zarovnané správně při zařazen do nespravovaného kódu v 64bitových operačních systémech.|  
|[CA1901: Deklarace volání by měla být přenosná](../code-quality/ca1901-p-invoke-declarations-should-be-portable.md)|Toto pravidlo vyhodnotí velikost jednotlivých parametrů a vrátí hodnotu, která P/Invoke a ověřuje, že jejich velikost je správný, když zařazen do nespravovaného kódu na 32bitové a 64bitové verze operačních systémů.|  
|[CA1903: Použijte pouze API z cílového rozhraní .NET Framework](../code-quality/ca1903-use-only-api-from-targeted-framework.md)|Člen nebo typ používá člen nebo typ, který byl uveden v aktualizaci Service Pack, která nebyla zahrnuta stejně jako cílové rozhraní projektu.|