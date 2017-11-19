---
title: "CA1032: Implementujte standardní konstruktory výjimky | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1032
- ImplementStandardExceptionConstructors
helpviewer_keywords:
- CA1032
- ImplementStandardExceptionConstructors
ms.assetid: a8623c56-273a-4c95-8d83-95911a042be7
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7300465ce9cef97cf322a7667e775852e22edb4e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1032-implement-standard-exception-constructors"></a>CA1032: Implementujte standardní konstruktory výjimky
|||  
|-|-|  
|TypeName|ImplementStandardExceptionConstructors|  
|CheckId|CA1032|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Typ rozšiřuje <xref:System.Exception?displayProperty=fullName> a nedeklaruje všechny požadované konstruktory.  
  
## <a name="rule-description"></a>Popis pravidla  
 Typy výjimek musí implementovat těchto konstruktorů:  
  
-   veřejné NewException()  
  
-   veřejné NewException(string)  
  
-   veřejné NewException (string, výjimka)  
  
-   chráněný nebo privátní NewException (položku SerializationInfo, StreamingContext)  
  
 Není-li dodána úplná sada konstruktorů, může být obtížné správně ošetřit výjimky. Například konstruktor, který má podpis `NewException(string, Exception)` se používá k vytvoření výjimky, které jsou způsobeny další výjimky. Bez tento konstruktor nemůže vytvořit a výjimku instanci vaše vlastní výjimka, která obsahuje vnitřní výjimku (vnořené), který je co spravovaného kódu má provést v této situaci. První tři výjimka konstruktory jsou veřejné podle konvence. Čtvrtý konstruktor je chráněný v nezapečetěných třídy a privátní v zapečetěné třídy. Další informace najdete v tématu [CA2229: implementovat Serializační konstruktory](../code-quality/ca2229-implement-serialization-constructors.md)  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, přidejte chybějící konstruktory výjimku a ujistěte se, jestli mají nastavená správná usnadnění.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné při porušení je způsobena pomocí úrovní různý přístup pro veřejné konstruktory potlačit upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Následující příklad obsahuje typ výjimky, která porušuje toto pravidlo a typ výjimky, která je implementovaná správně.  
  
 [!code-csharp[FxCop.Design.ExceptionMultipleCtors#1](../code-quality/codesnippet/CSharp/ca1032-implement-standard-exception-constructors_1.cs)]