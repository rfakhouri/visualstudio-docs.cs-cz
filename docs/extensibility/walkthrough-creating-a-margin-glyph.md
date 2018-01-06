---
title: "Návod: Vytvoření glyf okraj | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], new - margin glyph
ms.assetid: 814185db-24f9-417f-b3b1-7c5aabb42b45
caps.latest.revision: "29"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: fc813ed3c29c2fe0a4cac1c348ffed18ae8fd2d2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-a-margin-glyph"></a>Návod: Vytvoření glyf rozpětí
Pomocí vlastního editoru rozšíření můžete přizpůsobit vzhled okraje editoru. Tento názorný postup vlastní glyf umístí na okraj indikátoru vždy, když je slovo "todo" se zobrazí v komentář ke kódu.  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-mef-project"></a>Vytvoření projektu MEF  
  
1.  Vytvoření projektu C# VSIX. (V **nový projekt** dialogovém okně, vyberte **Visual C# nebo rozšíření**, pak **projektu VSIX**.) Název řešení `TodoGlyphTest`.  
  
2.  Přidání položky projektu třídění Editor. Další informace najdete v tématu [vytváření rozšíření pomocí šablony položky Editor](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
3.  Odstraňte existující soubory třídy.  
  
## <a name="defining-the-glyph"></a>Definování glyf  
 Definujte glyf implementací <xref:Microsoft.VisualStudio.Text.Editor.IGlyphFactory> rozhraní.  
  
#### <a name="to-define-the-glyph"></a>Chcete-li definovat glyf  
  
1.  Přidejte soubor třídy a pojmenujte ji `TodoGlyphFactory`.  
  
2.  Přidejte následující pomocí deklarace.  
  
     [!code-csharp[VSSDKTodoGlyphTest#1](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_1.cs)]
     [!code-vb[VSSDKTodoGlyphTest#1](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_1.vb)]  
  
3.  Přidejte třídu s názvem `TodoGlyphFactory` , která implementuje <xref:Microsoft.VisualStudio.Text.Editor.IGlyphFactory>.  
  
     [!code-csharp[VSSDKTodoGlyphTest#2](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_2.cs)]
     [!code-vb[VSSDKTodoGlyphTest#2](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_2.vb)]  
  
4.  Přidejte privátní pole, které definuje dimenze glyfu.  
  
     [!code-csharp[VSSDKTodoGlyphTest#3](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_3.cs)]
     [!code-vb[VSSDKTodoGlyphTest#3](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_3.vb)]  
  
5.  Implementace `GenerateGlyph` definováním element glyfy uživatelského rozhraní (UI). `TodoTag`dále v tomto návodu je definována.  
  
     [!code-csharp[VSSDKTodoGlyphTest#4](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_4.cs)]
     [!code-vb[VSSDKTodoGlyphTest#4](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_4.vb)]  
  
6.  Přidejte třídu s názvem `TodoGlyphFactoryProvider` , která implementuje <xref:Microsoft.VisualStudio.Text.Editor.IGlyphFactoryProvider>. Export Tato třída se <xref:Microsoft.VisualStudio.Utilities.NameAttribute> z "TodoGlyph" <xref:Microsoft.VisualStudio.Utilities.OrderAttribute> z po VsTextMarker <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "kódu" a <xref:Microsoft.VisualStudio.Text.Tagging.TagTypeAttribute> z TodoTag.  
  
     [!code-csharp[VSSDKTodoGlyphTest#5](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_5.cs)]
     [!code-vb[VSSDKTodoGlyphTest#5](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_5.vb)]  
  
7.  Implementace <xref:Microsoft.VisualStudio.Text.Editor.IGlyphFactoryProvider.GetGlyphFactory%2A> metoda po vytvoření instance `TodoGlyphFactory`.  
  
     [!code-csharp[VSSDKTodoGlyphTest#6](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_6.cs)]
     [!code-vb[VSSDKTodoGlyphTest#6](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_6.vb)]  
  
## <a name="defining-a-todo-tag-and-tagger"></a>Definování Todo značky a Tagger  
 Definování vztahů mezi element uživatelského rozhraní, který jste definovali v předchozích krocích a okraj indikátoru vytvořením typ značky a tagger a export pomocí tagger poskytovatele.  
  
#### <a name="to-define-a-todo-tag-and-tagger"></a>Chcete-li definovat todo značky a tagger  
  
1.  Přidejte nový soubor třídu do projektu a pojmenujte ji `TodoTagger`.  
  
2.  Přidejte následující importy.  
  
     [!code-csharp[VSSDKTodoGlyphTest#7](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_7.cs)]
     [!code-vb[VSSDKTodoGlyphTest#7](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_7.vb)]  
  
3.  Přidejte třídu s názvem `TodoTag`.  
  
     [!code-csharp[VSSDKTodoGlyphTest#8](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_8.cs)]
     [!code-vb[VSSDKTodoGlyphTest#8](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_8.vb)]  
  
4.  Upravit třída s názvem `TodoTagger` , která implementuje <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601> typu `TodoTag`.  
  
     [!code-csharp[VSSDKTodoGlyphTest#9](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_9.cs)]
     [!code-vb[VSSDKTodoGlyphTest#9](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_9.vb)]  
  
5.  K `TodoTagger` třídy, přidejte soukromé pole pro <xref:Microsoft.VisualStudio.Text.Classification.IClassifier> a text k vyhledání v příslušné klasifikaci zahrnuje.  
  
     [!code-csharp[VSSDKTodoGlyphTest#10](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_10.cs)]
     [!code-vb[VSSDKTodoGlyphTest#10](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_10.vb)]  
  
6.  Přidejte konstruktor, který nastaví třídění.  
  
     [!code-csharp[VSSDKTodoGlyphTest#11](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_11.cs)]
     [!code-vb[VSSDKTodoGlyphTest#11](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_11.vb)]  
  
7.  Implementace <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601.GetTags%2A> metoda tak, že najdete všechny klasifikace zahrnuje, jejichž názvy použít slovo "komentář" a jejíž text obsahuje hledaný text. Vždy, když je nalezen text vyhledávání, yield zpět novou <xref:Microsoft.VisualStudio.Text.Tagging.TagSpan%601> typu `TodoTag`.  
  
     [!code-csharp[VSSDKTodoGlyphTest#12](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_12.cs)]
     [!code-vb[VSSDKTodoGlyphTest#12](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_12.vb)]  
  
8.  Deklarace `TagsChanged` událostí.  
  
     [!code-csharp[VSSDKTodoGlyphTest#13](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_13.cs)]
     [!code-vb[VSSDKTodoGlyphTest#13](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_13.vb)]  
  
9. Přidejte třídu s názvem `TodoTaggerProvider` , která implementuje <xref:Microsoft.VisualStudio.Text.Tagging.ITaggerProvider>a exportovat je s <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "kódu" a <xref:Microsoft.VisualStudio.Text.Tagging.TagTypeAttribute> z TodoTag.  
  
     [!code-csharp[VSSDKTodoGlyphTest#14](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_14.cs)]
     [!code-vb[VSSDKTodoGlyphTest#14](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_14.vb)]  
  
10. Import <xref:Microsoft.VisualStudio.Text.Classification.IClassifierAggregatorService>.  
  
     [!code-csharp[VSSDKTodoGlyphTest#15](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_15.cs)]
     [!code-vb[VSSDKTodoGlyphTest#15](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_15.vb)]  
  
11. Implementace <xref:Microsoft.VisualStudio.Text.Tagging.ITaggerProvider.CreateTagger%2A> metoda po vytvoření instance `TodoTagger`.  
  
     [!code-csharp[VSSDKTodoGlyphTest#16](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_16.cs)]
     [!code-vb[VSSDKTodoGlyphTest#16](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_16.vb)]  
  
## <a name="building-and-testing-the-code"></a>Vytváření a testování kódu  
 K otestování tohoto kódu, sestavte řešení TodoGlyphTest a spusťte ji v experimentální instanci.  
  
#### <a name="to-build-and-test-the-todoglyphtest-solution"></a>Pro sestavení a otestování TodoGlyphTest řešení  
  
1.  Sestavte řešení.  
  
2.  Stisknutím klávesy F5 spusťte projekt. Vytvoření instance druhou instanci sady Visual Studio.  
  
3.  Ujistěte se, že se zobrazuje indikátor okraj. (Na **nástroje** nabídky, klikněte na tlačítko **možnosti**. Na **textového editoru** stránky, ujistěte se, že **okraj indikátoru** je vybrána.)  
  
4.  Otevření souboru kódu, který má komentáře. Přidáte slovo "úkolů" pro jeden z oddílů komentář.  
  
5.  Světla blue kruh, který má tmavý blue obrys by se zobrazit v indikátoru okraj na levé straně okna kódu.