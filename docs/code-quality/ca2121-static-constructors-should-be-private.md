---
title: 'CA2121: Statické konstruktory by měly být privátní'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2121
- StaticConstructorsShouldBePrivate
helpviewer_keywords:
- CA2121
- StaticConstructorsShouldBePrivate
ms.assetid: ee93c620-8fc1-4e47-866c-d389c3ca9f2e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9aecfe8e0be0f5d32df41b7eb164423fd4d405db
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62545000"
---
# <a name="ca2121-static-constructors-should-be-private"></a>CA2121: Statické konstruktory by měly být privátní

|||
|-|-|
|TypeName|StaticConstructorsShouldBePrivate|
|CheckId|CA2121|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina

Typ má statický konstruktor, který není privátní.

## <a name="rule-description"></a>Popis pravidla

Statický konstruktor, označované také jako konstruktor třídy, slouží k inicializaci typu. Systém volá statický konstruktor před vytvořením první instance typu nebo předtím, než jsou odkazovány jakékoli statické členy. Uživatel nemá žádnou kontrolu nad tím, kdy je volána statický konstruktor. Pokud statický konstruktor není soukromý, může být volán jiným kódem než kódem systému. V závislosti na operacích, které jsou provedeny v konstruktoru, to může způsobit neočekávané chování.

Toto pravidlo je vynuceno kompilátory C# a Visual Basic.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Porušení jsou obvykle způsobeno jedním z následujících akcí:

- Definice statického konstruktoru pro váš typ a nebyly provedeny je privátní.

- Kompilátor programovacího jazyka přidány výchozí statický konstruktor do typu a nebyly provedeny je privátní.

Chcete-li vyřešit první druh porušení, soukromá statický konstruktor. Chcete-li vyřešit druhý typ, přidejte privátní statický konstruktor do typu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte těchto porušení. Pokud váš návrh softwaru vyžaduje explicitní volání konstruktoru statický konstruktor, je pravděpodobné, že návrh obsahuje závažné chyby a byste měli zkontrolovat.