---
title: 'Ca5351: Nepoužívejte poškozené kryptografické algoritmy | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
ms.assetid: 483f51b3-e186-4433-b48e-5ca24a9a9c94
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 780745e2b4213d8fdd130fe03cac292b233c5b0c
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63430678"
---
# <a name="ca5351-do-not-use-broken-cryptographic-algorithms"></a>CA5351: Nepoužívejte poškozené kryptografické algoritmy
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotUseBrokenCryptographicAlgorithms|  
|CheckId|CA5351|  
|Kategorie|Microsoft.Cryptography|  
|Narušující změna|Pevné|  
  
> [!NOTE]
> Toto upozornění byl naposledy aktualizován. listopadu 2015.  
  
## <a name="cause"></a>Příčina  
 Funkce, jako hashování <xref:System.Security.Cryptography.MD5> a šifrovacích algoritmů, jako <xref:System.Security.Cryptography.DES> a <xref:System.Security.Cryptography.RC2> můžete zveřejnit významné riziko a může vést k úniku citlivých informací pomocí technik triviální útoků, jako jsou například útoky hrubou silou a kolize hodnot hash.  
  
 Níže uvedeného seznamu kryptografických algoritmů, které se vztahují známé kryptografického útoku. Kryptografická hodnota hash algoritmu <xref:System.Security.Cryptography.MD5> terčem útoků kolize hodnot hash.  V závislosti na využití může vést ke kolizi hash k zosobnění, manipulaci nebo jiné typy útoků na systémech, které závisí na jedinečných kryptografických výstup hashovací funkce. Algoritmy šifrování <xref:System.Security.Cryptography.DES> a <xref:System.Security.Cryptography.RC2> jsou v souladu s kryptografického útoku, které může vést k neúmyslnému zveřejnění šifrovaná data.  
  
## <a name="rule-description"></a>Popis pravidla  
 Kryptografické algoritmy nejsou považované za bezpečné a jejich použití se nedoporučuje. Algoritmus hash MD5 je náchylný k kolizí známé útoky, když se liší v závislosti na kontextu použití konkrétní ohrožení zabezpečení.  Algoritmy hash používá k zajištění integrity dat (např. podpis souboru nebo digitální certifikát) jsou snadno napadnutelný.  V tomto kontextu může útočník generovat dva samostatné druhy dat, tak, aby neškodné data se můžou nahradit se zlými úmysly daty a bez změna hodnoty hash nebo zrušení platnosti přidružený digitální podpis.  
  
 Pro šifrovací algoritmy:  
  
- <xref:System.Security.Cryptography.DES> šifrování obsahuje malá velikost klíče, které by mohly být útokem hrubou silou za kratší dobu než den.  
  
- <xref:System.Security.Cryptography.RC2> šifrování je náchylný k útok související s klíčem, pokud útočník zjistí matematické vztahy mezi všechny klíčové hodnoty.  
  
  Toto pravidlo aktivuje, když najde některý z výše uvedených kryptografické funkce ve zdrojovém kódu a vyvolá upozornění pro uživatele.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Použijte kryptograficky silnější možnosti:  
  
- MD5, použijte hodnoty hash v [SHA-2](https://msdn.microsoft.com/library/windows/desktop/aa382459.aspx) řady (třeba <xref:System.Security.Cryptography.SHA512>, <xref:System.Security.Cryptography.SHA384>, <xref:System.Security.Cryptography.SHA256>).  
  
- DES a RC2 <xref:System.Security.Cryptography.Aes> šifrování.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění tohoto pravidla, pokud je byly zkontrolovány podle kryptografického odborníka.  
  
## <a name="pseudo-code-example"></a>Příklad pseudo kódu  
 Následující ukázka pseudo kódu znázorňuje, zjistí toto pravidlo a je to možné alternativy.  
  
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
  
### <a name="des-br-br-encryption-violation"></a>DES <br /><br />Šifrování porušení  
  
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