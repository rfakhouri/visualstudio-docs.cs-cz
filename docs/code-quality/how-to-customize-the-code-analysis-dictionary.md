---
title: "Postupy: přizpůsobení slovníku analýzy kódu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code analysis dictionary
- custom dictionary, code analysis
- dictionary, code analysis
ms.assetid: 667e3b4e-beff-48be-b3d1-376e1716a895
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7fa5f88a3578998fca325500a3815b909b6ce4a9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-customize-the-code-analysis-dictionary"></a>Postupy: Přizpůsobení slovníku Analýzy kódu
Analýza kódu pomocí integrovaného slovníku kontroluje identifikátory v kódu chyby v pravopisu, gramaticky případ a jiné zásady vytváření názvů služby [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] pokyny. Můžete vytvořit vlastní slovník soubor Xml pro přidat, odebrat nebo změnit podmínky, zkratky a zkratky do slovníku předdefinované.  
  
 Předpokládejme například, že váš kód obsažené třídy s názvem **DoorKnokker**. Analýza kódu by určit název jako složené ze dvou slov: **dveře** a **knokker**. Poté vyvolá upozornění, **knokker** nebyl zadán správně. Chcete-li vynutit analýza kódu rozpoznat pravopis, můžete přidat termín **knokker** do slovníku vlastní.  
  
## <a name="to-create-a-custom-dictionary"></a>Chcete-li vytvořit vlastní slovník  
 Vytvoření souboru, který je pojmenován **CustomDictionary.xml**.  
  
 Definujte vaše vlastní slova pomocí následující strukturu XML:  
  
```  
<Dictionary>  
      <Words>  
         <Unrecognized>  
            <Word>knokker</Word>  
         </Unrecognized>  
         <Recognized>  
            <Word></Word>  
         </Recognized>  
         <Deprecated>  
            <Term PreferredAlternate=""></Term>  
         </Deprecated>  
         <Compound>  
            <Term CompoundAlternate=""></Term>  
         </Compound>  
         <DiscreteExceptions>  
            <Term></Term>  
         </DiscreteExceptions>  
      </Words>  
      <Acronyms>  
         <CasingExceptions>  
            <Acronym></Acronym>  
         </CasingExceptions>  
      </Acronyms>  
   </Dictionary>  
```  
  
## <a name="custom-dictionary-elements"></a>Vlastní slovník elementů  
 Chování slovníku analýzy kódu můžete upravit přidáním podmínky jako vnitřní text ve slovníku vlastní následující prvky:  
  
-   [Slovník nebo slova nebo rozpoznán nebo Word](../code-quality/how-to-customize-the-code-analysis-dictionary.md#BKMK_DictionaryWordsRecognizedWord)  
  
-   [Slovník nebo slova nebo nerozpoznaný nebo Word](../code-quality/how-to-customize-the-code-analysis-dictionary.md#BKMK_DictionaryWordsUnrecognizedWord)  
  
-   [Slovník nebo slova nebo zastaralé nebo termín [@PreferredAlternate]](../code-quality/how-to-customize-the-code-analysis-dictionary.md#BKMK_DictionaryWordsDeprecatedTermPreferredAlternate)  
  
-   [Slovník nebo slova nebo složené nebo termín [@CompoundAlternate]](../code-quality/how-to-customize-the-code-analysis-dictionary.md#BKMK_DictionaryWordsCompoundTermCompoundAlternate)  
  
-   [Slovník nebo slova nebo DiscreteExceptions nebo termín](../code-quality/how-to-customize-the-code-analysis-dictionary.md#BKMK_DictionaryWordsDiscreteExceptionsTerm)  
  
-   [Slovník nebo režim/CasingExceptions nebo zkratce](../code-quality/how-to-customize-the-code-analysis-dictionary.md#BKMK_DictionaryAcronymsCasingExceptionsAcronym)  
  
###  <a name="BKMK_DictionaryWordsRecognizedWord"></a>Slovník nebo slova nebo rozpoznán nebo Word  
 Zahrnout termín seznam termínů, které identifikují analýza kódu jako správně napsán, přidejte jako vnitřní text prvku slovníku nebo slova nebo Recognized nebo Word termín. Podmínky v elementy slovníku nebo slova nebo Recognized nebo Word nerozlišují malá a velká písmena.  
  
 **Příklad**  
  
```  
<Dictionary>  
      <Words>  
         <Recognized>  
            <Word>knokker</Word>  
            ...  
         </Recognized>  
         ...  
      </Words>  
      ...  
</Dictionary>  
  
```  
  
 Pro následující pravidel analýzy kódu platí podmínky slovník nebo slova nebo Recognized uzly:  
  
-   [CA1701: Malá a velká písmena složených slov prostředku řetězců by měla být použita správně](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)  
  
-   [CA1702: Malá a velká písmena složených slov by měla být použita správně](../code-quality/ca1702-compound-words-should-be-cased-correctly.md)  
  
-   [CA1703: Řetězce prostředků by měly být zadány správně](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)  
  
-   [CA1704: Identifikátory by měly být zadány správně](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)  
  
-   [CA1709: Malá a velká písmena identifikátorů by měla být použita správně](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
-   [CA1726: Použijte upřednostňované výrazy](../code-quality/ca1726-use-preferred-terms.md)  
  
-   [CA2204: Literály by měly být zadány správně](../code-quality/ca2204-literals-should-be-spelled-correctly.md)  
  
###  <a name="BKMK_DictionaryWordsUnrecognizedWord"></a>Slovník nebo slova nebo nerozpoznaný nebo Word  
 Termín vyloučíte ze seznamu podmínek, které identifikují analýza kódu jako správně napsán, přidejte termín vyloučit jako vnitřní text prvku slovníku a slova nebo neznámá nebo aplikace Word. Podmínky v elementy slovníku nebo slova nebo neznámá nebo Word nerozlišují malá a velká písmena.  
  
 **Příklad**  
  
```  
<Dictionary>  
      <Words>  
         <Unrecognized>  
            <Word>meth</Word>  
            ...  
         </Unrecognized>  
         ...  
      </Words>  
      ...  
</Dictionary>  
  
```  
  
 Podmínky v uzlu slovník nebo slova nebo nerozpoznána platí pro následující pravidel analýzy kódu:  
  
-   [CA1701: Malá a velká písmena složených slov prostředku řetězců by měla být použita správně](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)  
  
-   [CA1702: Malá a velká písmena složených slov by měla být použita správně](../code-quality/ca1702-compound-words-should-be-cased-correctly.md)  
  
-   [CA1703: Řetězce prostředků by měly být zadány správně](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)  
  
-   [CA1704: Identifikátory by měly být zadány správně](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)  
  
-   [CA1709: Malá a velká písmena identifikátorů by měla být použita správně](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
-   [CA1726: Použijte upřednostňované výrazy](../code-quality/ca1726-use-preferred-terms.md)  
  
-   [CA2204: Literály by měly být zadány správně](../code-quality/ca2204-literals-should-be-spelled-correctly.md)  
  
###  <a name="BKMK_DictionaryWordsDeprecatedTermPreferredAlternate"></a>Slovník nebo slova nebo zastaralé nebo termín [@PreferredAlternate]  
 Zahrnout termín seznam termínů, které identifikují analýza kódu jako zastaralé, přidejte jako vnitřní text prvku slovníku nebo slova nebo zastaralé funkce nebo termín termín. Nepoužívané termín je slovo, které je napsán správně, ale by se neměla používat.  
  
 Zahrnout navrhovaná alternativní termín upozornění, zadejte alternativní v atributu PreferredAlternate elementu termín. Hodnota atributu můžete ponechat prázdné, pokud nechcete navrhovat náhradní.  
  
-   Nepoužívané termín ve slovníku nebo slova/zastaralé funkce nebo termín element není malá a velká písmena.  
  
-   Hodnota atributu PreferredAlternate rozlišuje velká a malá písmena. Použijte pascalcase pro složené alternativ.  
  
 **Příklad**  
  
```  
<Dictionary>  
      <Words>  
         <Deprecated>  
            <Term PreferredAlternate="LogOn">login</Term>  
            ...  
         </Deprecated>  
         ...  
      </Words>  
      ...  
</Dictionary>  
  
```  
  
 Pro následující pravidel analýzy kódu platí podmínky v uzlu slovník nebo slova nebo zastaralé funkce:  
  
-   [CA1701: Malá a velká písmena složených slov prostředku řetězců by měla být použita správně](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)  
  
-   [CA1702: Malá a velká písmena složených slov by měla být použita správně](../code-quality/ca1702-compound-words-should-be-cased-correctly.md)  
  
-   [CA1703: Řetězce prostředků by měly být zadány správně](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)  
  
-   [CA1704: Identifikátory by měly být zadány správně](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)  
  
-   [CA1726: Použijte upřednostňované výrazy](../code-quality/ca1726-use-preferred-terms.md)  
  
###  <a name="BKMK_DictionaryWordsCompoundTermCompoundAlternate"></a>Slovník nebo slova nebo složené nebo termín [@CompoundAlternate]  
 Předdefinované slovníku identifikuje některé podmínky jako jeden, diskrétní podmínky, nikoli složené termín. Zahrnout termín seznam termínů, které analýza kódu identifikuje jako složené word a zadejte správné rozlišených podmínek, přidejte jako vnitřní text prvku slovníku nebo slova nebo složené nebo termín termín. V atributu CompoundAlternate elementu termín zadejte jednotlivé slova, která tvoří složené termín využitím první písmena jednotlivých slov (pascalcase). Všimněte si, že výraz zadaný v vnitřní text se automaticky přidá do slovníku nebo slova nebo DiscreteExceptions seznamu.  
  
-   Nepoužívané termín ve slovníku nebo slova/zastaralé funkce nebo termín element není malá a velká písmena.  
  
-   Hodnota atributu PreferredAlternate rozlišuje velká a malá písmena. Použijte pascalcase pro složené alternativ.  
  
 **Příklad**  
  
```  
<Dictionary>  
      <Words>  
         <Compound>  
            <Term CompoundAlternate="CheckBox">checkbox</Term>  
            ...  
         </Compound>  
         ...  
      </Words>  
      ...  
</Dictionary>  
  
```  
  
 V uzlu slovník nebo slova nebo složené podmínky platí pro následující pravidel analýzy kódu:  
  
-   [CA1701: Malá a velká písmena složených slov prostředku řetězců by měla být použita správně](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)  
  
-   [CA1702: Malá a velká písmena složených slov by měla být použita správně](../code-quality/ca1702-compound-words-should-be-cased-correctly.md)  
  
-   [CA1703: Řetězce prostředků by měly být zadány správně](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)  
  
-   [CA1704: Identifikátory by měly být zadány správně](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)  
  
###  <a name="BKMK_DictionaryWordsDiscreteExceptionsTerm"></a>Slovník nebo slova nebo DiscreteExceptions nebo termín  
 Vyloučit termín, který se v seznamu podmínek, které identifikují analýza kódu jako jeden, přidejte diskrétní word při kontrole termín pravidly malá a velká písmena složených slov, termín jako vnitřní text prvku slovníku nebo slova nebo DiscreteExceptions nebo termín. Termín v elementu slovník nebo slova nebo DiscreteExceptions nebo termín není malá a velká písmena.  
  
 **Příklad**  
  
```  
<Dictionary>  
      <Words>  
         <DiscreteExceptions>  
            <Term>checkbox</Term>  
            ...  
         </DiscreteExceptions>  
         ...  
      </Words>  
      ...  
</Dictionary>  
  
```  
  
 Podmínky v uzlu slovník nebo slova nebo DiscreteExceptions platí pro následující pravidel analýzy kódu:  
  
-   [CA1701: Malá a velká písmena složených slov prostředku řetězců by měla být použita správně](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)  
  
-   [CA1702: Malá a velká písmena složených slov by měla být použita správně](../code-quality/ca1702-compound-words-should-be-cased-correctly.md)  
  
###  <a name="BKMK_DictionaryAcronymsCasingExceptionsAcronym"></a>Slovník nebo režim/CasingExceptions nebo zkratce  
 Zahrnout zkratka seznam termínů, které analýza kódu identifikuje jako správně zadané a určit, jak se používá zkratka při kontrole termín podle malá a velká písmena pravidel pro složených slov, přidejte termín jako vnitřní text slovník nebo režim/CasingExceptions / Acronym element. Zkratka v elementu slovník nebo režim/CasingExceptions nebo zkratku rozlišuje velká a malá písmena.  
  
 **Příklad**  
  
```  
<Dictionary>  
      <Acronyms>  
         <CasingExceptions>  
            <Acronym>NESW</Acronym>   <!-- North East South West -->  
            ...  
         </CasingExceptions>  
         ...  
      </Acronyms>  
      ...  
</Dictionary>  
  
```  
  
 Podmínky v uzlu slovník nebo režim/CasingExceptions platí pro následující pravidel analýzy kódu:  
  
-   [CA1709: Malá a velká písmena identifikátorů by měla být použita správně](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
##  <a name="BKMK_ToApplyACustomDictionaryToAProject"></a>Chcete-li použít vlastní slovník do projektu  
  
1.  V **Průzkumníku**, použijte jednu z následujících postupů:  
  
2.  Pokud chcete přidat do slovníku k jedinému projektu, klikněte pravým tlačítkem na název projektu a pak klikněte na tlačítko **přidat existující položku**. Zadejte soubor v **přidat existující položku** dialogové okno.  
  
3.  Chcete-li přidat slovník, který je sdílen mezi dva nebo více projektů, vyhledejte soubor pro sdílení v **přidat existující položku** dialogové okno pole, klikněte na šipku dolů na **přidat** tlačítko a pak klikněte na tlačítko **přidat jako odkaz** .  
  
4.  V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **CustomDictionary.xml** název souboru a klikněte na tlačítko **vlastnosti**.  
  
5.  Z **akce sestavení** seznamu, vyberte **CodeAnalysisDictionary**.  
  
6.  Z **kopírovat do výstupního adresáře** seznamu, vyberte **nekopírovat**.