---
title: "CA2207: Inicializujte vloženou hodnotu statických polí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- InitializeValueTypeStaticFieldsInline
- CA2207
helpviewer_keywords:
- CA2207
- InitializeValueTypeStaticFieldsInline
ms.assetid: d1ea9d8b-ecc2-46ca-86e2-c41dd0e76658
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7f22975ba591e4300e54a4bda01f3802b393ae59
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca2207-initialize-value-type-static-fields-inline"></a>CA2207: Inicializujte vloženou hodnotu statických polí
|||  
|-|-|  
|TypeName|InitializeValueTypeStaticFieldsInline|  
|CheckId|CA2207|  
|Kategorie|Microsoft.Usage|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Typ hodnoty deklaruje explicitní statického konstruktoru.  
  
## <a name="rule-description"></a>Popis pravidla  
 Pokud je deklarovaný typ hodnoty, je zde nevyskytlo výchozí inicializace kde všechna pole typu hodnoty nastaveny na nulu a všechna pole typu odkazu jsou nastaveny na `null` (`Nothing` v jazyce Visual Basic). Explicitní statického konstruktoru pouze záruku, že se na spuštění před konstruktoru instance nebo se označuje jako statický člen daného typu. Proto pokud typ je vytvořen bez volání konstruktoru instance, statického konstruktoru není zaručena ke spuštění.  
  
 Pokud všechny statických dat je inicializovaného vložené a je deklarovaná žádné explicitní statického konstruktoru, přidejte kompilátory jazyka C# a Visual Basic `beforefieldinit` příznak v definici třídy MSIL. Kompilátory také přidat privátní statické konstruktor, který obsahuje kód statické inicializace. Tento konstruktor privátní statické záruku, že spustit předtím, než jsou přístupné všechny statické pole typu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo inicializovat všechny statických dat při je deklarovaná a odebrat statického konstruktoru.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1810: Inicializujte odkazový typ statického pole vloženě](../code-quality/ca1810-initialize-reference-type-static-fields-inline.md)