---
title: 'CA2202: Neuvolňujte objekty několikrát'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2202
- Do not dispose objects multiple times
- DoNotDisposeObjectsMultipleTimes
helpviewer_keywords:
- CA2202
ms.assetid: fa85349a-cf1e-42c8-a86b-eacae1f8bd96
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7c7eb35e556e8edd6e840f2fbd6701e182895706
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31920146"
---
# <a name="ca2202-do-not-dispose-objects-multiple-times"></a>CA2202: Neuvolňujte objekty několikrát
|||
|-|-|
|TypeName|DoNotDisposeObjectsMultipleTimes|
|CheckId|CA2202|
|Kategorie|Microsoft.Usage|
|Narušující změna|Bez ukončování řádků|

## <a name="cause"></a>příčina
 Implementace metody obsahuje cesty kódu, které by mohly způsobit několik volání <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> nebo Dispose ekvivalentní, jako je například metoda Close() na některé typy na stejný objekt.

## <a name="rule-description"></a>Popis pravidla
 A správně implementovat <xref:System.IDisposable.Dispose%2A> metodu lze volat vícekrát bez způsobení výjimky. To však není zaručena a aby nedošlo ke generování <xref:System.ObjectDisposedException?displayProperty=fullName> by neměl volání <xref:System.IDisposable.Dispose%2A> více než jednou na objekt.

## <a name="related-rules"></a>Související pravidla
 [CA2000: Uvolňujte objekty před ztrátou oboru](../code-quality/ca2000-dispose-objects-before-losing-scope.md)

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, změňte implementaci proto to bez ohledu na to kódová cesta, <xref:System.IDisposable.Dispose%2A> nazývá jenom jednou pro objekt.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo. I když <xref:System.IDisposable.Dispose%2A> pro objekt je znám být možné bezpečně volat vícekrát, může v budoucnu změnit implementace.

## <a name="example"></a>Příklad
 Vnořené `using` příkazy (`Using` v jazyce Visual Basic) může způsobit porušení CA2202 upozornění. Pokud IDisposable prostředku vnořené vnitřní `using` příkaz obsahuje prostředek vnějšího `using` příkaz, `Dispose` metoda vnořeného prostředku uvolní obsaženého zdroje. Pokud k této situaci dochází, `Dispose` metoda vnějšího `using` příkaz pokusí dispose jeho prostředků pro ještě jednou.

 V následujícím příkladu <xref:System.IO.Stream> objektu, který je vytvořen v vnější pomocí příkazu vydání na konci vnitřní pomocí příkazu v metodu Dispose <xref:System.IO.StreamWriter> objekt, který obsahuje `stream` objektu. Na konci vnější `using` příkaz, `stream` uvolnění objektu ještě jednou. Druhá verze je porušením CA2202.

```
using (Stream stream = new FileStream("file.txt", FileMode.OpenOrCreate))
{
    using (StreamWriter writer = new StreamWriter(stream))
    {
        // Use the writer object...
    }
}

```

## <a name="example"></a>Příklad
 Chcete-li vyřešit tento problém, použijte `try` / `finally` bloku místo vnější `using` příkaz. V `finally` blokovat, ujistěte se, že `stream` prostředek není null.

```
Stream stream = null;
try
{
    stream = new FileStream("file.txt", FileMode.OpenOrCreate);
    using (StreamWriter writer = new StreamWriter(stream))
    {
        stream = null;
        // Use the writer object...
    }
}
finally
{
    if(stream != null)
        stream.Dispose();
}

```

## <a name="see-also"></a>Viz také
 <xref:System.IDisposable?displayProperty=fullName> [Dispose – vzor](/dotnet/standard/design-guidelines/dispose-pattern)