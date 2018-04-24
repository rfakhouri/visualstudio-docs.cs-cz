---
title: 'CA2124: Zabalte ohroženou klauzuli finally do vnějšího bloku try'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2124
- WrapVulnerableFinallyClausesInOuterTry
helpviewer_keywords:
- CA2124
- WrapVulnerableFinallyClausesInOuterTry
ms.assetid: 82efd224-9e60-4b88-a0f5-dfabcc49a254
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d46bc7bcfa8c1918091fabbbd759172259ea9ba6
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca2124-wrap-vulnerable-finally-clauses-in-outer-try"></a>CA2124: Zabalte ohroženou klauzuli finally do vnějšího bloku try
|||
|-|-|
|TypeName|WrapVulnerableFinallyClausesInOuterTry|
|CheckId|CA2124|
|Kategorie|Microsoft.Security|
|Narušující změna|Bez ukončování řádků|

## <a name="cause"></a>příčina
 Ve verzích 1.0 a 1.1 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], obsahuje veřejný nebo chráněné metody `try` / `catch` / `finally` bloku. `finally` Bloku se zobrazí resetovat stav zabezpečení a není uzavřený v `finally` bloku.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo vyhledá `try` / `finally` bloků v kódu, která je cílena verze 1.0 a 1.1 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] , může být zranitelné v důsledku filtry škodlivý výjimek v zásobníku volání. Pokud citlivé operace, jako je například zosobnění probíhají v bloku try a je vyvolána výjimka, filtr můžete provést před `finally` bloku. Například zosobnění to znamená, že filtr by spustit jako se zosobněným uživatelem. Filtry jsou aktuálně implementable pouze v jazyce Visual Basic.

> [!WARNING]
>  **Poznámka:** verze 2.0 nebo novější z [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], modul runtime automaticky chrání `try` / `catch` /  `finally` blokovat z filtry výjimek škodlivý, pokud dojde k vynulování přímo v rámci metody, která obsahuje bloku výjimky.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Umístit rozbalenou `try` / `finally` v bloku vnější opakujte. Najdete v druhém příkladu, který následuje dále. Vynutí se tak `finally` ke spuštění před kód filtru.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="pseudo-code-example"></a>Příklad pseudo kódu

### <a name="description"></a>Popis
 Následující kód pseudo ilustruje vzor zjistil tímto pravidlem.

### <a name="code"></a>Kód

```
try {
   // Do some work.
   Impersonator imp = new Impersonator("John Doe");
   imp.AddToCreditCardBalance(100);
}
finally {
   // Reset security state.
   imp.Revert();
}
```

## <a name="example"></a>Příklad
 Následující pseudo kód ukazuje vzor, můžete použít k ochraně kódu a splňovat toto pravidlo.

```
try {
     try {
        // Do some work.
     }
     finally {
        // Reset security state.
     }
}
catch()
{
    throw;
}
```