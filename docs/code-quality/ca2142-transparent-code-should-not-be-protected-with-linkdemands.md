---
title: 'CA2142: Transparentní kód by neměl být chráněn pomocí LinkDemands'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2142
ms.assetid: 6dc59053-5dd9-4583-bf10-5f339107e59f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5ad4ca58848412944d28874554383caf178c2af4
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54970848"
---
# <a name="ca2142-transparent-code-should-not-be-protected-with-linkdemands"></a>CA2142: Transparentní kód by neměl být chráněn pomocí LinkDemands

|||
|-|-|
|TypeName|TransparentMethodsShouldNotBeProtectedWithLinkDemands|
|CheckId|CA2142|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Transparentní metoda vyžaduje, <xref:System.Security.Permissions.SecurityAction> nebo další požadavek zabezpečení.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo je vyvoláno transparentními metodami, které vyžadují pravidla LinkDemand pro přístup k nim. Kód transparentní z hlediska zabezpečení by neměl být odpovědný za ověření zabezpečení operace, a proto by neměl požadovat oprávnění. Protože transparentní metody mají být zabezpečení neutrální, jejich by neměla provádět rozhodnutí o zabezpečení. Kromě toho by neměl být bezpečně kritický kód, který rozhodování zabezpečení, spoléhat na transparentnímu kódu dříve provedli tato rozhodnutí.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, odeberte požadavek propojení na transparentní metodu nebo označte metodu s <xref:System.Security.SecuritySafeCriticalAttribute> kontroly atribut, pokud se provádí zabezpečení, jako jsou požadavky na zabezpečení.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 V následujícím příkladu pravidlo je vyvoláno na metodě vzhledem k tomu, že metoda je transparentní a je označená pomocí LinkDemand <xref:System.Security.PermissionSet> , který obsahuje <xref:System.Security.Permissions.SecurityAction>.

 [!code-csharp[FxCop.Security.CA2142.TransparentMethodsShouldNotBeProtectedWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2142-transparent-code-should-not-be-protected-with-linkdemands_1.cs)]

 Nepotlačujte upozornění na toto pravidlo.