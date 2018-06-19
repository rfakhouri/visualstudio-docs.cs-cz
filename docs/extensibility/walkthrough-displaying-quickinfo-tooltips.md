---
title: 'Návod: Zobrazení popisů tlačítek QuickInfo | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - QuickInfo
ms.assetid: 23fb8384-4f12-446f-977f-ce7910347947
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 81974967094d238f12141ad7cd31bcc8015b9633
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31146761"
---
# <a name="walkthrough-displaying-quickinfo-tooltips"></a>Návod: Zobrazení QuickInfo popisy tlačítek
QuickInfo je funkce technologie IntelliSense, která zobrazuje metoda podpisy a popisy, když se uživatel přesune ukazatel myši název metody. Funkce založené na jazyce jako třeba QuickInfo můžete implementovat definováním identifikátory, pro které byste chtěli poskytnout QuickInfo popisy, a pak vytvořit popisek ve kterém chcete zobrazit obsah. Můžete definovat QuickInfo v kontextu služby jazyk, nebo můžete definovat typ vlastního souboru název rozšíření a obsahu a zobrazit QuickInfo právě tohoto typu nebo můžete zobrazit QuickInfo pro existující typ obsahu (například "text"). Tento návod ukazuje, jak má být zobrazen pro typ obsahu "text" QuickInfo.  
  
 Příklad QuickInfo v tomto návodu zobrazí popisky tlačítek, když se uživatel přesunutí ukazatele myši název metody. Tento návrh vyžaduje, abyste implementovat tyto čtyři rozhraní:  
  
-   zdroj rozhraní  
  
-   zdroj rozhraní zprostředkovatele  
  
-   rozhraní řadiče  
  
-   rozhraní poskytovatele řadiče  
  
 Zprostředkovatelé zdroje a řadiče jsou součásti Managed Extensibility Framework (MEF) a jsou zodpovědní za export tříd zdroje a řadiče a importu služby a zprostředkovává, jako <xref:Microsoft.VisualStudio.Text.ITextBufferFactoryService>, která vytvoří text popisku vyrovnávací paměť a <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoBroker>, která aktivuje QuickInfo relace.  
  
 V tomto příkladu zdroji QuickInfo používá pevně zakódovaný seznam metoda názvy a popisy, ale v úplné implementace je zodpovědná za poskytování obsahu služba jazyka a dokumentace jazyk.  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-mef-project"></a>Vytvoření projektu MEF  
  
#### <a name="to-create-a-mef-project"></a>Vytvoření projektu MEF  
  
1.  Vytvoření projektu C# VSIX. (V **nový projekt** dialogovém okně, vyberte **Visual C# nebo rozšíření**, pak **projektu VSIX**.) Název řešení `QuickInfoTest`.  
  
2.  Do projektu přidejte šablony položky třídění Editor. Další informace najdete v tématu [vytváření rozšíření pomocí šablony položky Editor](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
3.  Odstraňte existující soubory třídy.  
  
## <a name="implementing-the-quickinfo-source"></a>Implementace zdroje QuickInfo  
 Zdroj QuickInfo zodpovídá za shromažďování sadu identifikátory a jejich popisy a když jeden identifikátorů došlo k přidávání obsahu do textová vyrovnávací paměť popisku. V tomto příkladu jsou identifikátory a jejich popisy právě přidali v konstruktoru zdroje.  
  
#### <a name="to-implement-the-quickinfo-source"></a>K implementaci zdroji QuickInfo  
  
1.  Přidejte soubor třídy a pojmenujte ji `TestQuickInfoSource`.  
  
2.  Přidáte odkaz na Microsoft.VisualStudio.Language.IntelliSense.  
  
3.  Přidejte následující importy.  
  
     [!code-vb[VSSDKQuickInfoTest#1](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_1.vb)]
     [!code-csharp[VSSDKQuickInfoTest#1](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_1.cs)]  
  
4.  Deklarace třídy, která implementuje <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSource>a pojmenujte ji `TestQuickInfoSource`.  
  
     [!code-vb[VSSDKQuickInfoTest#2](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_2.vb)]
     [!code-csharp[VSSDKQuickInfoTest#2](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_2.cs)]  
  
5.  Přidáte pole pro poskytovatele správy zdrojového QuickInfo, textovou vyrovnávací paměť a sadu metoda názvy a metoda podpisy. V tomto příkladu je v inicializovat metoda názvů a podpisů `TestQuickInfoSource` konstruktor.  
  
     [!code-vb[VSSDKQuickInfoTest#3](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_3.vb)]
     [!code-csharp[VSSDKQuickInfoTest#3](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_3.cs)]  
  
6.  Přidejte konstruktor, který nastaví poskytovatele správy zdrojového QuickInfo a textová vyrovnávací paměť a naplní sadu metoda názvy a metoda podpisy a popisy.  
  
     [!code-vb[VSSDKQuickInfoTest#4](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_4.vb)]
     [!code-csharp[VSSDKQuickInfoTest#4](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_4.cs)]  
  
7.  Implementace <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSource.AugmentQuickInfoSession%2A> metoda. V tomto příkladu metoda vyhledá aktuální slovo nebo slovo předchozí Pokud je kurzor na konci řádku nebo textovou vyrovnávací paměť. Pokud se jeden ze zadaných názvů metoda, popis pro tento název metody je přidán do QuickInfo obsah.  
  
     [!code-vb[VSSDKQuickInfoTest#5](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_5.vb)]
     [!code-csharp[VSSDKQuickInfoTest#5](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_5.cs)]  
  
8.  Musíte také implementovat metodu Dispose(), protože <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSource> implementuje <xref:System.IDisposable>:  
  
     [!code-vb[VSSDKQuickInfoTest#6](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_6.vb)]
     [!code-csharp[VSSDKQuickInfoTest#6](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_6.cs)]  
  
## <a name="implementing-a-quickinfo-source-provider"></a>Implementace zprostředkovatele QuickInfo zdroje  
 Zprostředkovatel zdroje QuickInfo slouží především pro export sám sebe jako součást MEF a vytvoření instance zdroji QuickInfo. Protože je součástí MEF součásti, můžete importovat dalších částí rozhraní MEF součásti.  
  
#### <a name="to-implement-a-quickinfo-source-provider"></a>Pro implementaci zprostředkovatele QuickInfo zdroje  
  
1.  Deklarovat QuickInfo poskytovatele zdroj s názvem `TestQuickInfoSourceProvider` , která implementuje <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSourceProvider>a exportovat je s <xref:Microsoft.VisualStudio.Utilities.NameAttribute> "Popisek QuickInfo zdroje", <xref:Microsoft.VisualStudio.Utilities.OrderAttribute> z před = "Výchozí" a <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "text".  
  
     [!code-vb[VSSDKQuickInfoTest#7](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_7.vb)]
     [!code-csharp[VSSDKQuickInfoTest#7](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_7.cs)]  
  
2.  Import dvě editor služby <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService> a <xref:Microsoft.VisualStudio.Text.ITextBufferFactoryService>, jako vlastnosti `TestQuickInfoSourceProvider`.  
  
     [!code-vb[VSSDKQuickInfoTest#8](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_8.vb)]
     [!code-csharp[VSSDKQuickInfoTest#8](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_8.cs)]  
  
3.  Implementace <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSourceProvider.TryCreateQuickInfoSource%2A> vrátit novou `TestQuickInfoSource`.  
  
     [!code-vb[VSSDKQuickInfoTest#9](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_9.vb)]
     [!code-csharp[VSSDKQuickInfoTest#9](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_9.cs)]  
  
## <a name="implementing-a-quickinfo-controller"></a>Implementace řadič QuickInfo  
 QuickInfo řadiče určují, kdy má být zobrazena QuickInfo. V tomto příkladu QuickInfo se zobrazí, když ukazatel myši nad slovo, které odpovídá jeden ze zadaných názvů metoda. Řadič QuickInfo implementuje obslužnou rutinu události při přechodu myší, která aktivuje relaci QuickInfo.  
  
#### <a name="to-implement-a-quickinfo-controller"></a>K implementaci řadič QuickInfo  
  
1.  Deklarace třídy, která implementuje <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseController>a pojmenujte ji `TestQuickInfoController`.  
  
     [!code-vb[VSSDKQuickInfoTest#10](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_10.vb)]
     [!code-csharp[VSSDKQuickInfoTest#10](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_10.cs)]  
  
2.  Přidáte privátní pole pro zobrazení textu textové vyrovnávací paměti v textového zobrazení, QuickInfo relace a zprostředkovatele QuickInfo kontroleru.  
  
     [!code-vb[VSSDKQuickInfoTest#11](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_11.vb)]
     [!code-csharp[VSSDKQuickInfoTest#11](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_11.cs)]  
  
3.  Přidejte konstruktor, který nastaví pole a přidá obslužné rutiny události při přechodu myší.  
  
     [!code-vb[VSSDKQuickInfoTest#12](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_12.vb)]
     [!code-csharp[VSSDKQuickInfoTest#12](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_12.cs)]  
  
4.  Přidejte obslužné rutiny události myši hover, která aktivuje QuickInfo relace.  
  
     [!code-vb[VSSDKQuickInfoTest#13](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_13.vb)]
     [!code-csharp[VSSDKQuickInfoTest#13](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_13.cs)]  
  
5.  Implementace <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseController.Detach%2A> metody, které se odstraní obslužné rutiny události myši hover řadičem odpojený od textového zobrazení.  
  
     [!code-vb[VSSDKQuickInfoTest#14](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_14.vb)]
     [!code-csharp[VSSDKQuickInfoTest#14](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_14.cs)]  
  
6.  Implementace <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseController.ConnectSubjectBuffer%2A> metoda a <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseController.DisconnectSubjectBuffer%2A> metoda jako prázdný metody v tomto příkladu.  
  
     [!code-vb[VSSDKQuickInfoTest#15](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_15.vb)]
     [!code-csharp[VSSDKQuickInfoTest#15](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_15.cs)]  
  
## <a name="implementing-the-quickinfo-controller-provider"></a>Implementace zprostředkovatele QuickInfo řadiče  
 Zprostředkovatel řadiče QuickInfo slouží především k samotné exportovat jako součást MEF a vytvoření instancí kontroleru QuickInfo. Protože je součástí MEF součásti, můžete importovat dalších částí rozhraní MEF součásti.  
  
#### <a name="to-implement-the-quickinfo-controller-provider"></a>Implementace zprostředkovatele QuickInfo kontroleru  
  
1.  Deklarace třídy s názvem `TestQuickInfoControllerProvider` , která implementuje <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseControllerProvider>a exportovat je s <xref:Microsoft.VisualStudio.Utilities.NameAttribute> "Popisek QuickInfo řadiče" a <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "text":  
  
     [!code-vb[VSSDKQuickInfoTest#16](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_16.vb)]
     [!code-csharp[VSSDKQuickInfoTest#16](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_16.cs)]  
  
2.  Import <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoBroker> jako vlastnost.  
  
     [!code-vb[VSSDKQuickInfoTest#17](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_17.vb)]
     [!code-csharp[VSSDKQuickInfoTest#17](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_17.cs)]  
  
3.  Implementace <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseControllerProvider.TryCreateIntellisenseController%2A> metoda po vytvoření instance kontroleru QuickInfo.  
  
     [!code-vb[VSSDKQuickInfoTest#18](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_18.vb)]
     [!code-csharp[VSSDKQuickInfoTest#18](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_18.cs)]  
  
## <a name="building-and-testing-the-code"></a>Vytváření a testování kódu  
 K otestování tohoto kódu, sestavte řešení QuickInfoTest a spusťte ji v experimentální instanci.  
  
#### <a name="to-build-and-test-the-quickinfotest-solution"></a>Pro sestavení a otestování QuickInfoTest řešení  
  
1.  Sestavte řešení.  
  
2.  Když spustíte tohoto projektu v ladicím programu, je vytvořena instance druhou instanci sady Visual Studio.  
  
3.  Vytvořte textový soubor a typ některé text, který obsahuje slova "Přidat" a "odečtena".  
  
4.  Přesuňte ukazatel myši nad jednu z výskytů "Přidat". Podpis a popis `add` metoda má být zobrazen.  
  
## <a name="see-also"></a>Viz také  
 [Návod: Propojení typu obsahu s příponou názvu souboru](../extensibility/walkthrough-linking-a-content-type-to-a-file-name-extension.md)