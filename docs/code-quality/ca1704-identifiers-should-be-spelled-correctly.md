---
title: "CA1704: Identifikátory by měly být zadány správně | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1704
- IdentifiersShouldBeSpelledCorrectly
helpviewer_keywords:
- CA1704
- IdentifiersShouldBeSpelledCorrectly
ms.assetid: f2c7a44d-1690-44ca-9cd0-681b04b12b2a
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e43e3340cdbc05ec00c909542e201692199ccfef
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1704-identifiers-should-be-spelled-correctly"></a>CA1704: Identifikátory by měly být zadány správně
|||  
|-|-|  
|TypeName|IdentifiersShouldBeSpelledCorrectly|  
|CheckId|CA1704|  
|Kategorie|Microsoft.Naming|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Název identifikátoru obsahuje jeden nebo více slova, která nerozpoznal kontrola pravopisu knihovně společnosti Microsoft. Toto pravidlo není zkontrolujte konstruktory nebo s názvem zvláštní členy například get a nastavte vlastnosti přistupující objekty.  
  
## <a name="rule-description"></a>Popis pravidla  
 Toto pravidlo analyzuje identifikátor do tokenů a kontroluje, zda každý token. Analýza algoritmus provádí následující transformace:  
  
-   Velká písmena spusťte nový token. Například MyNameIsJoe tokenizes "My", "Name", "Je", "Jan".  
  
-   Několik velkých písmen spustí poslední velké písmeno nový token. Například GUIEditor tokenizes k "Grafickým uživatelským rozhraním", "Editor".  
  
-   Úvodní a koncové apostrofy se odeberou. Například 'odesílatele' tokenizes "odesílateli".  
  
-   Podtržítka označují konec token a jsou odebrány. Například Hello_world tokenizes na text "Hello", "world".  
  
-   Vložené ampersandy se odeberou. Například pro & mat tokenizes k "format".  
  
 Ve výchozím nastavení se používá verze Angličtina (en) nástroj pro kontrolu pravopisu. Žádné jiné jazykové slovníky jsou nyní k dispozici.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, opravte pravopis aplikace word nebo přidat slovo do slovníku nazvaného CustomDictionary.xml. Umístěte slovníku v instalačním adresáři nástroje adresáři projektu nebo v adresáři, který je přidružen nástroj v profilu uživatele (%USERPROFILE%\Application\\...). Další informace o přidání do projektu ve slovníku vlastní [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], najdete v části [postupy: přizpůsobení slovníku analýzy kódu](../code-quality/how-to-customize-the-code-analysis-dictionary.md)  
  
-   Přidejte slova, která by nemělo způsobit narušení ve slovníku nebo slova nebo Recognized cestě.  
  
-   Přidejte slova, která by nemělo způsobit narušení v cestě slovník nebo slova nebo Nerozpoznán.  
  
-   Přidejte slova, která by měla být označené jako zastaralé v cestě slovník nebo slova nebo zastaralé. Podívejte se na téma související pravidlo [CA1726: použijte upřednostňované výrazy](../code-quality/ca1726-use-preferred-terms.md) Další informace.  
  
-   Přidáte výjimky pravidla velká a malá písmena zkratku do slovníku nebo režim/CasingExceptions cesty.  
  
 Následuje příklad struktury soubor vlastní slovník.  
  
```  
<Dictionary>  
   <Words>  
      <Unrecognized>  
         <Word>cb</Word>  
      </Unrecognized>  
      <Recognized>  
         <Word>stylesheet</Word>  
         <Word>GotDotNet</Word>  
      </Recognized>  
      <Deprecated>  
         <Term PreferredAlternate="EnterpriseServices">ComPlus</Term>  
      </Deprecated>  
   </Words>  
   <Acronyms>  
      <CasingExceptions>  
         <Acronym>CJK</Acronym>  
         <Acronym>Pi</Acronym>  
      </CasingExceptions>  
   </Acronyms>  
</Dictionary>  
```  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Potlačíte upozornění na toto pravidlo pouze v případě, že je slovo záměrně překlepu a slovo platí pro omezenou sadu knihovny. Správně hláskovaným slova redukovat křivku vyžadovanou pro nové knihovny softwaru.  
  
## <a name="related-rules"></a>Související pravidla  
 [CA2204: Literály by měly být zadány správně](../code-quality/ca2204-literals-should-be-spelled-correctly.md)  
  
 [CA1703: Řetězce prostředků by měly být zadány správně](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)  
  
 [CA1709: Identifikátory by měla být použita správně](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
 [CA1708: Identifikátory by se měly lišit o více než případu](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)  
  
 [CA1707: Identifikátory by neměly obsahovat podtržítka](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)  
  
 [CA1726: Použijte upřednostňované výrazy](../code-quality/ca1726-use-preferred-terms.md)  
  
## <a name="see-also"></a>Viz také  
 [Postupy: přizpůsobení slovníku analýzy kódu](../code-quality/how-to-customize-the-code-analysis-dictionary.md)
