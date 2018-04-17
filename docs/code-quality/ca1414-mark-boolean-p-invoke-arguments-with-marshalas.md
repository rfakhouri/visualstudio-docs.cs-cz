---
title: 'CA1414: Označte logické vyvolání P pomocí MarshalAs | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1414
- MarkBooleanPInvokeArgumentsWithMarshalAs
helpviewer_keywords:
- CA1414
- MarkBooleanPInvokeArgumentsWithMarshalAs
ms.assetid: c0c84cf5-7701-4897-9114-66fc4b895699
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 16e561e04444fba7200c00f299cc775978829100
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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
 Platforma volání nespravovaného kódu metoda přístupů a je definován pomocí `Declare` – klíčové slovo v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] nebo <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>. <xref:System.Runtime.InteropServices.MarshalAsAttribute> Určuje chování zařazování, který se používá pro převod typů data mezi spravovanými a nespravovanými kódu. Mnoho jednoduché datové typy, jako například <xref:System.Byte?displayProperty=fullName> a <xref:System.Int32?displayProperty=fullName>, mít jeden reprezentace v nespravovaném kódu a nevyžadují specifikaci jejich chování zařazování; modul common language runtime automaticky poskytuje správné chování.  
  
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