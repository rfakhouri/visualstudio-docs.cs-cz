---
title: 'CA1040: Vyhněte se prázdným rozhraním'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1040
- AvoidEmptyInterfaces
helpviewer_keywords:
- AvoidEmptyInterfaces
- CA1040
ms.assetid: 120a741b-5fd1-4836-8453-7857e0cd0380
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 25e798dac05213d8f66fe7ba3c7a737a71f6030e
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2019
ms.locfileid: "65842242"
---
# <a name="ca1040-avoid-empty-interfaces"></a>CA1040: Vyhněte se prázdným rozhraním

|||
|-|-|
|TypeName|AvoidEmptyInterfaces|
|CheckId|CA1040|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina

Rozhraní není deklarovat všechny členy nebo implementovat dvě nebo více rozhraní.

Ve výchozím nastavení, toto pravidlo pouze prohledá externě viditelného rozhraní, ale je to [konfigurovatelné](#configurability).

## <a name="rule-description"></a>Popis pravidla

Rozhraní definují členy ujednávající jejich chování nebo užití. Funkčnost popsaná rozhraním může být osvojena libovolným typem bez ohledu na to, kde se typ vyskytuje v hierarchii dědičnosti. Typ implementuje rozhraní tím, že poskytuje implementace jeho členů. Prázdné rozhraní nedefinuje žádné členy. Nedefinuje proto kontrakt, který je možné implementovat.

Pokud váš návrh obsahuje prázdný implementovat rozhraní, které typy se očekává, pravděpodobně používáte rozhraní jako značku nebo způsob, jak identifikovat skupinu typů. Pokud tato identifikace dojde za běhu, je správný způsob, jak toho dosáhnout pomocí vlastního atributu. Přítomnost nebo absence atributu nebo vlastnosti atributu, použijte k identifikaci cílové typy. Je-li označením se musí vyskytovat v době kompilace, je nepřijatelné využívat prázdné rozhraní.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Odebrat rozhraní nebo přidat členy do něj. Pokud prázdné rozhraní používá k označení sadu typů, nahraďte rozhraní vlastního atributu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit upozornění tohoto pravidla, pokud rozhraní se používá k identifikaci sadu typů v době kompilace.

## <a name="configurability"></a>Možnosti konfigurace:

Pokud používáte systém toto pravidlo z [analyzátory FxCop](install-fxcop-analyzers.md) (a ne prostřednictvím statickou analýzu kódu), které části můžete nakonfigurovat vašeho základu kódu pro toto pravidlo spouštět, v závislosti na jejich přístupnost. Například k určení, že se má pravidlo spustit jenom na povrchu neveřejné rozhraní API, přidejte následující dvojice klíč hodnota do souboru .editorconfig ve vašem projektu:

```ini
dotnet_code_quality.ca1040.api_surface = private, internal
```

Tuto možnost pro právě toto pravidlo, všechna pravidla nebo pro všechna pravidla můžete konfigurovat v této kategorii (návrh). Další informace najdete v tématu [analyzátory FxCop konfigurace](configure-fxcop-analyzers.md).

## <a name="example"></a>Příklad

Následující příklad ukazuje prázdné rozhraní.

[!code-csharp[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/CSharp/ca1040-avoid-empty-interfaces_1.cs)]
[!code-cpp[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/CPP/ca1040-avoid-empty-interfaces_1.cpp)]
[!code-vb[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/VisualBasic/ca1040-avoid-empty-interfaces_1.vb)]