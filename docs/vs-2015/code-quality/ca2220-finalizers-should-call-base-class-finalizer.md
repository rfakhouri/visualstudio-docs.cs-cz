---
title: 'CA2220: Finalizační metody by měly volat finalizační metodu základní třídy | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2220
- FinalizersShouldCallBaseClassFinalizer
helpviewer_keywords:
- CA2220
- FinalizersShouldCallBaseClassFinalizer
ms.assetid: 48329f42-170d-45ee-a381-e33f55a240c5
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 432d973a64c7ee7f4264841e2a1277f66c9259da
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54755794"
---
# <a name="ca2220-finalizers-should-call-base-class-finalizer"></a>CA2220: Finalizační metody by měly volat finalizační metodu základní třídy
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|FinalizersShouldCallBaseClassFinalizer|
|CheckId|CA2220|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina
 Typ, který přepíše <xref:System.Object.Finalize%2A?displayProperty=fullName> nevolá <xref:System.Object.Finalize%2A> metoda v její základní třídě.

## <a name="rule-description"></a>Popis pravidla
 Finalizační metoda musí být šířena přes hierarchii dědičnosti. Aby toto bylo zajištěno, musí typy zavolat své základní třídy <xref:System.Object.Finalize%2A> metodu z v rámci své vlastní <xref:System.Object.Finalize%2A> metody. Kompilátor jazyka C# automaticky přidá volání finalizační metodu třídy base.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, zavolejte základní typ <xref:System.Object.Finalize%2A> metodu z vašeho <xref:System.Object.Finalize%2A> metody.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo. Některé kompilátory, které se zaměřují na modul common language runtime vložit volání do finalizační metodu základního typu do Microsoft intermediate language (MSIL). Pokud upozornění toto pravidlo se použije v hlášení, kompilátor nevkládá volání a je třeba přidat ji do vašeho kódu.

## <a name="example"></a>Příklad
 Následující příklad jazyka Visual Basic ukazuje typ `TypeB` , která správně volá <xref:System.Object.Finalize%2A> metoda v její základní třídě.

 [!code-vb[FxCop.Usage.IDisposableBaseCalled#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.IDisposableBaseCalled/vb/FxCop.Usage.IDisposableBaseCalled.vb#1)]

## <a name="see-also"></a>Viz také
 [Vzor pro metodu Dispose](http://msdn.microsoft.com/library/31a6c13b-d6a2-492b-9a9f-e5238c983bcb)
