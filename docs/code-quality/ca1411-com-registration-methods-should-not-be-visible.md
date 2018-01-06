---
title: "CA1411: Metody registrace modelu COM by neměly být viditelné | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1411
- ComRegistrationMethodsShouldNotBeVisible
helpviewer_keywords:
- ComRegistrationMethodsShouldNotBeVisible
- CA1411
ms.assetid: a59f96f1-1f38-4596-b656-947df5c55311
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 43b1f340b62726edc33b3e7e05d52634c2a2595b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca1411-com-registration-methods-should-not-be-visible"></a>CA1411: Metody registrace modelu COM by neměly být viditelné
|||  
|-|-|  
|TypeName|ComRegistrationMethodsShouldNotBeVisible|  
|CheckId|CA1411|  
|Kategorie|Microsoft.Interoperability|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Metoda, která je označena <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> nebo <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName> atribut je viditelné.  
  
## <a name="rule-description"></a>Popis pravidla  
 Po sestavení registraci pomocí modelu COM (Component Object), jsou přidány položky registru pro jednotlivé COM – viditelné typy v sestavení. Metody, které jsou označené <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute> a <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute> atributy se nazývají během registrace a zrušení registrace procesů, ke spuštění uživatelského kódu, které jsou specifické pro registraci nebo zrušení registrace z těchto typů. Tento kód by neměla být volána mimo tyto procesy.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, změňte usnadnění metody `private` nebo `internal` (`Friend` v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]).  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje dvě metody, které porušují pravidlo.  
  
 [!code-csharp[FxCop.Interoperability.ComRegistration2#1](../code-quality/codesnippet/CSharp/ca1411-com-registration-methods-should-not-be-visible_1.cs)]
 [!code-vb[FxCop.Interoperability.ComRegistration2#1](../code-quality/codesnippet/VisualBasic/ca1411-com-registration-methods-should-not-be-visible_1.vb)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1410: Metody registrace modelu COM by si měly odpovídat](../code-quality/ca1410-com-registration-methods-should-be-matched.md)  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Runtime.InteropServices.RegistrationServices?displayProperty=fullName>   
 [Registrace sestavení modelu COM](/dotnet/framework/interop/registering-assemblies-with-com)   
 [Regasm.exe (nástroj registrace sestavení)](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)