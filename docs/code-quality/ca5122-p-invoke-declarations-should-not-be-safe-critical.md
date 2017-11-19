---
title: "Vyvolání P CA5122 deklarace nesmí být kritické | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2581a6d-2a0e-40c1-b600-f5dc70909200
caps.latest.revision: "4"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4d012b1fc37090f382d73dab73f1c302207edd30
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca5122-pinvoke-declarations-should-not-be-safe-critical"></a>CA5122: Deklarace volání nespravovaného kódu nesmí být kritické pro zabezpečení
|||  
|-|-|  
|TypeName|PInvokesShouldNotBeSafeCriticalFxCopRule|  
|CheckId|CA5122|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Byla označena deklaraci P/Invoke <xref:System.Security.SecuritySafeCriticalAttribute>:  
  
```csharp  
[assembly: AllowPartiallyTrustedCallers]  
  
// ...  
public class C  
{  
    [SecuritySafeCritical]  
    [DllImport("kernel32.dll")]  
    public static extern bool Beep(int frequency, int duration); // CA5122 - safe critical p/invoke  
   }  
  
```  
  
 V tomto příkladu `C.Beep(...)` byly označeny jako bezpečné kritické metody zabezpečení.  
  
## <a name="rule-description"></a>Popis pravidla  
 Metody jsou při provádění operace citlivé na zabezpečení označeny jako SecuritySafeCritical, ale lze je také bezpečně použít transparentním kódem. Jedním ze základních pravidel modelu transparentnosti zabezpečení je, že transparentní kód nikdy nesmí přímo volat nativní kód prostřednictvím deklarace P/Invoke. Proto označení P/Invoke jako bezpečně kritické z hlediska zabezpečení neumožní transparentnímu kódu vyvolat je a je zavádějící pro analýzu zabezpečení.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Aby byla deklarace P/Invoke zpřístupněna pro transparentní kód, vystavte pro něj z hlediska zabezpečení bezpečně kritickou obalující metodu.  
  
```csharp  
[assembly: AllowPartiallyTrustedCallers  
  
class C  
{  
   [SecurityCritical]  
   [DllImport("kernel32.dll", EntryPoint="Beep")]  
   private static extern bool BeepPinvoke(int frequency, int duration); // Security Critical P/Invoke  
  
   [SecuritySafeCritical]  
   public static bool Beep(int frequency, int duration)  
   {  
      return BeepPInvoke(frequency, duration);  
   }  
}  
  
```  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.