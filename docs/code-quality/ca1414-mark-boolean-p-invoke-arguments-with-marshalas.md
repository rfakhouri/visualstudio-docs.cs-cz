---
title: "CA1414: Označte logické vyvolání P pomocí MarshalAs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1414
- MarkBooleanPInvokeArgumentsWithMarshalAs
helpviewer_keywords:
- CA1414
- MarkBooleanPInvokeArgumentsWithMarshalAs
ms.assetid: c0c84cf5-7701-4897-9114-66fc4b895699
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3ce70291bd59ef3211c9fea871c8155f1a3e7fed
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca1414-mark-boolean-pinvoke-arguments-with-marshalas"></a>CA1414: Označte logické hodnoty volání nespravovaného kódu pomocí MarshalAs
|||  
|-|-|  
|TypeName|MarkBooleanPInvokeArgumentsWithMarshalAs|  
|CheckId|CA1414|  
|Kategorie|Microsoft.Interoperability|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Platformu invoke – metoda obsahuje prohlášení <xref:System.Boolean?displayProperty=fullName> hodnotu parametru nebo return ale <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=fullName> není použit atribut na hodnotu parametru nebo return.  
  
## <a name="rule-description"></a>Popis pravidla  
 Platforma volání nespravovaného kódu metoda přístupů a je definován pomocí `Declare` – klíčové slovo v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] nebo <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>. <xref:System.Runtime.InteropServices.MarshalAsAttribute>Určuje chování zařazování, který se používá pro převod typů data mezi spravovanými a nespravovanými kódu. Mnoho jednoduché datové typy, jako například <xref:System.Byte?displayProperty=fullName> a <xref:System.Int32?displayProperty=fullName>, mít jeden reprezentace v nespravovaném kódu a nevyžadují specifikaci jejich chování zařazování; modul common language runtime automaticky poskytuje správné chování.  
  
 <xref:System.Boolean> Datový typ má více reprezentací v nespravovaném kódu. Když <xref:System.Runtime.InteropServices.MarshalAsAttribute> není určena, výchozí chování pro zařazování <xref:System.Boolean> datový typ je <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>. Toto je 32bitové celé číslo, které není vhodná za všech okolností. Logická reprezentace vyžadovanou nespravované metoda by měla určit a odpovídá na příslušné <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>. UnmanagedType.Bool je typu Win32 BOOL, který je vždycky 4 bajtů. UnmanagedType.U1 má být použit pro C++ `bool` nebo jiné typy 1bajtový.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, použít <xref:System.Runtime.InteropServices.MarshalAsAttribute> k <xref:System.Boolean> hodnotu parametru nebo return. Nastavte hodnotu atributu na příslušné <xref:System.Runtime.InteropServices.UnmanagedType>.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo. I když výchozí chování zařazování je vhodné, kód zachovaný snadněji při chování je explicitně určena.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje dva platformy vyvolání metody, které jsou označené odpovídající <xref:System.Runtime.InteropServices.MarshalAsAttribute> atributy.  
  
 [!code-csharp[FxCop.Interoperability.BoolMarshalAs#1](../code-quality/codesnippet/CSharp/ca1414-mark-boolean-p-invoke-arguments-with-marshalas_1.cs)]
 [!code-vb[FxCop.Interoperability.BoolMarshalAs#1](../code-quality/codesnippet/VisualBasic/ca1414-mark-boolean-p-invoke-arguments-with-marshalas_1.vb)]
 [!code-cpp[FxCop.Interoperability.BoolMarshalAs#1](../code-quality/codesnippet/CPP/ca1414-mark-boolean-p-invoke-arguments-with-marshalas_1.cpp)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1901: Deklarace volání by měla být přenosná](../code-quality/ca1901-p-invoke-declarations-should-be-portable.md)  
  
 [CA2101: Určete zařazování pro argumenty řetězce P/Invoke](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>   
 [Spolupráce s nespravovaným kódem](/dotnet/framework/interop/index)