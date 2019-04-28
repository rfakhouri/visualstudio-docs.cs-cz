---
title: 'CA5350: Nepoužívejte slabé kryptografické algoritmy | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
ms.assetid: 4c51bb8a-fcfa-46aa-ab61-634be84c4a7a
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 004b09c471ea163a17391a8ad51abcc0aefee1ed
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63430713"
---
# <a name="ca5350-do-not-use-weak-cryptographic-algorithms"></a>CA5350: Nepoužívejte slabé kryptografické algoritmy
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotUseWeakCryptographicAlgorithms|  
|CheckId|CA5350|  
|Kategorie|Microsoft.Cryptography|  
|Narušující změna|Pevné|  
  
> [!NOTE]
> Toto upozornění byl naposledy aktualizován. listopadu 2015.  
  
## <a name="cause"></a>Příčina  
 Algoritmy šifrování, jako <xref:System.Security.Cryptography.TripleDES> a algoritmy hash jako <xref:System.Security.Cryptography.SHA1> a <xref:System.Security.Cryptography.RIPEMD160> jsou považovány za slabé.  
  
 Tyto kryptografické algoritmy se neposkytuje tolik zajištění zabezpečení jako Modernější protějšky. Kryptografické algoritmy hash <xref:System.Security.Cryptography.SHA1> a <xref:System.Security.Cryptography.RIPEMD160> zadejte méně kolizí odolnost než Modernější algoritmy hash. Šifrovací algoritmus <xref:System.Security.Cryptography.TripleDES> poskytuje méně bity zabezpečení než Modernější šifrovacích algoritmů.  
  
## <a name="rule-description"></a>Popis pravidla  
 Algoritmy slabé šifrování a hashovací funkce se dnes používají pro z několika důvodů, ale by neměly být použít k zajištění důvěrnosti údajů, které chrání.  
  
 Toto pravidlo aktivuje, když zjistí, 3DES, SHA1 nebo RIPEMD160 algoritmy v editoru kódu a vyvolá upozornění pro uživatele.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Použijte kryptograficky silnější možnosti:  
  
- Pro šifrování TripleDES, použijte <xref:System.Security.Cryptography.Aes> šifrování.  
  
- Pro funkce hash SHA1 nebo RIPEMD160, použijte těch, které jsou v [SHA-2](https://msdn.microsoft.com/library/windows/desktop/aa382459.aspx) řady (třeba <xref:System.Security.Cryptography.SHA512>, <xref:System.Security.Cryptography.SHA384>, <xref:System.Security.Cryptography.SHA256>).  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Potlačit upozornění tohoto pravidla, když úroveň ochrany, třeba dat nevyžaduje záruky zabezpečení.  
  
## <a name="pseudo-code-example"></a>Příklad pseudo kódu  
 V době době psaní tohoto textu znázorňuje následující ukázka kódu pseudo vzor, zjistí toto pravidlo.  
  
### <a name="sha-1-hashing-violation"></a>Porušení hashovací algoritmus SHA-1  
  
```  
using System.Security.Cryptography;   
...   
var hashAlg = SHA1.Create();  
  
```  
  
### <a name="solution"></a>Řešení  
  
```  
using System.Security.Cryptography;   
...   
var hashAlg = SHA256.Create();  
  
```  
  
### <a name="ripemd160-br-br-hashing-violation"></a>RIPEMD160 <br /><br />Hashování porušení  
  
```  
using System.Security.Cryptography;   
...   
var hashAlg = RIPEMD160Managed.Create();  
  
```  
  
### <a name="solution"></a>Řešení  
  
```  
using System.Security.Cryptography;   
...   
var hashAlg = SHA256.Create();  
  
```  
  
### <a name="tripledes-encryption-violation"></a>Porušení šifrování TripleDES  
  
```  
using System.Security.Cryptography;   
...    
using (TripleDES encAlg = TripleDES.Create())   
{   
  ...   
}  
```  
  
### <a name="solution"></a>Řešení  
  
```  
using System.Security.Cryptography;   
...   
using (AesManaged encAlg = new AesManaged())   
{   
  ...   
}  
```