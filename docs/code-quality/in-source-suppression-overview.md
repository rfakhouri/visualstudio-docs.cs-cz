---
title: "Přehled potlačování ve zdroji | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source suppression, code analysis
- code analysis, source suppression
ms.assetid: f1a2dc6a-a9eb-408c-9078-2571e57d207d
caps.latest.revision: "40"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f35833df8e84a4e4caba8fd46f8daea8dd5119a1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="in-source-suppression-overview"></a>Přehled potlačování ve zdroji
Potlačení zdroje v je schopnost potlačit nebo ignorovat porušení analýza kódu ve spravovaném kódu tak, že přidáte **suppressmessage –** atribut segmenty kódu, které způsobí porušení zásad. **Suppressmessage –** se podmíněný atribut, který je součástí IL metadat vašeho sestavení spravovaného kódu, jenom když je symbol kompilace CODE_ANALYSIS definované při kompilaci.  
  
 V jazyce C + +/ CLI, pomocí makra CA_SUPPRESS_MESSAGE nebo CA_GLOBAL_SUPPRESS_MESSAGE v záhlaví souboru, přidejte atribut.  
  
 Aby se zabránilo přesouvání metadata potlačení v zdroje omylem byste neměli používat suppressions-source u sestavení pro vydání. Kvůli zpracování náklady potlačení ve zdroje vaší aplikace může také docházet ke snížení výkonu zahrnutím metadata potlačení v zdroje.  
  
> [!NOTE]
>  Není nutné předat kód tyto atributy sami. Další informace najdete v tématu [postupy: potlačení upozornění s použitím položky nabídky](../code-quality/how-to-suppress-warnings-by-using-the-menu-item.md). Položky nabídky není k dispozici pro C++ – kód.  
  
## <a name="suppressmessage-attribute"></a>Suppressmessage – atribut  
 Když kliknete pravým tlačítkem na upozornění analýzy kódu v **seznam chyb** a pak klikněte na **potlačit zprávy**, **suppressmessage –** atribut se přidá do vašeho kódu nebo na globální suppressions souboru projektu.  
  
 **Suppressmessage –** atribut má následující formát:  
  
```vb  
<Scope:SuppressMessage("Rule Category", "Rule Id", Justification = "Justification", MessageId = "MessageId", Scope = "Scope", Target = "Target")>  
```  
  
```csharp  
[Scope:SuppressMessage("Rule Category", "Rule Id", Justification = "Justification", MessageId = "MessageId", Scope = "Scope", Target = "Target")]  
  
```  
  
 [C++]  
  
```  
CA_SUPPRESS_MESSAGE("Rule Category", "Rule Id", Justification = "Justification", MessageId = "MessageId", Scope = "Scope", Target = "Target")  
  
```  
  
 Kde:  
  
-   **Pravidlo kategorie** – kategorie, ve kterém je definovaný pravidlo. Další informace o kategorií pravidel analýzy kódu najdete v tématu [analýzy kódu pro spravovaný kód upozornění](../code-quality/code-analysis-for-managed-code-warnings.md).  
  
-   **Pravidlo Id** -identifikátor pravidla. Podpora zahrnuje jak krátký a dlouhý název identifikátor pravidla. Krátký název je CAXXXX; dlouhý název je CAXXXX:FriendlyTypeName.  
  
-   **Při zarovnání do bloku** – text, který se používá k dokumentu z důvodu pro potlačení zprávy.  
  
-   **Id zprávy** – jedinečný identifikátor problém pro každou zprávu.  
  
-   **Obor** -cíl, na kterém je potlačeno upozornění. Pokud není zadaný cíl, je nastaven k cílovému atributu. Podporované obory zahrnují následující:  
  
    -   Modul  
  
    -   Obor názvů  
  
    -   Prostředek  
  
    -   Typ  
  
    -   Člen  
  
-   **Cíl** – identifikátor, který slouží k určení cíle, na kterém je potlačeno upozornění. Musí obsahovat položky plně kvalifikovaný název.  
  
## <a name="suppressmessage-usage"></a>Suppressmessage – použití  
 Upozornění analýzy kódu jsou potlačovány na úrovni, na kterou instanci **suppressmessage –** atribut se používá. Účelem tohoto objektu je úzce spojte potlačení informací pomocí kódu kde dojde k porušení zásady.  
  
 Obecná forma potlačení zahrnuje kategorie pravidel a identifikátor pravidla, která obsahuje volitelné čitelná pro člověka reprezentace název pravidla. Například  
  
 `[SuppressMessage("Microsoft.Design", "CA1039:ListsAreStrongTyped")]`  
  
 Pokud existují striktní výkonu důvody pro minimalizaci metadata potlačení v zdroje, můžete vynecháno samotný název pravidla. Kategorie pravidel a jeho ID pravidla společně tvoří pravidlo dostatečně jedinečný identifikátor. Například  
  
 `[SuppressMessage("Microsoft.Design", "CA1039")]`  
  
 Tento formát se nedoporučuje kvůli problémům s udržovatelnosti.  
  
## <a name="suppressing-multiple-violations-within-a-method-body"></a>Potlačení více porušení v textu – metoda  
 Atributy lze použít pouze na metodu a nemůže být vložen v těle metoda. Můžete však zadat identifikátor jako ID zprávy k rozlišení více výskytů typů narušení v rámci metody.  
  
 [!code-cpp[InSourceSuppression#1](../code-quality/codesnippet/CPP/in-source-suppression-overview_1.cpp)]
 [!code-vb[InSourceSuppression#1](../code-quality/codesnippet/VisualBasic/in-source-suppression-overview_1.vb)]
 [!code-csharp[InSourceSuppression#1](../code-quality/codesnippet/CSharp/in-source-suppression-overview_1.cs)]  
  
## <a name="generated-code"></a>Generovaný kód  
 Kompilátory spravovaného kódu a některé nástroje třetích stran pro generování kódu usnadňuje vývoj rychlé kódu. Generované kompilátorem kód, který se zobrazí ve zdrojových souborech obvykle označena **GeneratedCodeAttribute** atribut.  
  
 Můžete zvolit, jestli se má potlačit upozornění analýzy kódu a chyby pro vygenerovaný kód. Informace o tom, jak potlačit takové upozornění a chyby najdete v tématu [postupy: potlačení upozornění pro kód generované](../code-quality/how-to-suppress-code-analysis-warnings-for-generated-code.md).  
  
 Všimněte si, že analýza kódu ignoruje **GeneratedCodeAttribute** kdy byl použit k celé sestavení nebo jeden parametr. V takových situacích dojít zřídka.  
  
## <a name="global-level-suppressions"></a>Globální úrovni Suppressions  
 Nástroj Analýza spravovaného kódu zjistí, zda **suppressmessage –** atributy, které se použijí na úrovni sestavení, modulu, typu, člen nebo parametr. Aktivuje se také porušení proti prostředky a obory názvů. Tato porušení se musí použít na globální úrovni a jsou obor a cílem. Například následující zpráva potlačí narušení obor názvů:  
  
 `[module: SuppressMessage("Microsoft.Design", "CA1020:AvoidNamespacesWithFewTypes", Scope = "namespace", Target = "MyNamespace")]`  
  
> [!NOTE]
>  Když je potlačit upozornění s oborem názvů, potlačí upozornění na obor názvů sám sebe. Je nepotlačuje upozornění s typy v rámci oboru názvů.  
  
 Všechny potlačení může být vyjádřený zadáním výslovného oboru. Tyto suppressions musí za provozu na globální úrovni. Potlačení úrovni člena nelze zadat pomocí architekturu typu.  
  
 Globální úrovni suppressions jsou jedině k potlačení zprávy, které odkazují na generované kompilátorem kódu, které nejsou namapované do zdroje explicitně zadaný uživatel. Následující kód například potlačí narušení proti konstruktor vygenerované kompilátoru:  
  
 `[module: SuppressMessage("Microsoft.Design", "CA1055:AbstractTypesDoNotHavePublicConstructors", Scope="member", Target="Microsoft.Tools.FxCop.Type..ctor()")]`  
  
> [!NOTE]
>  Cíl vždy obsahuje položku plně kvalifikovaný název.  
  
## <a name="global-suppression-file"></a>Globální potlačení souboru  
 Soubor globální potlačení udržuje suppressions, které jsou globální úrovni suppressions nebo suppressions, které neurčují cíl. Například suppressions pro porušení úrovně sestavení jsou uloženy v tomto souboru. Kromě toho některé suppressions ASP.NET jsou uloženy v tomto souboru protože úrovně nastavení projektu nejsou k dispozici pro kódu na pozadí formuláře. Globální potlačení je vytvořen a přidán do projektu poprvé, kterou vyberete **v souboru projektu potlačení** možnost **potlačit zprávy** příkazu v okně Seznam chyb. Další informace najdete v tématu [postupy: potlačení upozornění s použitím položky nabídky](../code-quality/how-to-suppress-warnings-by-using-the-menu-item.md).  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Diagnostics.CodeAnalysis>