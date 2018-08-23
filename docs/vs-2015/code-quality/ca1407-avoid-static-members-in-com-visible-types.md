---
title: 'CA1407: Vyhněte se statickým členům ve viditelných typech modelu COM | Dokumentace Microsoftu'
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
- CA1407
- AvoidStaticMembersInComVisibleTypes
helpviewer_keywords:
- CA1407
- AvoidStaticMembersInComVisibleTypes
ms.assetid: bebd0776-ad04-453c-bca8-8c124c2d7840
caps.latest.revision: 25
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: b07afe3138ba7b775ad82355e76c664f68fb91ce
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42678787"
---
# <a name="ca1407-avoid-static-members-in-com-visible-types"></a>CA1407: Vyhněte se statickým členům ve viditelných typech modelu COM
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1407: Vyhněte se statickým členům ve viditelných typech modelu COM](https://docs.microsoft.com/visualstudio/code-quality/ca1407-avoid-static-members-in-com-visible-types).  
  
TypeName | AvoidStaticMembersInComVisibleTypes |  
| ID kontroly | CA1407 |  
| Kategorie | Microsoft.Interoperability|  
| Zásadní změna | Ukončování bez |  
  
## <a name="cause"></a>příčina  
 Obsahuje typ, který je označen jako viditelný pro Model COM (Component Object) `public``static` metoda.  
  
## <a name="rule-description"></a>Popis pravidla  
 Model COM nepodporuje `static` metody.  
  
 Toto pravidlo se ignoruje vlastnost a přístupových objektů událostí, přetížení metody nebo metody, které jsou označeny pomocí operátoru <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> atribut nebo <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName> atribut.  
  
 Ve výchozím nastavení, jsou následující viditelné modelu COM: sestavení, veřejné typy, členy veřejné instance ve veřejných typů a členů veřejných hodnotových typech.  
  
 Pro toto pravidlo na výskyt, úrovni sestavení <xref:System.Runtime.InteropServices.ComVisibleAttribute> musí být nastaveno na `false` a třída - <xref:System.Runtime.InteropServices.ComVisibleAttribute> musí být nastaveno na `true`, jak ukazuje následující kód.  
  
```csharp  
using System;  
using System.Runtime.InteropServices;   
  
[assembly: ComVisible(false)]   
namespace Samples  
{      
    [ComVisible(true)]  
    public class MyClass  
    {  
        public static void DoSomething()  
        {  
        }  
    }  
}  
```  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, změňte návrhu a použít metodu instance, která poskytuje stejné funkce jako `static` metody.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění tohoto pravidla, pokud klient modelu COM nevyžaduje přístup k funkci, která je poskytována `static` metody.  
  
## <a name="example-violation"></a>Příklad porušení  
  
### <a name="description"></a>Popis  
 Následující příklad ukazuje `static` metodu, která poruší toto pravidlo.  
  
### <a name="code"></a>Kód  
 [!code-csharp[FxCop.Interoperability.ComVisibleStaticMembersViolation#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.ComVisibleStaticMembersViolation/cs/FxCop.Interoperability.ComVisibleStaticMembersViolation.cs#1)]  
  
### <a name="comments"></a>Komentáře  
 V tomto příkladu **Book.FromPages** metodu nejde volat z modelu COM.  
  
## <a name="example-fix"></a>Oprava příkladu  
  
### <a name="description"></a>Popis  
 Chcete-li vyřešit porušení zásad v předchozím příkladu, můžete změnit metodu na metodu instance, ale, který nemá smysl v této instanci. Lepším řešením je výslovně `ComVisible(false)` metodě k němu vymazat s ostatními vývojáři, že metoda je nemohou vidět z modelu COM.  
  
 Následující příklad použije <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute> metody.  
  
### <a name="code"></a>Kód  
 [!code-csharp[FxCop.Interoperability.ComVisibleStaticMembersFixed#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.ComVisibleStaticMembersFixed/cs/FxCop.Interoperability.ComVisibleStaticMembersFixed.cs#1)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1017: Označte sestavení pomocí atributu ComVisibleAttribute](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)  
  
 [CA1406: Vyhněte se argumentům Int64 pro klienty jazyka Visual Basic 6](../code-quality/ca1406-avoid-int64-arguments-for-visual-basic-6-clients.md)  
  
 [CA1413: Vyhněte se neveřejným polím v hodnotách viditelných modulem COM](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)  
  
## <a name="see-also"></a>Viz také  
 [Spolupráce s nespravovaným kódem](http://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)



