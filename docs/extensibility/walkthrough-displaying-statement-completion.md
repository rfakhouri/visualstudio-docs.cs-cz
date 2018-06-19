---
title: 'Návod: Zobrazení dokončování | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - statement completion
ms.assetid: f3152c4e-7673-4047-a079-2326941d1c83
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bbdc79275dd99c502533c82665741b84620be928
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31147112"
---
# <a name="walkthrough-displaying-statement-completion"></a>Návod: Zobrazení dokončování příkazů
Na základě jazyka dokončování můžete implementovat definováním identifikátory, pro které byste chtěli poskytnout dokončení a potom aktivuje relaci dokončení. Můžete definovat dokončování v kontextu služby jazyk, definovat vlastní příponu názvu souboru a typu obsahu a následně se zobrazí dokončení právě tohoto typu nebo můžete aktivovat dokončení pro existující typ obsahu – například prostý text"". Tento návod ukazuje, jak aktivovat dokončování pro typ obsahu "prostý text", což je typ obsahu textových souborů. Typ obsahu "text" je nadřazeného všechny ostatní typy obsahu, včetně kódu a soubory XML.  
  
 Dokončování příkazů, které se obvykle aktivuje tak, že zadáte některé znaky – například zadáním začátku identifikátor například "pomocí". Toto pravidlo se zavře obvykle po stisknutí klávesy MEZERNÍK, tabulátor nebo Enter k potvrzení výběr. Můžete implementovat funkce IntelliSense, které se spouštějí zadáním znak pomocí obslužná rutina příkazu stisknutí kláves ( <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní) a zprostředkovatele obslužná rutina, která implementuje <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener> rozhraní. Vytvoření zdroje dokončení, což je seznam identifikátorů, které jsou součástí dokončení, implementovat <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSource> rozhraní a dokončení zdroj zprostředkovatele ( <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSourceProvider> rozhraní). Zprostředkovatele jsou součásti Managed Extensibility Framework (MEF). Odpovídají pro třídy zdroje a řadič export a import služeb a zprostředkovatelé – například <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService>, což umožňuje navigace ve textová vyrovnávací paměť a <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionBroker>, která aktivuje dokončení relace.  
  
 Tento návod ukazuje, jak implementovat dokončování pro sadu pevně identifikátorů. V úplné implementacích je zodpovědná za poskytování obsahu služba jazyka a dokumentace jazyk.  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-mef-project"></a>Vytvoření projektu MEF  
  
#### <a name="to-create-a-mef-project"></a>Vytvoření projektu MEF  
  
1.  Vytvoření projektu C# VSIX. (V **nový projekt** dialogovém okně, vyberte **Visual C# nebo rozšíření**, pak **projektu VSIX**.) Název řešení `CompletionTest`.  
  
2.  Do projektu přidejte šablony položky třídění Editor. Další informace najdete v tématu [vytváření rozšíření pomocí šablony položky Editor](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
3.  Odstraňte existující soubory třídy.  
  
4.  Přidejte následující odkazy na projekt a ujistěte se, že **CopyLocal** je nastaven na `false`:  
  
     Microsoft.VisualStudio.Editor  
  
     Microsoft.VisualStudio.Language.Intellisense  
  
     Sestavení Microsoft.VisualStudio.OLE.Interop  
  
     Microsoft.VisualStudio.Shell.14.0  
  
     Microsoft.VisualStudio.Shell.Immutable.10.0  
  
     Microsoft.VisualStudio.TextManager.Interop  
  
## <a name="implementing-the-completion-source"></a>Implementace zdroje dokončení  
 Zdroj dokončení je zodpovědná za sadu identifikátory shromažďování a přidávat obsah do okna dokončení, pokud uživatel zadá aktivační událost dokončení, například první písmena identifikátoru. V tomto příkladu, identifikátory a jejich popisy jsou pevně zakódovaná ve <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSource.AugmentCompletionSession%2A> metoda. Ve většině reálného používá využije se získat token k naplnění seznamu dokončení analyzátor svůj jazyk.  
  
#### <a name="to-implement-the-completion-source"></a>K implementaci zdroji dokončení  
  
1.  Přidejte soubor třídy a pojmenujte ji `TestCompletionSource`.  
  
2.  Přidejte tyto importy:  
  
     [!code-csharp[VSSDKCompletionTest#1](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_1.cs)]
     [!code-vb[VSSDKCompletionTest#1](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_1.vb)]  
  
3.  Upravit deklaraci třídy pro `TestCompletionSource` tak, aby se implementuje <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSource>:  
  
     [!code-csharp[VSSDKCompletionTest#2](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_2.cs)]
     [!code-vb[VSSDKCompletionTest#2](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_2.vb)]  
  
4.  Přidání privátním polím pro poskytovatele správy zdrojového textová vyrovnávací paměť a seznam <xref:Microsoft.VisualStudio.Language.Intellisense.Completion> objekty (které odpovídají identifikátory, které budou součástí relace dokončení):  
  
     [!code-csharp[VSSDKCompletionTest#3](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_3.cs)]
     [!code-vb[VSSDKCompletionTest#3](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_3.vb)]  
  
5.  Přidejte konstruktor, který nastaví Zprostředkovatel zdroje a vyrovnávací paměti. `TestCompletionSourceProvider` Třída definovaná v následujících krocích:  
  
     [!code-csharp[VSSDKCompletionTest#4](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_4.cs)]
     [!code-vb[VSSDKCompletionTest#4](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_4.vb)]  
  
6.  Implementace <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSource.AugmentCompletionSession%2A> metoda přidáním dokončení sadu, která obsahuje dokončených, kterou chcete přidat v kontextu. Každá sada dokončení obsahuje sadu <xref:Microsoft.VisualStudio.Language.Intellisense.Completion> dokončených a že odpovídá na kartě okna dokončení. (V projektech Visual Basic, jsou pojmenované okno karty dokončení **běžné** a **všechny**.) Metoda FindTokenSpanAtPosition je definována v dalším kroku.  
  
     [!code-csharp[VSSDKCompletionTest#5](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_5.cs)]
     [!code-vb[VSSDKCompletionTest#5](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_5.vb)]  
  
7.  Následující metodu je použít k vyhledání aktuální slovo od pozice kurzoru:  
  
     [!code-csharp[VSSDKCompletionTest#6](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_6.cs)]
     [!code-vb[VSSDKCompletionTest#6](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_6.vb)]  
  
8.  Implementace `Dispose()` metoda:  
  
     [!code-csharp[VSSDKCompletionTest#7](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_7.cs)]
     [!code-vb[VSSDKCompletionTest#7](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_7.vb)]  
  
## <a name="implementing-the-completion-source-provider"></a>Implementace zprostředkovatele zdroj dokončení  
 Zprostředkovatel zdroje dokončení je část MEF součást, která vytvoří instanci zdroji dokončení.  
  
#### <a name="to-implement-the-completion-source-provider"></a>K implementaci poskytovatele správy zdrojového dokončení  
  
1.  Přidejte třídu s názvem `TestCompletionSourceProvider` , která implementuje <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSourceProvider>. Tato třída se exportovat <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "prostého textu" a <xref:Microsoft.VisualStudio.Utilities.NameAttribute> "dokončení testu".  
  
     [!code-csharp[VSSDKCompletionTest#8](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_8.cs)]
     [!code-vb[VSSDKCompletionTest#8](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_8.vb)]  
  
2.  Import <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService>, který se používá k vyhledání aktuální aplikace word ve zdroji dokončení.  
  
     [!code-csharp[VSSDKCompletionTest#9](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_9.cs)]
     [!code-vb[VSSDKCompletionTest#9](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_9.vb)]  
  
3.  Implementace <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSourceProvider.TryCreateCompletionSource%2A> metoda pro vytvoření instance zdroji dokončení.  
  
     [!code-csharp[VSSDKCompletionTest#10](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_10.cs)]
     [!code-vb[VSSDKCompletionTest#10](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_10.vb)]  
  
## <a name="implementing-the-completion-command-handler-provider"></a>Implementace zprostředkovatele dokončení příkazu obslužné rutiny  
 Zprostředkovateli dokončení příkazu obslužná rutina je odvozený od <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener>, který přijímá události vytváření zobrazení textu a převede zobrazení <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>– což umožňuje přidání příkazu řetězu příkazového prostředí sady Visual Studio – k <xref:Microsoft.VisualStudio.Text.Editor.ITextView>. Vzhledem k tomu, že tato třída je export rozhraní MEF, můžete ji použít i k importu služby, které jsou vyžadované obslužná rutina sám sebe.  
  
#### <a name="to-implement-the-completion-command-handler-provider"></a>Pro implementaci zprostředkovatele dokončení příkazu obslužné rutiny  
  
1.  Přidejte soubor s názvem `TestCompletionCommandHandler`.  
  
2.  Přidejte tyto příkazy:  
  
     [!code-csharp[VSSDKCompletionTest#11](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_11.cs)]
     [!code-vb[VSSDKCompletionTest#11](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_11.vb)]  
  
3.  Přidejte třídu s názvem `TestCompletionHandlerProvider` , která implementuje <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener>. Tato třída se exportovat <xref:Microsoft.VisualStudio.Utilities.NameAttribute> "token dokončení obslužné rutiny", <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "prostého textu" a <xref:Microsoft.VisualStudio.Text.Editor.TextViewRoleAttribute> z <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles.Editable>.  
  
     [!code-csharp[VSSDKCompletionTest#12](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_12.cs)]
     [!code-vb[VSSDKCompletionTest#12](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_12.vb)]  
  
4.  Import <xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService>, což umožňuje převod <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> k <xref:Microsoft.VisualStudio.Text.Editor.ITextView>, <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionBroker>a <xref:Microsoft.VisualStudio.Shell.SVsServiceProvider> umožňující přístup ke službám standardní sady Visual Studio.  
  
     [!code-csharp[VSSDKCompletionTest#13](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_13.cs)]
     [!code-vb[VSSDKCompletionTest#13](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_13.vb)]  
  
5.  Implementace <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener.VsTextViewCreated%2A> metoda pro vytvoření instance obslužná rutina příkazu.  
  
     [!code-csharp[VSSDKCompletionTest#14](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_14.cs)]
     [!code-vb[VSSDKCompletionTest#14](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_14.vb)]  
  
## <a name="implementing-the-completion-command-handler"></a>Implementace dokončení obslužná rutina  
 Protože dokončování se aktivuje při stisknutí kláves, je nutné implementovat <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní přijímat a zpracovávat stisknutí kláves, které aktivují, potvrzení a zavření relace dokončení.  
  
#### <a name="to-implement-the-completion-command-handler"></a>K implementaci dokončení obslužná rutina  
  
1.  Přidejte třídu s názvem `TestCompletionCommandHandler` , která implementuje <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>:  
  
     [!code-csharp[VSSDKCompletionTest#15](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_15.cs)]
     [!code-vb[VSSDKCompletionTest#15](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_15.vb)]  
  
2.  Přidejte soukromé pole pro další obslužná rutina (ke které předáte příkaz), textového zobrazení, poskytovateli obslužná rutina příkazu (který umožňuje přístup k různým službám) a dokončení relace:  
  
     [!code-csharp[VSSDKCompletionTest#16](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_16.cs)]
     [!code-vb[VSSDKCompletionTest#16](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_16.vb)]  
  
3.  Přidejte konstruktor, který nastaví textového zobrazení a pole zprostředkovatele a přidá příkaz řetězu příkaz:  
  
     [!code-csharp[VSSDKCompletionTest#17](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_17.cs)]
     [!code-vb[VSSDKCompletionTest#17](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_17.vb)]  
  
4.  Implementace <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metoda předáním příkaz podél:  
  
     [!code-csharp[VSSDKCompletionTest#18](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_18.cs)]
     [!code-vb[VSSDKCompletionTest#18](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_18.vb)]  
  
5.  Implementace <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> metoda. Když tato metoda obdrží stisknutí klávesy, ho musíte udělat jednu z těchto věcí:  
  
    -   Povolit znak, který má být zapsána do vyrovnávací paměti a potom aktivovat nebo filtrovat dokončení. (Tisk znaků to provést.)  
  
    -   Potvrdit dokončení, ale zakázat znak, který má být zapsána do vyrovnávací paměti. (Prázdný znak, karta a zadejte to provést při dokončení relace zobrazí.)  
  
    -   Povolte příkaz mají být předány další obslužná rutina. (Všechny ostatní příkazy.)  
  
     Vzhledem k tomu, že tato metoda může zobrazit uživatelské rozhraní, volání <xref:Microsoft.VisualStudio.Shell.VsShellUtilities.IsInAutomationFunction%2A> a ujistěte se, že není volat v kontextu automatizace:  
  
     [!code-csharp[VSSDKCompletionTest#19](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_19.cs)]
     [!code-vb[VSSDKCompletionTest#19](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_19.vb)]  
  
6.  Tento kód je soukromá metoda, která aktivuje dokončení relace:  
  
     [!code-csharp[VSSDKCompletionTest#20](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_20.cs)]
     [!code-vb[VSSDKCompletionTest#20](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_20.vb)]  
  
7.  V dalším příkladu je soukromá metoda, která odhlásí <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseSession.Dismissed> událostí:  
  
     [!code-csharp[VSSDKCompletionTest#21](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_21.cs)]
     [!code-vb[VSSDKCompletionTest#21](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_21.vb)]  
  
## <a name="building-and-testing-the-code"></a>Vytváření a testování kódu  
 K otestování tohoto kódu, sestavte řešení CompletionTest a spusťte ji v experimentální instanci.  
  
#### <a name="to-build-and-test-the-completiontest-solution"></a>Pro sestavení a otestování CompletionTest řešení  
  
1.  Sestavte řešení.  
  
2.  Když spustíte tohoto projektu v ladicím programu, je vytvořena instance druhou instanci sady Visual Studio.  
  
3.  Vytvoření textového souboru a zadejte nějaký text, který obsahuje slovo "Přidat".  
  
4.  Jak budete zadávat nejprve "a" a potom "d", seznamu, který obsahuje "Přidání" a "přizpůsobení" budou zobrazeny. Všimněte si, že je vybraný přidání. Když zadáte jiný "d", seznamu by měl obsahovat pouze "Přidání", která je teď vybrána. Můžete potvrdit "Přidání" po stisknutí klávesy MEZERNÍK, tabulátor nebo Enter nebo zavření seznamu zadáním Esc nebo jiného klíče.  
  
## <a name="see-also"></a>Viz také  
 [Návod: Propojení typu obsahu s příponou názvu souboru](../extensibility/walkthrough-linking-a-content-type-to-a-file-name-extension.md)