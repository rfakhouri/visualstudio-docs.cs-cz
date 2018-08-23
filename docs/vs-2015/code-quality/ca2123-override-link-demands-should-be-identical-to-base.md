---
title: 'CA2123: Požadavky na přepsání odkazu musejí být identické s bází | Dokumentace Microsoftu'
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
- CA2123
- OverrideLinkDemandsShouldBeIdenticalToBase
helpviewer_keywords:
- OverrideLinkDemandsShouldBeIdenticalToBase
- CA2123
ms.assetid: 4538ecd5-fc6f-4480-ab00-90b2ce4730db
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 963fe3c5bea24aac6e46dfb66973e92a39352ffa
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666557"
---
# <a name="ca2123-override-link-demands-should-be-identical-to-base"></a>CA2123: Požadavky na přepsání odkazu musejí být identické s bází
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA2123: požadavky na přepsání odkazu musejí být identické s bází](https://docs.microsoft.com/visualstudio/code-quality/ca2123-override-link-demands-should-be-identical-to-base).  
  
TypeName | OverrideLinkDemandsShouldBeIdenticalToBase |  
| ID kontroly | CA2123 |  
| Kategorie | Microsoft.Security|  
| Zásadní změna | Zásadní |  
  
## <a name="cause"></a>příčina  
 Veřejná nebo chráněná metoda veřejného typu přepsání metody nebo implementuje rozhraní a nemá stejný [požadavky propojení](http://msdn.microsoft.com/library/a33fd5f9-2de9-4653-a4f0-d9df25082c4d) jako rozhraní nebo virtuální metody.  
  
## <a name="rule-description"></a>Popis pravidla  
 Toto pravidlo přiřazuje metodu své základní metodě, kterou je buď rozhraní, nebo virtuální metoda jiného typu, a poté v obou metodách srovnává požadavky propojení. Porušení bude nahlášena, pokud metodu nebo metodu základní má požadavku propojení a druhá ne.  
  
 Pokud je toto pravidlo porušeno, volající obejít požadavek propojení pouhým voláním nezabezpečené metody.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, použijte stejný požadavek propojení toto metody nebo implementaci. Pokud to není možné, označte metodu se požadavek na úplné nebo úplně odeberte atribut.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje různé porušení tohoto pravidla.  
  
 [!code-csharp[FxCop.Security.OverridesAndSecurity#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.OverridesAndSecurity/cs/FxCop.Security.OverridesAndSecurity.cs#1)]  
  
## <a name="see-also"></a>Viz také  
 [Pokyny pro zabezpečené kódování](http://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177)   
 [Požadavky propojení](http://msdn.microsoft.com/library/a33fd5f9-2de9-4653-a4f0-d9df25082c4d)



