---
title: "Návod: Konfigurace a používání vlastní sady pravidel | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code analysis, walkthroughs
- code analysis, rule sets
ms.assetid: 7fe0a4e3-1ce0-4f38-a87a-7d81238ec7cd
caps.latest.revision: "40"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 054cf016dba69561591ad6bc8b18029272e85d8f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-configuring-and-using-a-custom-rule-set"></a>Návod: Konfigurace a používání vlastní sady pravidel
Tento návod ukazuje, jak pomocí nástrojů pro analýzu kódu, které byly nakonfigurovány k použijte vlastní *sadu pravidel* na knihovny tříd. Můžete vybrat sadu pravidel, která má vztah k typu projektu, který jste zadali pro vaše řešení, nebo můžete vybrat, že nastaví alternativní pravidlo ke splnění konkrétní potřebu například procházení kódu starší verze na problémy, které lze opravit pevných způsobem. V obou případech sady pravidel se dá přizpůsobit taky vyladění je požadavky projektu.  
  
 V tomto návodu se krok prostřednictvím tyto procesy:  
  
-   Vytvoření knihovny tříd.  
  
-   Vyberte **Microsoft základní pravidla obecných zásad návrhu** sada pravidel analýzy kódu.  
  
-   Přidáte vlastní kód pro třídu.  
  
-   Spuštění analýzy kódu.  
  
-   Přizpůsobte sadu pravidel.  
  
-   Spuštění analýzy kódu a zjistěte, jak nastavit pravidlo přizpůsobení chování funguje.  
  
## <a name="prerequisites"></a>Požadavky  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], nebo[!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
## <a name="using-rule-sets-with-code-analysis"></a>Použití sad pravidel analýzy kódu  
 Nejprve vytvořte knihovnu jednoduchá.  
  
#### <a name="create-a-class-library"></a>Vytvoření knihovny tříd  
  
1.  Na **soubor** nabídky, klikněte na tlačítko **nový** a pak klikněte na **projektu**.  
  
2.  V **nový projekt** dialogovém **typy projektů**, klikněte na tlačítko **Visual C#**.  
  
3.  V části **Visual C#**, vyberte **knihovny tříd**.  
  
4.  V **název** textového pole, typ **RuleSetSample** a pak klikněte na **OK**.  
  
 V dalším kroku vyberete **Microsoft základní pravidla obecných zásad návrhu** sadu pravidel a uložit ho s projektem.  
  
#### <a name="select-a-code-analysis-rule-set"></a>Vyberte sadu pravidel analýzy kódu  
  
1.  Na **analyzovat** nabídky, klikněte na tlačítko **konfigurace analýzy kódu pro RuleSetSample**.  
  
     Zobrazí se konfigurace nastavení pro analýzu kódu.  
  
2.  V **spuštění této sady pravidel** rozevíracího seznamu vyberte **všechna pravidla Microsoft**.  
  
     Další informace o sady k dispozici pravidel najdete v tématu [referenční dokumentace sady pravidel nástroje Analýza kódu](../code-quality/code-analysis-rule-set-reference.md).  
  
     V nabídce Soubor klikněte na tlačítko **uložit vybrané položky** aktualizace souboru projektu s informace o sadu pravidel, který jste vybrali a jeho nastavení.  
  
    > [!TIP]
    >  V situaci, reálného, je vhodné použít pro stanovení priority problémy, které chcete zacílit s analýzou kódu začínat **Minimální doporučená pravidla** sady pravidel a opravte problémy požadované a pak postupně přidávat Další pravidla nebo pravidlo nastaví najít a opravit další problémy.  
  
 V dalším kroku přidáte nějaký kód do třídy knihovny, která se použije k předvedení porušení CA1704 "Identifikátory by měly být zadány správně" pravidel nástroje Analýza kódu. Další informace najdete v tématu [CA1704: identifikátory by měly být zadány správně](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md).  
  
#### <a name="add-your-own-code"></a>Přidat vlastní kód  
  
-   V Průzkumníku řešení otevřete soubor Class1.cs a nahraďte existující kód s následujícími službami:  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
  
    namespace RuleSetSample  
    {  
        public class Class1  
        {  
            //The variable parameter names "a" and "b" will cause  
            //the warning CA 1704 Microsoft.Naming "Consider   
            //providing a more meaningful name" to fire  
            public int AddIntegers(int a, int b)  
            {  
  
                int sum = a + b;  
  
                return (sum);  
            }  
        }  
    }  
  
    ```  
  
 Nyní můžete spustit analýza kódu v projektu RuleSetSample a vyhledejte všechny chyby a varování vygenerované v okně Seznam chyb.  
  
#### <a name="run-code-analysis-on-the-rulesetsample-project"></a>Spuštění analýzy kódu v projektu RuleSetSample  
  
1.  Na **analyzovat** nabídky, klikněte na tlačítko **spuštění analýzy kódu na RuleSetSample**.  
  
2.  V okně Seznam chyb, klikněte na **upozornění** a klikněte **popis** záhlaví sloupce seřadíte upozornění alfanumericky.  
  
     V reálné aplikaci by opravit jakékoli porušení pravidel vhodné v tomto okamžiku opravě nebo volitelně vypnout nebo potlačit pravidlo, je-li určit, že nebylo vhodné řešení. Další informace najdete v tématu [potlačení upozornění s použitím atributu SuppressMessage](../code-quality/suppress-warnings-by-using-the-suppressmessage-attribute.md).  
  
3.  Všimněte si CA1704 upozornění. Tato porušení na toto pravidlo znamenat, že "zvažte poskytuje více smysluplný název pro parametry." Může opravte problém v kódu nebo můžete zakázat pravidla, jak je popsáno v dalším postupu.  
  
 V dalším kroku bude upravit pravidlo vyloučen CA1704 upozornění, "Identifikátory by měly být zadány správně".  
  
#### <a name="customize-the-rule-set-for-your-project-to-disable-a-specific-rule"></a>Upravit pravidlo, nastavte pro váš projekt zakázat konkrétní pravidlo  
  
1.  Na **analyzovat** nabídky, klikněte na tlačítko **konfigurace analýzy kódu pro RuleSetSample**.  
  
2.  V **spuštění této sady pravidel** rozevíracího seznamu seznamu, ověřte, zda **všechna pravidla Microsoft** pravidlo sadu stále zvýrazní a pak klikněte na **otevřete**. Zobrazí se stránka sady pravidel.  
  
3.  Rozbalte uzel Microsoft.Naming kategorie a potom vyberte CA1704 upozornění.  
  
4.  V části **akce** sloupce, vyberte **None.** CA1704 zabrání zobrazení jako upozornění nebo chyby v okně Seznam chyb.  
  
     Teď by být dobrý čas a experimentovat s různými tlačítka panelu nástrojů a možnosti, abyste se seznámili s nimi filtrování. Například můžete použít **Group By** při vyhledání konkrétní pravidla nebo kategorie pravidel rozevíracího seznamu. Dalším příkladem je, že můžete používat **skrýt zakázaná pravidla** tlačítka na panelu nástrojů stránky sadu pravidel pro skrytí nebo zobrazení všechna pravidla s **akce** sloupec nastavený na **žádné**. To může být užitečné, pokud chcete vyhledat všechna pravidla, která jste vypnuli k ověření, stále chcete mít je zakázána.  
  
5.  V nabídce Zobrazit klikněte na tlačítko Vlastnosti – okno. Typ **Moje vlastní pravidlo nastavené** do pole název okna Vlastnosti nástroje. Zobrazovaný název sady nové pravidel se tak změní [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] IDE.  
  
6.  Na **soubor** nabídky, klikněte na tlačítko **uložit všechny Rules.ruleset** uložení vlastní pravidla sady. Přejděte do kořenové složky vašeho projektu. V **název souboru** textového pole, typ **MyCustomRuleSet**. Pro použití s projektu můžete nyní vybrat sadu vlastní pravidlo.  
  
 Sadou vaší nové pravidel vytvořen budete muset teď nakonfigurovat nastavení projektu k určení, kterou chcete použít nastavení s ním nové pravidlo.  
  
#### <a name="specify-the-new-rule-set-for-use-with-your-project"></a>Zadejte nové pravidlo nastavit pro použití s projektu  
  
1.  V Průzkumníku řešení klikněte pravým tlačítkem na projekt a potom vyberte **vlastnosti**.  
  
2.  V **vlastnosti** , klikněte na **analýza kódu**.  
  
     V **spuštění této sady pravidel** rozevíracího seznamu, klikněte na tlačítko  **\<Procházet... >**. Přejděte do kořenové složky projektu kódu a pak vyberte **MyCustomRuleSet.ruleset**. Toto je nové sady pravidel, který jste vytvořili v předchozím postupu.  
  
3.  Na **soubor** nabídky, klikněte na tlačítko **Uložit** uložte konfiguraci projektu. Sada vlastní pravidlo lze nyní s projektem.  
  
 Nakonec se spustí znovu pomocí vaší MyCustomRuleSet sada pravidel analýzy kódu. Všimněte si, že v okně Seznam chyb nezobrazí porušení pravidel výkonu CA1704.  
  
#### <a name="run-code-analysis-on-the-rulesetsample-project-for-the-second-time"></a>Spuštění analýzy kódu v projektu RuleSetSample podruhé  
  
1.  Na **analyzovat** nabídky, klikněte na tlačítko **spuštění analýzy kódu na RuleSetSample**.  
  
2.  V okně Seznam chyb, Všimněte si, že po kliknutí na tlačítko **upozornění**, už se nezobrazují porušení upozornění CA1704 pro pravidlo "Identifikátory by měly být zadány správně".  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Konfigurace analýzy kódu pro spravovaný projekt kódu](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)   
 [Referenční dokumentace sady pravidel nástroje Analýza kódu](../code-quality/code-analysis-rule-set-reference.md)