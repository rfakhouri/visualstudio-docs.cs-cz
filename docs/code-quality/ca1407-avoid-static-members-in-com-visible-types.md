---
title: "CA1407: Vyhněte se statickým členům ve viditelných typech modelu COM | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1407
- AvoidStaticMembersInComVisibleTypes
helpviewer_keywords:
- CA1407
- AvoidStaticMembersInComVisibleTypes
ms.assetid: bebd0776-ad04-453c-bca8-8c124c2d7840
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 43240b8969026a8bbec18528230d3ca97bcb2236
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1407-avoid-static-members-in-com-visible-types"></a>CA1407: Vyhněte se statickým členům ve viditelných typech modelu COM
|||  
|-|-|  
|TypeName|AvoidStaticMembersInComVisibleTypes|  
|CheckId|CA1407|  
|Kategorie|Microsoft.Interoperability|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Typ, který je specificky označen jako viditelný na modelu COM (Component Object) obsahuje `public``static` metoda.  
  
## <a name="rule-description"></a>Popis pravidla  
 COM nepodporuje `static` metody.  
  
 Toto pravidlo ignoruje vlastnosti a přístupových objektů událostí, přetížení metody nebo metody, které jsou označeny buď pomocí operátoru <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> atribut nebo <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName> atribut.  
  
 Ve výchozím nastavení, jsou viditelné pro COM následující: sestavení, veřejné typy, členy veřejné instance ve veřejné typy a všichni členové typů veřejné hodnot.  
  
 Pro toto pravidlo proběhnout, úroveň sestavení <xref:System.Runtime.InteropServices.ComVisibleAttribute> musí být nastavena na `false` a třída - <xref:System.Runtime.InteropServices.ComVisibleAttribute> musí být nastavena na `true`, jak ukazuje následující kód.  
  
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
 Chcete-li opravit porušení toto pravidlo, změnit návrh používat metodu instance, která poskytuje stejné funkce jako `static` metoda.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění na toto pravidlo, pokud klient COM nevyžaduje přístup k funkcím, které poskytuje `static` metoda.  
  
## <a name="example-violation"></a>Příklad porušení  
  
### <a name="description"></a>Popis  
 Následující příklad ukazuje `static` metoda, která porušuje toto pravidlo.  
  
### <a name="code"></a>Kód  
 [!code-csharp[FxCop.Interoperability.ComVisibleStaticMembersViolation#1](../code-quality/codesnippet/CSharp/ca1407-avoid-static-members-in-com-visible-types_1.cs)]  
  
### <a name="comments"></a>Komentáře  
 V tomto příkladu **Book.FromPages** metodu nelze volat z modelu COM.  
  
## <a name="example-fix"></a>Příklad oprava  
  
### <a name="description"></a>Popis  
 V předchozím příkladu opravit porušení zásady, můžete změnit metodu na metodu instanci, ale které nemá smysl v této instanci. Lepší řešení je třeba explicitně použít `ComVisible(false)` metodu aby zrušte k jinými vývojáři, že metoda je nemohou vidět z modelu COM.  
  
 Následující příklad se týká <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute> metodě.  
  
### <a name="code"></a>Kód  
 [!code-csharp[FxCop.Interoperability.ComVisibleStaticMembersFixed#1](../code-quality/codesnippet/CSharp/ca1407-avoid-static-members-in-com-visible-types_2.cs)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1017: Označte sestavení pomocí atributu ComVisibleAttribute](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)  
  
 [CA1406: Vyhněte se argumentům Int64 pro klienty jazyka Visual Basic 6](../code-quality/ca1406-avoid-int64-arguments-for-visual-basic-6-clients.md)  
  
 [CA1413: Vyhněte se neveřejným polím v viditelných typech modelu COM](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)  
  
## <a name="see-also"></a>Viz také  
 [Spolupráce s nespravovaným kódem](/dotnet/framework/interop/index)