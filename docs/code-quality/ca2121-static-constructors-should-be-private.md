---
title: 'CA2121: Statické konstruktory by měly být privátní | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
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
ms.openlocfilehash: 6248371d4089b4d1e651a9ea3c391d293b94f40c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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