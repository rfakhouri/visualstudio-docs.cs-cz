---
title: 'CA2121: Statické konstruktory by měly být privátní'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4f6eef1097565090fd1b9be572f9a33afed9afed
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31917909"
---
# <a name="ca2121-static-constructors-should-be-private"></a>CA2121: Statické konstruktory by měly být privátní
|||
|-|-|
|TypeName|StaticConstructorsShouldBePrivate|
|CheckId|CA2121|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Typ obsahuje statický konstruktor, který není privátní.

## <a name="rule-description"></a>Popis pravidla
 Statický konstruktor, také známé jako konstruktoru třídy, se používá k chybě při inicializaci typu. Systém volá statický konstruktor před vytvořením první instance typu nebo předtím, než jsou odkazovány jakékoli statické členy. Uživatel nemá žádnou kontrolu nad kdy se nazývá statického konstruktoru. Pokud statický konstruktor není soukromý, může být volán jiným kódem než kódem systému. V závislosti na operacích, které jsou provedeny v konstruktoru, to může způsobit neočekávané chování.

 Toto pravidlo se vynucuje kompilátory jazyka C# a Visual Basic.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Porušení jsou obvykle způsobeno jedním z následujících akcí:

-   Statický konstruktor definovaný pro váš typ a nedostaly privátní.

-   Programovací jazyk kompilátoru přidat výchozí statický konstruktor pro typ vašeho a nedostaly privátní.

 Pokud chcete vyřešit první druh porušení, soukromá statického konstruktoru. Opravit druhý typ, přidejte do vašeho typu privátní statického konstruktoru.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Tato porušení nejsou potlačeny. Pokud váš návrh softwaru vyžaduje explicitní volání statického konstruktoru, je pravděpodobné, že návrh obsahuje závažné chyby a měli zkontrolovat.