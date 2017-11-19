---
title: "Návod: Zobrazení odpovídající složené závorky | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], new - brace matching
ms.assetid: 5af08ac7-1d08-4ccf-997e-01aa6cb3d3d7
caps.latest.revision: "27"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c4a7d122f19e21eebbe5bd598272fb7cb9f52b27
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-displaying-matching-braces"></a>Návod: Zobrazení odpovídající složené závorky
Můžete implementovat funkce založené na jazyce jako třeba závorky definováním složené závorky, které chcete porovnat a následným přidáním značku značky text odpovídající složené závorky, když pomocí kurzoru je na některém ze složené závorky. Můžete definovat složené závorky v kontextu jazyka, nebo můžete definovat typ vlastního souboru název rozšíření a obsahu a použití značek u právě tohoto typu nebo značky můžete použít pro existující typ obsahu (například "text"). Následující postup ukazuje, jak použít závorky značek k typu obsahu "text".  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-managed-extensibility-framework-mef-project"></a>Vytvoření projektu spravovaných rozšíření Framework (MEF)  
  
#### <a name="to-create-a-mef-project"></a>Vytvoření projektu MEF  
  
1.  Vytvoření projektu třídění Editor. Název řešení `BraceMatchingTest`.  
  
2.  Do projektu přidejte šablony položky třídění Editor. Další informace najdete v tématu [vytváření rozšíření pomocí šablony položky Editor](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
3.  Odstraňte existující soubory třídy.  
  
## <a name="implementing-a-brace-matching-tagger"></a>Implementace závorky Tagger  
 Chcete-li získat složená závorka zvýraznění vliv, který se podobá, který se používá v sadě Visual Studio, můžete implementovat tagger typu <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag>. Následující kód ukazuje, jak definovat tagger pro dvojice závorek na libovolnou úroveň vnoření. V tomto příkladu [] dvojice závorek. [] {} jsou definovány v konstruktoru tagger, ale v implementaci úplným jazykovým páry relevantní závorek by být definována v specifikace jazyka.  
  
#### <a name="to-implement-a-brace-matching-tagger"></a>K implementaci závorky tagger  
  
1.  Přidejte soubor třídy s názvem BraceMatching.  
  
2.  Importujte následující obory názvů.  
  
     [!code-csharp[VSSDKBraceMatchingTest#1](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_1.cs)]
     [!code-vb[VSSDKBraceMatchingTest#1](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_1.vb)]  
  
3.  Definice třídy `BraceMatchingTagger` který dědí z <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601> typu <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag>.  
  
     [!code-csharp[VSSDKBraceMatchingTest#2](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_2.cs)]
     [!code-vb[VSSDKBraceMatchingTest#2](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_2.vb)]  
  
4.  Přidáte vlastnosti pro textového zobrazení, zdrojová vyrovnávací paměť a aktuální snímek bod a také sada párů závorek.  
  
     [!code-csharp[VSSDKBraceMatchingTest#3](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_3.cs)]
     [!code-vb[VSSDKBraceMatchingTest#3](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_3.vb)]  
  
5.  V konstruktoru tagger, nastavte vlastnosti a přihlásit se k zobrazení událostí změn <xref:Microsoft.VisualStudio.Text.Editor.ITextCaret.PositionChanged> a <xref:Microsoft.VisualStudio.Text.Editor.ITextView.LayoutChanged>. V tomto příkladu pro ilustraci, odpovídající páry je definována v konstruktoru.  
  
     [!code-csharp[VSSDKBraceMatchingTest#4](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_4.cs)]
     [!code-vb[VSSDKBraceMatchingTest#4](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_4.vb)]  
  
6.  Jako součást <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601> implementace TagsChanged událost deklarovat.  
  
     [!code-csharp[VSSDKBraceMatchingTest#5](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_5.cs)]
     [!code-vb[VSSDKBraceMatchingTest#5](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_5.vb)]  
  
7.  Obslužné rutiny událostí aktualizovat aktuální pozici pomocí kurzoru `CurrentChar` vlastnost a vyvolat událost TagsChanged.  
  
     [!code-csharp[VSSDKBraceMatchingTest#6](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_6.cs)]
     [!code-vb[VSSDKBraceMatchingTest#6](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_6.vb)]  
  
8.  Implementace <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601.GetTags%2A> metoda tak, aby odpovídaly složené závorky buď když aktuální znak otevřete levá složená závorka nebo když předchozí znak je zavřít složené závorce, jako v sadě Visual Studio. Pokud je nalezena shoda, tato metoda vytvoří dvě značky, jeden pro otevřené závorek a jeden pro zavřít závorek.  
  
     [!code-csharp[VSSDKBraceMatchingTest#7](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_7.cs)]
     [!code-vb[VSSDKBraceMatchingTest#7](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_7.vb)]  
  
9. Následující metody privátní najít odpovídajících složených závorek v libovolnou úroveň vnoření. První metoda vyhledá zavřít znak, který odpovídá otevřete znaku:  
  
     [!code-csharp[VSSDKBraceMatchingTest#8](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_8.cs)]
     [!code-vb[VSSDKBraceMatchingTest#8](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_8.vb)]  
  
10. Následující pomocnou metodu vyhledá otevřete znak, který odpovídá zavřít znaku:  
  
     [!code-csharp[VSSDKBraceMatchingTest#9](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_9.cs)]
     [!code-vb[VSSDKBraceMatchingTest#9](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_9.vb)]  
  
## <a name="implementing-a-brace-matching-tagger-provider"></a>Implementace závorky Tagger zprostředkovatele  
 Kromě implementace tagger, musíte také implementovat a exportovat tagger zprostředkovatele. V takovém případě je typ obsahu zprostředkovatele "text". To znamená, že odpovídající složené závorce se objeví v všechny typy textových souborů, ale úplnější implementace by použít závorky pouze na konkrétní typ obsahu.  
  
#### <a name="to-implement-a-brace-matching-tagger-provider"></a>Pro implementaci zprostředkovatele odpovídající tagger závorek  
  
1.  Deklarovat tagger zprostředkovatele, který dědí z <xref:Microsoft.VisualStudio.Text.Tagging.IViewTaggerProvider>, pojmenujte ji BraceMatchingTaggerProvider a exportovat je <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "text" a <xref:Microsoft.VisualStudio.Text.Tagging.TagTypeAttribute> z <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag>.  
  
     [!code-csharp[VSSDKBraceMatchingTest#10](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_10.cs)]
     [!code-vb[VSSDKBraceMatchingTest#10](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_10.vb)]  
  
2.  Implementace <xref:Microsoft.VisualStudio.Text.Tagging.IViewTaggerProvider.CreateTagger%2A> metoda pro vytvoření instance BraceMatchingTagger.  
  
     [!code-csharp[VSSDKBraceMatchingTest#11](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_11.cs)]
     [!code-vb[VSSDKBraceMatchingTest#11](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_11.vb)]  
  
## <a name="building-and-testing-the-code"></a>Vytváření a testování kódu  
 K otestování tohoto kódu, sestavte řešení BraceMatchingTest a spusťte ji v experimentální instanci.  
  
#### <a name="to-build-and-test-bracematchingtest-solution"></a>Pro sestavení a otestování BraceMatchingTest řešení  
  
1.  Sestavte řešení.  
  
2.  Když spustíte tohoto projektu v ladicím programu, je vytvořena instance druhou instanci sady Visual Studio.  
  
3.  Vytvoření textového souboru a zadejte nějaký text, který obsahuje odpovídající složené závorky.  
  
    ```  
    hello {  
    goodbye}  
  
    {}  
  
    {hello}  
    ```  
  
4.  Když umístíte pomocí kurzoru před otevřete levá složená závorka, by měl mít zvýrazněná této závorek a odpovídajících složených závorek zavřít. Když umístěte kurzor bezprostředně za zavřít složené závorce, by měly být označeny této závorek a odpovídajících otevřete složených závorek.  
  
## <a name="see-also"></a>Viz také  
 [Návod: Propojení typu obsahu s příponu názvu souboru](../extensibility/walkthrough-linking-a-content-type-to-a-file-name-extension.md)