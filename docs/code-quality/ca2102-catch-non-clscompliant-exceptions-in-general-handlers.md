---
title: "CA2102: Zachycujte výjimky bez CLSCompliant v obecné obslužné rutině | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2102
- CatchNonClsCompliantExceptionsInGeneralHandlers
helpviewer_keywords:
- CA2102
ms.assetid: bf2df68f-d386-4379-ad9e-930a2c2e930d
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 17238e140f8672e9d2d5a67594eb26b415c0b8d8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca2102-catch-non-clscompliant-exceptions-in-general-handlers"></a>CA2102: Zachycujte výjimky bez CLSCompliant v obecné obslužné rutině
|||  
|-|-|  
|TypeName|CatchNonClsCompliantExceptionsInGeneralHandlers|  
|CheckId|CA2102|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Člen v sestavení, který není označen atributem <xref:System.Runtime.CompilerServices.RuntimeCompatibilityAttribute> nebo je označena `RuntimeCompatibility(WrapNonExceptionThrows = false)` obsahuje blok catch, která zpracovává <xref:System.Exception?displayProperty=fullName> a neobsahuje bloku okamžitě následující obecné catch. Toto pravidlo ignoruje [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] sestavení.  
  
## <a name="rule-description"></a>Popis pravidla  
 Blok catch, která zpracovává <xref:System.Exception> zachytí všechny výjimky kompatibilní specifikace CLS (Common Language). Nezachytí však kompatibilní výjimky specifikací CLS. Non-specifikací CLS kompatibilní výjimky může být vyvolána z nativního kódu nebo ze spravovaného kódu, který byl vygenerován Microsoft mezilehlé jazyk MSIL Assembler. Všimněte si, že jazyka C# a [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] kompilátory neumožňují bez podpory CLS kompatibilní výjimky vyvolání a [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] nezachytí výjimky kompatibilní-specifikací CLS. Pokud je záměrem bloku catch – zpracování všech výjimek, použijte následující syntaxi bloku catch Obecné.  
  
-   C#:`catch {}`  
  
-   C++: `catch(...) {}` nebo`catch(Object^) {}`  
  
 Kompatibilní výjimku neošetřené neodpovídající specifikaci CLS bude problém zabezpečení, když se odeberou dřív povolené oprávnění v bloku catch. Vzhledem k tomu, že nejsou kompatibilní s výjimky specifikací CLS zachyceny, může se zvýšenými oprávněními spustit škodlivý metodu, která předpisy výjimky v důsledku jiných specifikací CLS.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Pokud je cílem zachytit vše opravit porušení toto pravidlo výjimky, nahraďte nebo přidat bloku catch obecné nebo označit sestavení `RuntimeCompatibility(WrapNonExceptionThrows = true)`. Pokud odeberete oprávnění v bloku catch duplicitní funkce v obecné catch – blok. Pokud není cílem zpracování všech výjimek, nahraďte blok catch, která zpracovává <xref:System.Exception> s bloků catch, které zpracovávají typy konkrétních výjimek.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění na toto pravidlo, pokud blok try neobsahuje žádné příkazy, které mohou vytvořit kompatibilní výjimka specifikací CLS. Protože všechny nativní nebo spravovaný kód může vyvolat bez specifikací CLS kompatibilní výjimky, to vyžaduje znalost všechen kód, který lze spustit v všechny cesty kódu uvnitř bloku try. Všimněte si, že nejsou kompatibilní s výjimkami specifikací CLS vyvolané modul common language runtime.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje třídu MSIL, který vyhodí výjimku kompatibilní-specifikací CLS.  
  
```  
.assembly ThrowNonClsCompliantException {}  
.class public auto ansi beforefieldinit ThrowsExceptions  
{  
   .method public hidebysig static void  
         ThrowNonClsException() cil managed  
   {  
      .maxstack  1  
      IL_0000:  newobj     instance void [mscorlib]System.Object::.ctor()  
      IL_0005:  throw  
   }  
}  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje metodu, která obsahuje bloku catch obecné splňující toto pravidlo.  
  
 [!code-csharp[FxCop.Security.CatchNonClsCompliantException#1](../code-quality/codesnippet/CSharp/ca2102-catch-non-clscompliant-exceptions-in-general-handlers_1.cs)]  
  
 V předchozích příkladech zkompilujte následujícím způsobem.  
  
```  
ilasm /dll ThrowNonClsCompliantException.il  
csc /r:ThrowNonClsCompliantException.dll CatchNonClsCompliantException.cs  
```  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1031: Nezachycujte výjimky obecného typu](../code-quality/ca1031-do-not-catch-general-exception-types.md)  
  
## <a name="see-also"></a>Viz také  
 [Výjimky a jejich zpracování](/dotnet/csharp/programming-guide/exceptions/exceptions-and-exception-handling)   
 [Ilasm.exe (IL assembleru)](/dotnet/framework/tools/ilasm-exe-il-assembler)   
 [Jazyková nezávislost a jazykově nezávislé komponenty](/dotnet/standard/language-independence-and-language-independent-components)