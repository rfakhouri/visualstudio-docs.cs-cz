---
title: "CA1403: Typy automatického rozložení by neměly být viditelné modelu COM | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AutoLayoutTypesShouldNotBeComVisible
- CA1403
helpviewer_keywords:
- CA1403
- AutoLayoutTypesShouldNotBeComVisible
ms.assetid: a7007714-f9b4-4730-94e0-67d3dc68991f
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7da04d7ecda3e47239bd865812c6fbd05428ac09
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca1403-auto-layout-types-should-not-be-com-visible"></a>CA1403: Typy automatického rozložení by neměly být viditelné modelu COM
|||  
|-|-|  
|TypeName|AutoLayoutTypesShouldNotBeComVisible|  
|CheckId|CA1403|  
|Kategorie|Microsoft.Interoperability|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Typ hodnoty viditelné modelu COM (Component Object) je označena <xref:System.Runtime.InteropServices.StructLayoutAttribute?displayProperty=fullName> atribut nastaven na <xref:System.Runtime.InteropServices.LayoutKind?displayProperty=fullName>.  
  
## <a name="rule-description"></a>Popis pravidla  
 <xref:System.Runtime.InteropServices.LayoutKind>typy rozložení se spravují přes modul common language runtime. Rozložení těchto typů můžete volit mezi verze rozhraní .NET Framework, které by došlo k přerušení klientů modelu COM, které očekávají konkrétní rozložení. Všimněte si, že pokud <xref:System.Runtime.InteropServices.StructLayoutAttribute> atribut nezadá, jazyka C#, [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], a zadejte kompilátory C++ <xref:System.Runtime.InteropServices.LayoutKind> rozložení pro typy hodnot.  
  
 V opačném případě označena, všechny veřejné neobecné typy jsou viditelné pro COM; všechny neveřejní a obecné typy jsou neviditelná modelu COM. Však snížil počet falešných poplachů, toto pravidlo vyžaduje COM viditelnost typ, který má být explicitně uvedena; musí být označen obsahující sestavení <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> nastavena na `false` a typ musí být označené jako <xref:System.Runtime.InteropServices.ComVisibleAttribute> nastavena na `true`.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, změňte hodnotu <xref:System.Runtime.InteropServices.StructLayoutAttribute> atribut <xref:System.Runtime.InteropServices.LayoutKind> nebo <xref:System.Runtime.InteropServices.LayoutKind>, nebo nastavit typ neviditelné modelu COM.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typ, který porušuje pravidlo a typ, který splňuje pravidlo.  
  
 [!code-csharp[FxCop.Interoperability.AutoLayout#1](../code-quality/codesnippet/CSharp/ca1403-auto-layout-types-should-not-be-com-visible_1.cs)]
 [!code-vb[FxCop.Interoperability.AutoLayout#1](../code-quality/codesnippet/VisualBasic/ca1403-auto-layout-types-should-not-be-com-visible_1.vb)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1408: Nepoužívejte AutoDual ClassInterfaceType](../code-quality/ca1408-do-not-use-autodual-classinterfacetype.md)  
  
## <a name="see-also"></a>Viz také  
 [Kvalifikace typů .NET pro spolupráci](/dotnet/framework/interop/qualifying-net-types-for-interoperation)   
 [Spolupráce s nespravovaným kódem](/dotnet/framework/interop/index)