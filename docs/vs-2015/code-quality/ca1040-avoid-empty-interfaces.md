---
title: 'CA1040: Vyhněte se prázdným rozhraním | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1040
- AvoidEmptyInterfaces
helpviewer_keywords:
- AvoidEmptyInterfaces
- CA1040
ms.assetid: 120a741b-5fd1-4836-8453-7857e0cd0380
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: bc785967b4e27599b4a04aeb7740b53b5076938d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62559739"
---
# <a name="ca1040-avoid-empty-interfaces"></a>CA1040: Vyhněte se prázdným rozhraním
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|AvoidEmptyInterfaces|
|CheckId|CA1040|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Rozhraní není deklarovat všechny členy nebo implementovat dvě nebo více rozhraní.

## <a name="rule-description"></a>Popis pravidla
 Rozhraní definují členy ujednávající jejich chování nebo užití. Funkčnost popsaná rozhraním může být osvojena libovolným typem bez ohledu na to, kde se typ vyskytuje v hierarchii dědičnosti. Typ implementuje rozhraní tím, že poskytuje implementace jeho členů. Prázdné rozhraní nedefinuje žádné členy. Nedefinuje proto kontrakt, který je možné implementovat.

 Pokud váš návrh obsahuje prázdný implementovat rozhraní, které typy se očekává, pravděpodobně používáte rozhraní jako značku nebo způsob, jak identifikovat skupinu typů. Pokud tato identifikace dojde za běhu, je správný způsob, jak toho dosáhnout pomocí vlastního atributu. Přítomnost nebo absence atributu nebo vlastnosti atributu, použijte k identifikaci cílové typy. Je-li označením se musí vyskytovat v době kompilace, je nepřijatelné využívat prázdné rozhraní.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Odebrat rozhraní nebo přidat členy do něj. Pokud prázdné rozhraní používá k označení sadu typů, nahraďte rozhraní vlastního atributu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla, pokud rozhraní se používá k identifikaci sadu typů v době kompilace.

## <a name="example"></a>Příklad
 Následující příklad ukazuje prázdné rozhraní.

 [!code-cpp[FxCop.Design.InterfacesNotEmpty#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.InterfacesNotEmpty/cpp/FxCop.Design.InterfacesNotEmpty.cpp#1)]
 [!code-csharp[FxCop.Design.InterfacesNotEmpty#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.InterfacesNotEmpty/cs/FxCop.Design.InterfacesNotEmpty.cs#1)]
 [!code-vb[FxCop.Design.InterfacesNotEmpty#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.InterfacesNotEmpty/vb/FxCop.Design.InterfacesNotEmpty.vb#1)]
