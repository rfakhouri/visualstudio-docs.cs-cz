---
title: 'Návod: Vytvoření přehledu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - outlining
ms.assetid: d75a44aa-265a-44d4-9c28-457f59c4ff9f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8360daf5ff1e7d94d995bdbefee6228a47e47db8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31143888"
---
# <a name="walkthrough-outlining"></a>Návod: vytvoření přehledu
Můžete implementovat funkce založené na jazyce jako třeba osnovy definováním druhy text oblastí, které chcete rozbalit nebo sbalit. Můžete definovat oblasti v kontextu služby jazyk, nebo můžete definovat typ vlastního souboru název rozšíření a obsahu a definice oblast týkají pouze typu nebo definice oblasti můžete použít pro existující typ obsahu (například "text"). Tento návod ukazuje, jak definovat a zobrazení osnovy oblastí.  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-managed-extensibility-framework-mef-project"></a>Vytvoření projektu spravovaných rozšíření Framework (MEF)  
  
#### <a name="to-create-a-mef-project"></a>Vytvoření projektu MEF  
  
1.  Vytvoření projektu VSIX. Název řešení `OutlineRegionTest`.  
  
2.  Do projektu přidejte šablony položky třídění Editor. Další informace najdete v tématu [vytváření rozšíření pomocí šablony položky Editor](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
3.  Odstraňte existující soubory třídy.  
  
## <a name="implementing-an-outlining-tagger"></a>Implementace osnovy Tagger  
 Osnovy oblasti jsou označené nástrojem druh značky (<xref:Microsoft.VisualStudio.Text.Tagging.OutliningRegionTag>). Tato značka poskytuje standardní osnovy chování. Oblasti popsané můžete rozbalit nebo sbalit. Popsané oblast je označena kvalifikátorem znaménko PLUS sbaleného nebo znaménkem MINUS, pokud je rozbalený a rozšířená oblast je jsou označené, svislá čára.  
  
 Následující kroky ukazují, jak definovat tagger, která vytvoří popisující oblasti pro všechny oblasti, které jsou odděleny "[" a "]".  
  
#### <a name="to-implement-an-outlining-tagger"></a>K implementaci osnovy tagger  
  
1.  Přidejte soubor třídy a pojmenujte ji `OutliningTagger`.  
  
2.  Importujte následující obory názvů.  
  
     [!code-csharp[VSSDKOutlineRegionTest#1](../extensibility/codesnippet/CSharp/walkthrough-outlining_1.cs)]
     [!code-vb[VSSDKOutlineRegionTest#1](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_1.vb)]  
  
3.  Vytvoření třídy s názvem `OutliningTagger`, a mějte ho implementovat <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601>:  
  
     [!code-csharp[VSSDKOutlineRegionTest#2](../extensibility/codesnippet/CSharp/walkthrough-outlining_2.cs)]
     [!code-vb[VSSDKOutlineRegionTest#2](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_2.vb)]  
  
4.  Přidáte některá pole ke sledování textovou vyrovnávací paměť a snímků a hromadit sady řádků, které by měl být označené jako osnova oblasti. Tento kód obsahuje seznam objektů oblast (který se má definovat později), které představují popisující oblasti.  
  
     [!code-csharp[VSSDKOutlineRegionTest#3](../extensibility/codesnippet/CSharp/walkthrough-outlining_3.cs)]
     [!code-vb[VSSDKOutlineRegionTest#3](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_3.vb)]  
  
5.  Přidat tagger konstruktor, který inicializuje pole, analyzuje vyrovnávací paměť, a přidá obslužnou rutinu události a <xref:Microsoft.VisualStudio.Text.ITextBuffer.Changed> událostí.  
  
     [!code-csharp[VSSDKOutlineRegionTest#4](../extensibility/codesnippet/CSharp/walkthrough-outlining_4.cs)]
     [!code-vb[VSSDKOutlineRegionTest#4](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_4.vb)]  
  
6.  Implementace <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601.GetTags%2A> zahrnuje metodu, která vytvoří instanci značky. Tento příklad předpokládá, že rozsahy v <xref:Microsoft.VisualStudio.Text.NormalizedSpanCollection> předaná metodě jsou souvislé, i když to nemusí být vždy případu. Tato metoda vytvoří nové značky rozpětí pro každou popisující oblastí.  
  
     [!code-csharp[VSSDKOutlineRegionTest#5](../extensibility/codesnippet/CSharp/walkthrough-outlining_5.cs)]
     [!code-vb[VSSDKOutlineRegionTest#5](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_5.vb)]  
  
7.  Deklarace `TagsChanged` obslužné rutiny události.  
  
     [!code-csharp[VSSDKOutlineRegionTest#6](../extensibility/codesnippet/CSharp/walkthrough-outlining_6.cs)]
     [!code-vb[VSSDKOutlineRegionTest#6](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_6.vb)]  
  
8.  Přidat `BufferChanged` obslužné rutiny události, která reaguje na <xref:Microsoft.VisualStudio.Text.ITextBuffer.Changed> události analýzou textová vyrovnávací paměť.  
  
     [!code-csharp[VSSDKOutlineRegionTest#7](../extensibility/codesnippet/CSharp/walkthrough-outlining_7.cs)]
     [!code-vb[VSSDKOutlineRegionTest#7](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_7.vb)]  
  
9. Přidejte metodu, která analyzuje vyrovnávací paměti. Příklad zadané v tomto poli je pouze pro ilustraci. Analyzuje synchronně vyrovnávací paměti do vnořené osnovy oblasti.  
  
     [!code-csharp[VSSDKOutlineRegionTest#8](../extensibility/codesnippet/CSharp/walkthrough-outlining_8.cs)]
     [!code-vb[VSSDKOutlineRegionTest#8](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_8.vb)]  
  
10. Následující pomocnou metodu získá celé číslo, které představuje úroveň osnovy, tak, aby 1 je pár krajní levá složená závorka.  
  
     [!code-csharp[VSSDKOutlineRegionTest#9](../extensibility/codesnippet/CSharp/walkthrough-outlining_9.cs)]
     [!code-vb[VSSDKOutlineRegionTest#9](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_9.vb)]  
  
11. Následující pomocnou metodu překládá do SnapshotSpan oblast (definovanou později v tomto tématu).  
  
     [!code-csharp[VSSDKOutlineRegionTest#10](../extensibility/codesnippet/CSharp/walkthrough-outlining_10.cs)]
     [!code-vb[VSSDKOutlineRegionTest#10](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_10.vb)]  
  
12. Následující kód je pouze pro ilustraci. Definuje třídu PartialRegion, která obsahuje číslo řádku a posun začátek popisující oblast a také odkaz na nadřazený oblast (pokud existuje). To umožňuje analyzátor nastavit vnořené osnovy oblasti. Odvozené třídy oblast obsahuje odkaz na číslo řádku konce osnovy oblast.  
  
     [!code-csharp[VSSDKOutlineRegionTest#11](../extensibility/codesnippet/CSharp/walkthrough-outlining_11.cs)]
     [!code-vb[VSSDKOutlineRegionTest#11](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_11.vb)]  
  
## <a name="implementing-a-tagger-provider"></a>Implementace zprostředkovatele Tagger  
 Je nutné exportovat tagger zprostředkovatele pro vaše tagger. Vytvoří zprostředkovatele tagger `OutliningTagger` vyrovnávací paměti obsahu typu "text", nebo jiný vrátí `OutliningTagger` Pokud vyrovnávací paměť již jeden má.  
  
#### <a name="to-implement-a-tagger-provider"></a>Pro implementaci zprostředkovatele tagger  
  
1.  Vytvoření třídy s názvem `OutliningTaggerProvider` , která implementuje <xref:Microsoft.VisualStudio.Text.Tagging.ITaggerProvider>a exportovat je s atributy ContentType a typů.  
  
     [!code-csharp[VSSDKOutlineRegionTest#12](../extensibility/codesnippet/CSharp/walkthrough-outlining_12.cs)]
     [!code-vb[VSSDKOutlineRegionTest#12](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_12.vb)]  
  
2.  Implementace <xref:Microsoft.VisualStudio.Text.Tagging.ITaggerProvider.CreateTagger%2A> metoda přidáním `OutliningTagger` na vlastnosti vyrovnávací paměti.  
  
     [!code-csharp[VSSDKOutlineRegionTest#13](../extensibility/codesnippet/CSharp/walkthrough-outlining_13.cs)]
     [!code-vb[VSSDKOutlineRegionTest#13](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_13.vb)]  
  
## <a name="building-and-testing-the-code"></a>Vytváření a testování kódu  
 K otestování tohoto kódu, sestavte řešení OutlineRegionTest a spusťte ji v experimentální instanci.  
  
#### <a name="to-build-and-test-the-outlineregiontest-solution"></a>Pro sestavení a otestování OutlineRegionTest řešení  
  
1.  Sestavte řešení.  
  
2.  Když spustíte tohoto projektu v ladicím programu, je vytvořena instance druhou instanci sady Visual Studio.  
  
3.  Vytvořte textový soubor. Zadejte text, který zahrnuje levá složená závorka i složená závorka.  
  
    ```  
    [  
       Hello  
    ]  
    ```  
  
4.  Měla by existovat popisující oblast, která obsahuje oba složené závorky. Nyní byste měli mít klikněte na tlačítko mínus nalevo od otevřete závorek na Sbalit popisující oblast. Když sbalena oblast, symbol tří teček (...) by se měla objevit nalevo od oblasti sbalené a místní okno obsahující hledaný text **najeďte text** by se měla objevit při přesunutí ukazatele myši na se třemi tečkami.  
  
## <a name="see-also"></a>Viz také  
 [Návod: Propojení typu obsahu s příponou názvu souboru](../extensibility/walkthrough-linking-a-content-type-to-a-file-name-extension.md)