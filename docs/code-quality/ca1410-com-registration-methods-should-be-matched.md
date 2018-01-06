---
title: "CA1410: Metody registrace modelu COM by si měly odpovídat | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1410
- ComRegistrationMethodsShouldBeMatched
helpviewer_keywords:
- CA1410
- ComRegistrationMethodsShouldBeMatched
ms.assetid: f3b2e62d-fd66-4093-9f0c-dba01ad995fd
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 660524e4198a06eb6a7e3d627e28acaa721bf8c2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca1410-com-registration-methods-should-be-matched"></a>CA1410: Metody registrace modelu COM by si měly odpovídat
|||  
|-|-|  
|TypeName|ComRegistrationMethodsShouldBeMatched|  
|CheckId|CA1410|  
|Kategorie|Microsoft.Interoperability|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Typ deklaruje metodu, která je označena <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> atribut ale nedeklaruje metodu, která je označena <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName> atribut, nebo naopak.  
  
## <a name="rule-description"></a>Popis pravidla  
 U klientů modelu COM (Component Object) k vytvoření [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] typu, typ musí být nejprve registrována. Pokud je k dispozici, metoda, která je označena <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute> atribut je volána v průběhu procesu registrace ke spuštění kódu zadaného uživatelem. Odpovídající metodu, která je označena <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute> atribut je volána v průběhu procesu zrušení registrace reverse operace metody registrace.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, přidejte metodu odpovídající registraci nebo zrušení registrace.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typ, který porušuje pravidlo. Komentovaný kód ukazuje opravu pro porušení zásady.  
  
 [!code-csharp[FxCop.Interoperability.ComRegistration#1](../code-quality/codesnippet/CSharp/ca1410-com-registration-methods-should-be-matched_1.cs)]
 [!code-vb[FxCop.Interoperability.ComRegistration#1](../code-quality/codesnippet/VisualBasic/ca1410-com-registration-methods-should-be-matched_1.vb)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1411: Metody registrace modelu COM by neměly být viditelné](../code-quality/ca1411-com-registration-methods-should-not-be-visible.md)  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Runtime.InteropServices.RegistrationServices?displayProperty=fullName>   
 [Registrace sestavení modelu COM](/dotnet/framework/interop/registering-assemblies-with-com)   
 [Regasm.exe (nástroj registrace sestavení)](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)