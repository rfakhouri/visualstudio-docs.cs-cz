---
title: 'CA2149: Transparentní metody nesmějí provádět volání do nativního kódu | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2149
ms.assetid: 28951bd7-f3db-4871-99aa-bad68d1ead80
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 16f79922b4b3f586b6b5a05b04237851807f0502
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42673011"
---
# <a name="ca2149-transparent-methods-must-not-call-into-native-code"></a>CA2149: Transparentní metody nesmějí provádět volání do nativního kódu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA2149: transparentní metody nesmějí provádět volání do nativního kódu](https://docs.microsoft.com/visualstudio/code-quality/ca2149-transparent-methods-must-not-call-into-native-code).  
  
TypeName | TransparentMethodsMustNotCallNativeCode |  
| ID kontroly | CA2149 |  
| Kategorie | Microsoft.Security|  
| Zásadní změna | Zásadní |  
  
## <a name="cause"></a>příčina  
 Metoda volá nativní funkce prostřednictvím pahýl metody, jako je například P/Invoke.  
  
## <a name="rule-description"></a>Popis pravidla  
 Toto pravidlo je vyvoláno na jakékoli transparentní metodě, která přímo volá nativní kód, například prostřednictvím P/Invoke. Porušení tohoto pravidla vede k <xref:System.MethodAccessException> v modelu transparentnosti úrovně 2 a k úplnému pro <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A> v modelu transparentnosti úrovně 1.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, označte metody, která volá nativní kód <xref:System.Security.SecurityCriticalAttribute> nebo <xref:System.Security.SecuritySafeCriticalAttribute> atribut.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 [!code-csharp[FxCop.Security.CA2149.TransparentMethodsMustNotCallNativeCode#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2149.transparentmethodsmustnotcallnativecode/cs/ca2149 - transparentmethodsmustnotcallnativecode.cs#1)]



