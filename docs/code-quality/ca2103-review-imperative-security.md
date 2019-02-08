---
title: 'CA2103: Zkontrolujte imperativní zabezpečení'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2103
- ReviewImperativeSecurity
helpviewer_keywords:
- CA2103
- ReviewImperativeSecurity
ms.assetid: d24fde71-bdf6-46c0-8965-9a73dc33c1aa
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2417266da44c4af38e37eb8e0f67ac13a5a7823e
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55916723"
---
# <a name="ca2103-review-imperative-security"></a>CA2103: Zkontrolujte imperativní zabezpečení

|||
|-|-|
|TypeName|ReviewImperativeSecurity|
|CheckId|CA2103|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Metoda používá imperativní zabezpečení a může vytvářet oprávnění pomocí stavové informace nebo návratové hodnoty, která se může změnit, pokud je žádost aktivní.

## <a name="rule-description"></a>Popis pravidla
 Imperativní zabezpečení používá k určení oprávnění a akce zabezpečení při provádění kódu, ve srovnání s deklarativní zabezpečení, která využívá atributy pro uložení oprávnění a akcí v metadatech spravovaných objektů. Imperativní zabezpečení je velmi flexibilní, protože můžete nastavit stav objektu oprávnění a výběr akce zabezpečení pomocí informace, které nejsou k dispozici až do spuštění. Spolu s, která se dodává flexibilitu riziko, že informace o modulu runtime, který používáte k určení, že stav oprávnění nezůstávat beze změny, dokud akce je v platnosti.

 Používejte deklarativní zabezpečení vždy, když je to možné. Jsou Jednoduší na porozumění deklarativní požadavky.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Zkontrolujte požadavky imperativní zabezpečení, abyste měli jistotu, že stav oprávnění nevyžaduje informace, které můžete změnit tak dlouho, dokud se používá oprávnění.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla, je-li oprávnění nevyžaduje se měnícími daty. Je však lepší změnit imperativní požadavek na ekvivalentní deklarativní.

## <a name="see-also"></a>Viz také:

- [Pokyny pro zabezpečené kódování](/dotnet/standard/security/secure-coding-guidelines)
- [Data a modelování](/dotnet/framework/data/index)