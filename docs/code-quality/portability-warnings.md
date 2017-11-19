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
ms.openlocfilehash: 112f3686f2a3d21b2d5d493498b42e9b63fdb05b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="portability-warnings"></a>Upozornění přenositelnosti
Upozornění přenositelnosti podpora přenositelnost v rámci různých operačních systémech.  
  
## <a name="in-this-section"></a>V tomto oddílu  
  
|Pravidlo|Popis|  
|----------|-----------------|  
|[CA1900: Pole hodnot typu by měla být přenosná](../code-quality/ca1900-value-type-fields-should-be-portable.md)|Toto pravidlo zkontroluje, že struktury, které jsou deklarovány s použitím atribut explicitní rozložení zarovnané správně při zařazen do nespravovaného kódu v 64bitových operačních systémech.|  
|[CA1901: Deklarace volání by měla být přenosná](../code-quality/ca1901-p-invoke-declarations-should-be-portable.md)|Toto pravidlo vyhodnotí velikost jednotlivých parametrů a vrátí hodnotu, která P/Invoke a ověřuje, že jejich velikost je správný, když zařazen do nespravovaného kódu na 32bitové a 64bitové verze operačních systémů.|  
|[CA1903: Použijte pouze API z cílové rozhraní](../code-quality/ca1903-use-only-api-from-targeted-framework.md)|Člen nebo typ používá člen nebo typ, který byl uveden v aktualizaci Service Pack, která nebyla zahrnuta stejně jako cílové rozhraní projektu.|