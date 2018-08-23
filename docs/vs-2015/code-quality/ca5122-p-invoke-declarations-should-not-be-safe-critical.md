---
title: Deklarace CA5122 nespravovaného kódu nesmí být bezpečné kritické | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2581a6d-2a0e-40c1-b600-f5dc70909200
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: f6343cd7a61c0040aec274908095916ed20a37ae
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42678779"
---
# <a name="ca5122-pinvoke-declarations-should-not-be-safe-critical"></a>CA5122: Deklarace volání nespravovaného kódu nesmí být kritické pro zabezpečení
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [deklarace CA5122 nespravovaného kódu nesmí být bezpečné kritické](https://docs.microsoft.com/visualstudio/code-quality/ca5122-p-invoke-declarations-should-not-be-safe-critical).  
  
TypeName | PInvokesShouldNotBeSafeCriticalFxCopRule |  
| ID kontroly | CA5122 |  
| Kategorie | Microsoft.Security|  
| Zásadní změna | Zásadní |  
  
## <a name="cause"></a>příčina  
 Deklarace P/Invoke byla označena atributem <xref:System.Security.SecuritySafeCriticalAttribute>:  
  
```csharp  
[assembly: AllowPartiallyTrustedCallers]  
  
// ...  
public class C  
{  
    [SecuritySafeCritical]  
    [DllImport("kernel32.dll")]  
    public static extern bool Beep(int frequency, int duration); // CA5122 – safe critical p/invoke  
   }  
  
```  
  
 V tomto příkladu `C.Beep(...)` byl označen jako zabezpečení bezpečně kritická metoda.  
  
## <a name="rule-description"></a>Popis pravidla  
 Metody jsou při provádění operace citlivé na zabezpečení označeny jako SecuritySafeCritical, ale lze je také bezpečně použít transparentním kódem. Jedním ze základních pravidel modelu transparentnosti zabezpečení je, že transparentní kód nikdy nesmí přímo volat nativní kód prostřednictvím deklarace P/Invoke. Proto označení P/Invoke jako bezpečně kritické z hlediska zabezpečení neumožní transparentnímu kódu vyvolat je a je zavádějící pro analýzu zabezpečení.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Aby byla deklarace P/Invoke zpřístupněna pro transparentní kód, vystavte pro něj z hlediska zabezpečení bezpečně kritickou obalující metodu.  
  
```csharp  
[assembly: AllowPartiallyTrustedCallers  
  
class C  
{  
   [SecurityCritical]  
   [DllImport(“kernel32.dll”, EntryPoint=”Beep”)]  
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



