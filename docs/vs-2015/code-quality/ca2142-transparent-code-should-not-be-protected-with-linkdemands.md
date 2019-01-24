---
title: 'CA2142: Transparentní kód nemůže být chráněn pomocí LinkDemands | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2142
ms.assetid: 6dc59053-5dd9-4583-bf10-5f339107e59f
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 11bd1668e4ab599461d3619c63cd3c9732a05b4f
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54761344"
---
# <a name="ca2142-transparent-code-should-not-be-protected-with-linkdemands"></a>CA2142: Transparentní kód by neměl být chráněn pomocí LinkDemands
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TransparentMethodsShouldNotBeProtectedWithLinkDemands|
|CheckId|CA2142|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Transparentní metoda vyžaduje, <xref:System.Security.Permissions.SecurityAction> nebo další požadavek zabezpečení.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo je vyvoláno na transparentních metodách, které vyžadují pro přístup k nim pravidla LinkDemand. Kód transparentní z hlediska zabezpečení by neměl být odpovědný za ověření zabezpečení operace, a proto by neměl požadovat oprávnění. Protože transparentní metody mají být zabezpečení neutrální, jejich by neměla provádět rozhodnutí o zabezpečení. Kromě toho by neměl být bezpečně kritický kód, který rozhodování zabezpečení, spoléhat na transparentnímu kódu dříve provedli tato rozhodnutí.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, odeberte požadavek propojení na transparentní metodu nebo označte metodu s <xref:System.Security.SecuritySafeCriticalAttribute> kontroly atribut, pokud se provádí zabezpečení, jako jsou požadavky na zabezpečení.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 V následujícím příkladu pravidlo je vyvoláno na metodě vzhledem k tomu, že metoda je transparentní a je označená pomocí LinkDemand <xref:System.Security.PermissionSet> , který obsahuje <xref:System.Security.Permissions.SecurityAction>.

 [!code-csharp[FxCop.Security.CA2142.TransparentMethodsShouldNotBeProtectedWithLinkDemands#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2142.transparentmethodsshouldnotbeprotectedwithlinkdemands/cs/ca2142 -transparentmethodsshouldnotbeprotectedwithlinkdemands.cs#1)]

 Nepotlačujte upozornění na toto pravidlo.
