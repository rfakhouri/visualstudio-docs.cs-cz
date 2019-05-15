---
title: 'CA1415: Deklarujte správně | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1415
- DeclarePInvokesCorrectly
helpviewer_keywords:
- CA1415
- DeclarePInvokesCorrectly
ms.assetid: 42a90796-0264-4460-bf97-2fb4a093dfdc
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 57482b720b1a7801fc75e06a5eb5d05d3b1a1417
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65691850"
---
# <a name="ca1415-declare-pinvokes-correctly"></a>CA1415: Deklarujte správně volání nespravovaných kódů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DeclarePInvokesCorrectly|
|CheckId|CA1415|
|Kategorie|Microsoft.Interoperability|
|Narušující změna|Bez konce – Pokud P/Invoke, který deklaruje parametr je nemohou vidět mimo sestavení. Rozdělení - P/Invoke, který deklaruje parametr viditelné mimo sestavení.|

## <a name="cause"></a>Příčina
 Metoda vyvolání platformy je deklarován nesprávně.

## <a name="rule-description"></a>Popis pravidla
 Platforma vyvolat metodu přístupy do nespravovaného kódu a je definován pomocí `Declare` – klíčové slovo v [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] nebo <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>. V současné době toto pravidlo hledá deklarace metod, které se zaměřují na funkce Win32, které mají ukazatel na parametr struktury OVERLAPPED vyvolání platformy a odpovídající spravovaný parametr není ukazatel <xref:System.Threading.NativeOverlapped?displayProperty=fullName> struktury.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, deklarujte správně platformu vyvolání metody.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje metody, které porušují pravidlo a splňovat pravidla vyvolání platformy.

 [!code-csharp[FxCop.Interoperability.DeclarePInvokes#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.DeclarePInvokes/cs/FxCop.Interoperability.DeclarePInvokes.cs#1)]

## <a name="see-also"></a>Viz také
 [Spolupráce s nespravovaným kódem](https://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)
