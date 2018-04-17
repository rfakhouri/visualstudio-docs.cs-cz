---
title: 'CA5350: Nepoužívejte slabé kryptografické algoritmy | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
ms.assetid: 4c51bb8a-fcfa-46aa-ab61-634be84c4a7a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 484b20a9c1d20cb0f18290de2277aa3feef26a8e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca5350-do-not-use-weak-cryptographic-algorithms"></a>CA5350: Nepoužívejte slabé kryptografické algoritmy
|||  
|-|-|  
|TypeName|DoNotUseWeakCryptographicAlgorithms|  
|CheckId|CA5350|  
|Kategorie|Microsoft.Cryptography|  
|Narušující změna|Bez ukončování řádků|  
  
> [!NOTE]
>  Toto upozornění byl naposledy aktualizován. listopadu 2015.  
  
## <a name="cause"></a>příčina  
 Algoritmy šifrování, jako <xref:System.Security.Cryptography.TripleDES> a algoritmy hash, jako <xref:System.Security.Cryptography.SHA1> a <xref:System.Security.Cryptography.RIPEMD160> se považují za slabé.  
  
 Tyto kryptografické algoritmy neposkytují tolik zajištění zabezpečení jako více moderní svými protějšky. Kryptografické algoritmy hash <xref:System.Security.Cryptography.SHA1> a <xref:System.Security.Cryptography.RIPEMD160> zadejte menší kolizí odporu než více moderní délkami algoritmů hash. Šifrovací algoritmus <xref:System.Security.Cryptography.TripleDES> poskytuje méně bity zabezpečení než více moderních šifrovacích algoritmů.  
  
## <a name="rule-description"></a>Popis pravidla  
 Slabé šifrování algoritmy hash funkce pro používají a dnes z mnoha důvodů, ale nepoužívejte zaručit důvěrnost dat, které chrání.  
  
 Toto pravidlo spustí, když se najde 3DES, algoritmů SHA1 nebo RIPEMD160 v editoru kódu a generuje upozornění pro uživatele.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Použijte kryptograficky silnější možnosti:  
  
-   Pro šifrování TripleDES, použijte <xref:System.Security.Cryptography.Aes> šifrování.  
  
-   Pro funkce hash SHA1 nebo RIPEMD160, použijte těch, které jsou v [SHA-2](https://msdn.microsoft.com/library/windows/desktop/aa382459.aspx) rodiny (například <xref:System.Security.Cryptography.SHA512>, <xref:System.Security.Cryptography.SHA384>, <xref:System.Security.Cryptography.SHA256>).  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Potlačíte upozornění na toto pravidlo, když úroveň ochrany, které jsou potřebné pro data nevyžaduje záruku zabezpečení.  
  
## <a name="pseudo-code-example"></a>Příklad pseudo kódu  
 Od verze době psaní tohoto textu znázorňuje následující ukázka kódu pseudo vzoru zjistil tímto pravidlem.  
  
### <a name="sha-1-hashing-violation"></a>Porušení hash SHA-1  
  
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
  
### <a name="ripemd160-br-br-hashing-violation"></a>RIPEMD160 <br /><br />Hash porušení  
  
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