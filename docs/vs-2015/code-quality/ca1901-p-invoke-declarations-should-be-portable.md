---
title: 'CA1901: Deklarace volání by měla být přenosná | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1901
- PInvokeDeclarationsShouldBePortable
helpviewer_keywords:
- CA1901
- PInvokeDeclarationsShouldBePortable
ms.assetid: 90361812-55ca-47f7-bce9-b8775d3b8803
caps.latest.revision: 25
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 685d576594a442f4cac510b5e29000ca0b6d3eb3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42677834"
---
# <a name="ca1901-pinvoke-declarations-should-be-portable"></a>CA1901: Deklarace volání nespravovaného kódu by měla být přenosná
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1901: deklarace volání by měla být přenosná](https://docs.microsoft.com/visualstudio/code-quality/ca1901-p-invoke-declarations-should-be-portable).  
  
TypeName | PInvokeDeclarationsShouldBePortable |  
| ID kontroly | CA1901 |  
| Kategorie | Microsoft.Portability|  
| Zásadní změna | Rozdělení - P/Invoke je viditelná mimo sestavení. Pevné – Pokud P/Invoke není viditelný mimo sestavení. |  
  
## <a name="cause"></a>příčina  
 Toto pravidlo vyhodnotí velikost každého parametru a vrácené hodnoty deklarace P/Invoke a ověří správnost jejich velikost, při zařazení na nespravovaný kód v 32bitové a 64bitové platformy. Nejběžnější porušení tohoto pravidla je předat celé číslo pevnou velikostí, ve kterém jsou vyžadována proměnná závislého na platformě, velikosti ukazatele.  
  
## <a name="rule-description"></a>Popis pravidla  
 Jednu z následujících scénářů poruší toto pravidlo vyvolá:  
  
-   Návratová hodnota nebo parametr je zadán jako celé číslo pevnou velikostí při by měla být zadána jako `IntPtr`.  
  
-   Návratová hodnota nebo parametr je zadán jako `IntPtr` kdy by měla být zadána jako celé číslo pevnou velikostí.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Je-li opravit toto porušení pomocí `IntPtr` nebo `UIntPtr` k reprezentaci obslužné rutiny místo `Int32` nebo `UInt32`.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Neměli potlačení tohoto upozornění.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje porušení tohoto pravidla.  
  
```csharp  
internal class NativeMethods  
{  
    [DllImport("shell32.dll", CharSet=CharSet.Auto)]  
    internal static extern IntPtr ExtractIcon(IntPtr hInst,   
        string lpszExeFileName, IntPtr nIconIndex);  
}  
```  
  
 V tomto příkladu `nIconIndex` parametr je deklarován jako `IntPtr`, což je 4 bajty široké na 32bitové platformě a 8 bajtů na platformě 64 bitů široké. V nespravované deklarace, který následuje, vidíte, že `nIconIndex` je 4 bajty celé číslo bez znaménka na všech platformách.  
  
```csharp  
HICON ExtractIcon(HINSTANCE hInst, LPCTSTR lpszExeFileName,   
    UINT nIconIndex);  
```  
  
## <a name="example"></a>Příklad  
 Chcete-li vyřešit porušení zásad, změňte deklaraci takto:  
  
```csharp  
internal class NativeMethods{  
    [DllImport("shell32.dll", CharSet=CharSet.Auto)]   
    internal static extern IntPtr ExtractIcon(IntPtr hInst,   
        string lpszExeFileName, uint nIconIndex);  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Upozornění přenositelnosti](../code-quality/portability-warnings.md)



