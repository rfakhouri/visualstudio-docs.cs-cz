---
title: "CA2202: Neodstraňovat objekty několikrát | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2202
- Do not dispose objects multiple times
- DoNotDisposeObjectsMultipleTimes
helpviewer_keywords: CA2202
ms.assetid: fa85349a-cf1e-42c8-a86b-eacae1f8bd96
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3439739626a81636020a6b645ba5820a59747f2d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
 <xref:System.IDisposable?displayProperty=fullName>   
 [Vzor pro metodu Dispose](/dotnet/standard/design-guidelines/dispose-pattern)