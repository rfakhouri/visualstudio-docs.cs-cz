---
title: "CA5351 Nepoužívejte porušený kryptografické algoritmy | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 483f51b3-e186-4433-b48e-5ca24a9a9c94
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d23ca03e10476bba11a8f64c0626e0dd8aec5147
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca5351-do-not-use-broken-cryptographic-algorithms"></a>CA5351 Nepoužívejte porušený kryptografické algoritmy
|||  
|-|-|  
|TypeName|DoNotUseBrokenCryptographicAlgorithms|  
|CheckId|CA5351|  
|Kategorie|Microsoft.Cryptography|  
|Narušující změna|Bez ukončování řádků|  
  
> [!NOTE]
>  Toto upozornění byl naposledy aktualizován. listopadu 2015.  
  
## <a name="cause"></a>příčina  
 Funkce algoritmu hash, jako <xref:System.Security.Cryptography.MD5> a šifrovacích algoritmů, například <xref:System.Security.Cryptography.DES> a <xref:System.Security.Cryptography.RC2> můžou zpřístupnit významné riziko a může vést k úniku citlivých informací prostřednictvím trivial útoku techniky, jako jsou útoky hrubou silou a kolize hodnot hash.  
  
 Níže uvedeného seznamu kryptografických algoritmů, které se vztahují známých kryptografických útoků. Algoritmus kryptografické hodnoty hash <xref:System.Security.Cryptography.MD5> terčem útoků kolizí hash.  V závislosti na využití kolizí hash může vést k zosobnění, zneužití nebo jiných druhů útoky na systémy, které jsou závislé na jedinečný kryptografických výstup funkce algoritmu hash. Algoritmy šifrování <xref:System.Security.Cryptography.DES> a <xref:System.Security.Cryptography.RC2> jsou předmětem kryptografických útoků, které může vést k neočekávaným zpřístupnění šifrovaná data.  
  
## <a name="rule-description"></a>Popis pravidla  
 Kryptografické algoritmy nejsou považované za bezpečné a jejich použití se nedoporučuje. Algoritmus hash MD5 je náchylný kolizí známé útoky, když se bude lišit v závislosti na kontextu použít konkrétní ohrožení zabezpečení.  Jsou obzvláště citlivé délkami algoritmů hash použít k zajištění integrity dat (např. podpis souboru nebo digitální certifikát).  V tomto kontextu by útočníci vytvořit dvě samostatné částí dat, tak, aby neškodné data se můžou nahradit s škodlivá data bez změnit hodnotu hash nebo zneplatnění přidružené digitální podpis.  
  
 Pro šifrovací algoritmy:  
  
-   <xref:System.Security.Cryptography.DES>šifrování obsahuje malá velikost klíče, které by mohly být hrubou silou za méně než jeden den.  
  
-   <xref:System.Security.Cryptography.RC2>šifrování je ohrožena útoky založenými na útok související s klíčem, zjistí-li útočník matematickém vztahy mezi všechny klíčové hodnoty.  
  
 Toto pravidlo spustí, když se některé z výše uvedených kryptografické funkce vyhledá ve zdrojovém kódu a vyvolá upozornění pro uživatele.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Použijte kryptograficky silnější možnosti:  
  
-   Pro MD5, použít hodnoty hash v [SHA-2](https://msdn.microsoft.com/en-us/library/windows/desktop/aa382459.aspx) rodiny (například <xref:System.Security.Cryptography.SHA512>, <xref:System.Security.Cryptography.SHA384>, <xref:System.Security.Cryptography.SHA256>).  
  
-   DES a RC2 <xref:System.Security.Cryptography.Aes> šifrování.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Pokud ho revidován kryptografických expert není potlačení upozornění od tohoto pravidla.  
  
## <a name="pseudo-code-example"></a>Příklad pseudo kódu  
 Následující ukázka kódu pseudo znázorňuje vzoru zjištěný toto pravidlo a možné náhradní řešení.  
  
### <a name="md5-hashing-violation"></a>MD5 Použití algoritmu hash porušení  
  
```  
using System.Security.Cryptography;   
...   
var hashAlg = MD5.Create();  
  
```  
  
### <a name="solution"></a>Řešení  
  
```  
using System.Security.Cryptography;   
...   
var hashAlg = SHA256.Create();  
  
```  
  
### <a name="rc2-encryption-violation"></a>RC2 Porušení šifrování  
  
```  
using System.Security.Cryptography;   
...    
RC2 encAlg = RC2.Create();  
  
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
  
### <a name="des-br-br-encryption-violation"></a>DES <br /><br />Porušení šifrování  
  
```  
using System.Security.Cryptography;   
...   
DES encAlg = DES.Create();  
  
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