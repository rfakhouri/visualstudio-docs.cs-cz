---
title: 'Ca1401: volání nespravovaných kódů. vyvolá P by neměly být viditelné | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- PInvokesShouldNotBeVisible
- CA1401
helpviewer_keywords:
- CA1401
- PInvokesShouldNotBeVisible
ms.assetid: 0f4d96c1-f9de-414e-b223-4dc7f691bee3
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 1b811f57a3939a026152e70babbf263244aed056
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49211691"
---
# <a name="ca1401-pinvokes-should-not-be-visible"></a>CA1401: Volání nespravovaných kódů by neměla být viditelná
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]
|||
|-|-|
|TypeName|PInvokesShouldNotBeVisible|
|CheckId|CA1401|
|Kategorie|Microsoft.Interoperability|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Veřejná nebo chráněná metoda veřejného typu má <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> atribut (také implementováno pomocí `Declare` – klíčové slovo v [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]).

## <a name="rule-description"></a>Popis pravidla
 Metody, které jsou označené <xref:System.Runtime.InteropServices.DllImportAttribute> atribut (nebo metody, které jsou definovány pomocí `Declare` – klíčové slovo v [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) používat platformu vyvolání služby pro přístup k nespravovanému kódu. Tyto metody by neměly být vystaveny. Udržováním tyto metody soukromý nebo interní, ujistěte se, že knihovny nelze použít k narušení zabezpečení tím, že volající přístup k nespravované rozhraní API, která nelze volat v opačném případě.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, změňte úroveň přístupu metody.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad deklaruje metodu, která poruší toto pravidlo.

 [!code-csharp[FxCop.Interoperability.DllImports#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.DllImports/cs/FxCop.Interoperability.DllImports.cs#1)]
 [!code-vb[FxCop.Interoperability.DllImports#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.DllImports/vb/FxCop.Interoperability.DllImports.vb#1)]



