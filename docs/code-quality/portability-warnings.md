---
title: Upozornění přenositelnosti
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- vs.codeanalysis.PortabilityRules
helpviewer_keywords:
- portability warnings
- managed code analysis warnings, portability warnings
- warnings, portability
ms.assetid: 902e859a-2153-4970-baaa-8a5b4a11806f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9f181411d8379c8583057419c2a31f6b27c9d884
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53882452"
---
# <a name="portability-warnings"></a>Upozornění přenositelnosti
Upozornění přenositelnosti podporují přenositelnost napříč různými operačními systémy.

## <a name="in-this-section"></a>V tomto oddílu

|Pravidlo|Popis|
|----------|-----------------|
|[CA1900: Pole hodnot by měla být přenosná](../code-quality/ca1900-value-type-fields-should-be-portable.md)|Toto pravidlo zkontroluje, že budou při zařazení na nespravovaný kód v 64bitových operačních systémech správně zarovnány struktury, které jsou deklarovány pomocí explicitního rozložení atribut.|
|[CA1901: Deklarace volání nespravovaného kódu by měla být přenosná](../code-quality/ca1901-p-invoke-declarations-should-be-portable.md)|Toto pravidlo vyhodnotí velikost každého parametru a vrácené hodnoty deklarace P/Invoke a ověří, jestli je správná při zařazení na nespravovaný kód v 32bitové a 64bitové operační systémy jejich velikost.|
|[CA1903: Použijte pouze API z cíleného rozhraní](../code-quality/ca1903-use-only-api-from-targeted-framework.md)|Člen nebo typ používá člen nebo typ, který byl uveden v aktualizaci Service Pack, která nebyla zahrnuta stejně jako cílové rozhraní projektu.|