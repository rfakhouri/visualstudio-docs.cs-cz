---
title: 'CA1414: Označte logické nespravovaného kódu pomocí MarshalAs | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1414
- MarkBooleanPInvokeArgumentsWithMarshalAs
helpviewer_keywords:
- CA1414
- MarkBooleanPInvokeArgumentsWithMarshalAs
ms.assetid: c0c84cf5-7701-4897-9114-66fc4b895699
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 8df0404657b6740c27544292dc101a6030a6563f
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65691920"
---
# <a name="ca1414-mark-boolean-pinvoke-arguments-with-marshalas"></a>CA1414: Označte logické argumenty volání nespravovaného kódu pomocí MarshalAs
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|MarkBooleanPInvokeArgumentsWithMarshalAs|
|CheckId|CA1414|
|Kategorie|Microsoft.Interoperability|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Vyvolání platformy – metoda obsahuje prohlášení <xref:System.Boolean?displayProperty=fullName> parametr nebo návratovou hodnotu ale <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=fullName> atribut není použit parametr nebo návratovou hodnotu.

## <a name="rule-description"></a>Popis pravidla
 Platforma vyvolat metodu přístupy do nespravovaného kódu a je definován pomocí `Declare` – klíčové slovo v [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] nebo <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>. <xref:System.Runtime.InteropServices.MarshalAsAttribute> Určuje chování zařazování, který se používá k převodu datových typů mezi spravovaným a nespravovaným kódem. Mnoho jednoduché datové typy, jako <xref:System.Byte?displayProperty=fullName> a <xref:System.Int32?displayProperty=fullName>, mají jednotné vyjádření v nespravovaném kódu a nevyžadují specifikace jejich chování zařazování, modul common language runtime automaticky poskytuje správné chování.

 <xref:System.Boolean> Datový typ má více reprezentací v nespravovaném kódu. Když <xref:System.Runtime.InteropServices.MarshalAsAttribute> není zadán, výchozí chování pro zařazování <xref:System.Boolean> datový typ je <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>. Toto je 32bitové celé číslo, které není vhodné za všech okolností. Logickou reprezentaci, který vyžaduje metodu nespravované by měl určit a spárují s odpovídající <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>. UnmanagedType.Bool je typ Win32 BOOL, který je vždycky 4 bajty. UnmanagedType.U1 byste měli použít pro C++ `bool` nebo jiných typů 1 bajt. Další informace najdete v tématu [výchozí zařazování pro logické typy](https://msdn.microsoft.com/d4c00537-70f7-4ca6-8197-bfc1ec037ff9).

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, použijte <xref:System.Runtime.InteropServices.MarshalAsAttribute> k <xref:System.Boolean> parametr nebo návratovou hodnotu. Nastavit hodnotu atributu na příslušné <xref:System.Runtime.InteropServices.UnmanagedType>.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo. I v případě, že výchozí chování zařazování je vhodné, kód je snadněji nepoužije, když je chování explicitně zadán.

## <a name="example"></a>Příklad
 Následující příklad ukazuje dva platformu vyvolání metody, které jsou označené odpovídající <xref:System.Runtime.InteropServices.MarshalAsAttribute> atributy.

 [!code-cpp[FxCop.Interoperability.BoolMarshalAs#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.BoolMarshalAs/cpp/FxCop.Interoperability.BoolMarshalAs.cpp#1)]
 [!code-csharp[FxCop.Interoperability.BoolMarshalAs#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.BoolMarshalAs/cs/FxCop.Interoperability.BoolMarshalAs.cs#1)]
 [!code-vb[FxCop.Interoperability.BoolMarshalAs#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.BoolMarshalAs/vb/FxCop.Interoperability.BoolMarshalAs.vb#1)]

## <a name="related-rules"></a>Související pravidla
 [CA1901: Deklarace volání nespravovaného kódu by měla být přenosná](../code-quality/ca1901-p-invoke-declarations-should-be-portable.md)

 [CA2101: Určete zařazování pro argumenty řetězce volání nespravovaného](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)

## <a name="see-also"></a>Viz také
 <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName> [Výchozí zařazování pro logické typy](https://msdn.microsoft.com/d4c00537-70f7-4ca6-8197-bfc1ec037ff9) [spolupráce pomocí nespravovaného kódu](https://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)
