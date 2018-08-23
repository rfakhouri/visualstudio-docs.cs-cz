---
title: 'CA1411: Metody registrace modelu COM by neměly být viditelné | Dokumentace Microsoftu'
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
- CA1411
- ComRegistrationMethodsShouldNotBeVisible
helpviewer_keywords:
- ComRegistrationMethodsShouldNotBeVisible
- CA1411
ms.assetid: a59f96f1-1f38-4596-b656-947df5c55311
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 40fa3f3a99df840dc38a0177a6a3dafa81a31722
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632221"
---
# <a name="ca1411-com-registration-methods-should-not-be-visible"></a>CA1411: Metody registrace modelu COM by neměly být viditelné
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1411: metody registrace modelu COM by neměly být viditelné](https://docs.microsoft.com/visualstudio/code-quality/ca1411-com-registration-methods-should-not-be-visible).  
  
TypeName | ComRegistrationMethodsShouldNotBeVisible |  
| ID kontroly | CA1411 |  
| Kategorie | Microsoft.Interoperability|  
| Zásadní změna | Zásadní |  
  
## <a name="cause"></a>příčina  
 Metoda, která je označena <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> nebo <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName> atribut je externě viditelná.  
  
## <a name="rule-description"></a>Popis pravidla  
 Když sestavení registrováno s modelu COM (Component Object), položky se přidají do registru pro každý typ viditelný modulem COM v sestavení. Metody, které jsou označené <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute> a <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute> atributy jsou volány během procesu registrace a zrušení registrace, ke spuštění uživatelský kód, který je specifický pro registraci nebo zrušení registrace z těchto typů. Tento kód by neměla být volána mimo tyto procesy.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, změňte přístupnost metody, která `private` nebo `internal` (`Friend` v [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]).  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje dvě metody, které se pravidlo porušují.  
  
 [!code-csharp[FxCop.Interoperability.ComRegistration2#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.ComRegistration2/cs/FxCop.Interoperability.ComRegistration2.cs#1)]
 [!code-vb[FxCop.Interoperability.ComRegistration2#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.ComRegistration2/vb/FxCop.Interoperability.ComRegistration2.vb#1)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1410: Metody registrace modelu COM by si měly odpovídat](../code-quality/ca1410-com-registration-methods-should-be-matched.md)  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Runtime.InteropServices.RegistrationServices?displayProperty=fullName>   
 [Registrování sestav pomocí modelu COM](http://msdn.microsoft.com/library/87925795-a3ae-4833-b138-125413478551)   
 [Regasm.exe (nástroj registrace sestavení)](http://msdn.microsoft.com/library/e190e342-36ef-4651-a0b4-0e8c2c0281cb)



