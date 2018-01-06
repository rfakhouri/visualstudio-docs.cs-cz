---
title: "Návod: Zobrazení nápovědy podpis | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], new - signature help/parameter info
ms.assetid: 4a6a884b-5730-4b54-9264-99684f5b523c
caps.latest.revision: "28"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: ced0eb5d3545a75ee31cff55d0e4fb9dab8c8bcb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-displaying-signature-help"></a>Návod: Zobrazení nápovědy podpis
Podpis nápovědy (také označované jako *informace o parametrech*) zobrazí podpis metody ve formě popisu tlačítka, když uživatel zadá parametr seznamu úvodní znak (obvykle levé závorky). Jako parametr a parametr oddělovače (obvykle čárkou) jsou zadali, je aktualizována popisek na další parametr tučným písmem. Podpis pomoci můžete definovat v kontextu služby jazyk, nebo můžete definovat typ vlastního souboru název rozšíření a obsahu a zobrazit nápovědu k podpisu pro právě tento typ, nebo můžete zobrazit podpis pomoci pro existující typ obsahu (například "text"). Tento návod ukazuje, jak zobrazit nápovědu k podpisu pro typ obsahu "text".  
  
 Podpis nápovědy se obvykle aktivuje zadáním konkrétní znak, například "(" (levé závorky) a zavře zadáním jiné znak, například ")" (zavření závorky). Funkce IntelliSense, které se spouštějí zadáním znak můžete implementovat pomocí obslužná rutina příkazu stisknutí kláves ( <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní) a zprostředkovatele obslužná rutina, která implementuje <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener> rozhraní. Chcete-li vytvořit podpis pomoci zdroj, který je seznam podpisy, které jsou součástí podpis pomoci, implementovat <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSource> rozhraní a Zprostředkovatel zdroje, který implementuje <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSourceProvider> rozhraní. Zprostředkovatele jsou součásti Managed Extensibility Framework (MEF) a jsou zodpovědní za třídy zdroje a řadič exportu a importu služby a zprostředkovatelé, například <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService>, které lze přejít v textová vyrovnávací paměť a <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpBroker>, která aktivuje podpis pomoci relace.  
  
 Tento návod ukazuje, jak implementovat podpis pomoci pro sadu pevně identifikátorů. V úplné implementacích jazyk zodpovídá za poskytování obsahu.  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-mef-project"></a>Vytvoření projektu MEF  
  
#### <a name="to-create-a-mef-project"></a>Vytvoření projektu MEF  
  
1.  Vytvoření projektu C# VSIX. (V **nový projekt** dialogovém okně, vyberte **Visual C# nebo rozšíření**, pak **projektu VSIX**.) Název řešení `SignatureHelpTest`.  
  
2.  Do projektu přidejte šablony položky třídění Editor. Další informace najdete v tématu [vytváření rozšíření pomocí šablony položky Editor](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
3.  Odstraňte existující soubory třídy.  
  
4.  Přidejte následující odkazy na projekt a zajistěte, aby **CopyLocal** je nastaven na `false`:  
  
     Microsoft.VisualStudio.Editor  
  
     Microsoft.VisualStudio.Language.Intellisense  
  
     Sestavení Microsoft.VisualStudio.OLE.Interop  
  
     Microsoft.VisualStudio.Shell.14.0  
  
     Microsoft.VisualStudio.TextManager.Interop  
  
## <a name="implementing-signature-help-signatures-and-parameters"></a>Implementace podpis podpisy a parametry  
 Zdroj podpis pomoci je založena na podpisy, které implementují <xref:Microsoft.VisualStudio.Language.Intellisense.ISignature>, z nichž každý obsahuje parametry, které implementují <xref:Microsoft.VisualStudio.Language.Intellisense.IParameter>. V úplnou implementaci tyto informace by byl získán z dokumentace jazyk, ale v tomto příkladu jsou pevně zakódovaná podpisů.  
  
#### <a name="to-implement-the-signature-help-signatures-and-parameters"></a>K implementaci podpis pomoci podpisů a parametry  
  
1.  Přidejte soubor třídy a pojmenujte ji `SignatureHelpSource`.  
  
2.  Přidejte následující importy.  
  
     [!code-vb[VSSDKSignatureHelpTest#1](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_1.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#1](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_1.cs)]  
  
3.  Přidejte třídu s názvem `TestParameter` , která implementuje <xref:Microsoft.VisualStudio.Language.Intellisense.IParameter>.  
  
     [!code-vb[VSSDKSignatureHelpTest#2](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_2.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#2](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_2.cs)]  
  
4.  Přidejte konstruktor, který nastaví všechny vlastnosti.  
  
     [!code-vb[VSSDKSignatureHelpTest#3](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_3.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#3](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_3.cs)]  
  
5.  Přidání vlastnosti <xref:Microsoft.VisualStudio.Language.Intellisense.IParameter>.  
  
     [!code-vb[VSSDKSignatureHelpTest#4](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_4.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#4](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_4.cs)]  
  
6.  Přidejte třídu s názvem `TestSignature` , která implementuje <xref:Microsoft.VisualStudio.Language.Intellisense.ISignature>.  
  
     [!code-vb[VSSDKSignatureHelpTest#5](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_5.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#5](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_5.cs)]  
  
7.  Přidejte do něj privátní pole.  
  
     [!code-vb[VSSDKSignatureHelpTest#6](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_6.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#6](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_6.cs)]  
  
8.  Přidejte konstruktor, který nastaví pole a přihlásí k odběru <xref:Microsoft.VisualStudio.Text.ITextBuffer.Changed> událostí.  
  
     [!code-vb[VSSDKSignatureHelpTest#7](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_7.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#7](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_7.cs)]  
  
9. Deklarace `CurrentParameterChanged` událostí. Tato událost se vyvolá, když uživatel vyplní jeden z parametrů v podpisu.  
  
     [!code-vb[VSSDKSignatureHelpTest#8](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_8.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#8](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_8.cs)]  
  
10. Implementace <xref:Microsoft.VisualStudio.Language.Intellisense.ISignature.CurrentParameter%2A> vlastnosti, které se vyvolá `CurrentParameterChanged` události při změně hodnoty vlastnosti.  
  
     [!code-vb[VSSDKSignatureHelpTest#9](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_9.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#9](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_9.cs)]  
  
11. Přidejte metodu, která vyvolává `CurrentParameterChanged` událostí.  
  
     [!code-vb[VSSDKSignatureHelpTest#10](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_10.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#10](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_10.cs)]  
  
12. Přidejte metodu, která vypočítá aktuální parametr tak, že porovnáte počet čárkami v <xref:Microsoft.VisualStudio.Language.Intellisense.ISignature.ApplicableToSpan%2A> počtu čárkami v podpisu.  
  
     [!code-vb[VSSDKSignatureHelpTest#11](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_11.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#11](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_11.cs)]  
  
13. Přidání obslužné rutiny události pro <xref:Microsoft.VisualStudio.Text.ITextBuffer.Changed> událost, která se volá `ComputeCurrentParameter()` metoda.  
  
     [!code-vb[VSSDKSignatureHelpTest#12](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_12.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#12](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_12.cs)]  
  
14. Implementace <xref:Microsoft.VisualStudio.Language.Intellisense.ISignature.ApplicableToSpan%2A> vlastnost. Tato vlastnost obsahuje <xref:Microsoft.VisualStudio.Text.ITrackingSpan> odpovídající rozpětí textu ve vyrovnávací paměti, pro kterou platí podpis.  
  
     [!code-vb[VSSDKSignatureHelpTest#13](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_13.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#13](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_13.cs)]  
  
15. Implementujte další parametry.  
  
     [!code-vb[VSSDKSignatureHelpTest#14](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_14.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#14](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_14.cs)]  
  
## <a name="implementing-the-signature-help-source"></a>Implementace zdroje nápovědy podpis  
 Zdroj podpis pomoci je sada podpisy, pro které je zadat informace.  
  
#### <a name="to-implement-the-signature-help-source"></a>K implementaci zdroji podpis pomoci  
  
1.  Přidejte třídu s názvem `TestSignatureHelpSource` , která implementuje <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSource>.  
  
     [!code-vb[VSSDKSignatureHelpTest#15](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_15.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#15](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_15.cs)]  
  
2.  Přidáte odkaz na textová vyrovnávací paměť.  
  
     [!code-vb[VSSDKSignatureHelpTest#16](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_16.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#16](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_16.cs)]  
  
3.  Přidejte konstruktor, který nastaví textová vyrovnávací paměť a zprostředkovatel podpis pomoci zdroje.  
  
     [!code-vb[VSSDKSignatureHelpTest#17](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_17.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#17](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_17.cs)]  
  
4.  Implementace <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSource.AugmentSignatureHelpSession%2A> metoda. V tomto příkladu podpisy jsou pevně, ale v úplnou implementaci by tyto informace získáte v dokumentaci k jazyk.  
  
     [!code-vb[VSSDKSignatureHelpTest#18](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_18.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#18](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_18.cs)]  
  
5.  Pomocná metoda `CreateSignature()` se poskytuje pouze z důvodů obrázku.  
  
     [!code-vb[VSSDKSignatureHelpTest#19](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_19.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#19](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_19.cs)]  
  
6.  Implementace <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSource.GetBestMatch%2A> metoda. V tomto příkladu se ještě dvě podpisy, z nichž každá má dva parametry. Proto tato metoda se nevyžaduje. V implementaci úplnější, ve kterém je více než jeden podpis pomoci zdroj k dispozici, tato metoda se používá k rozhodování, zda zdroj podpis pomoci nejvyšší prioritou, můžete zadat odpovídající podpis. Pokud ne, vrátí metoda hodnotu null a další nejvyšší prioritou zdroj je vyzván k zadání shody.  
  
     [!code-vb[VSSDKSignatureHelpTest#20](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_20.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#20](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_20.cs)]  
  
7.  Implementujte metodu Dispose():  
  
     [!code-vb[VSSDKSignatureHelpTest#21](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_21.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#21](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_21.cs)]  
  
## <a name="implementing-the-signature-help-source-provider"></a>Implementace zprostředkovatele zdroj podpis nápovědy  
 Zprostředkovatel zdroje podpis pomoci zodpovídá pro export části součást Managed Extensibility Framework (MEF) a pro vytvoření instance zdroji podpis pomoci.  
  
#### <a name="to-implement-the-signature-help-source-provider"></a>Pro implementaci zprostředkovatele podpis pomoci zdroje  
  
1.  Přidejte třídu s názvem `TestSignatureHelpSourceProvider` , která implementuje <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSourceProvider>a exportovat je s <xref:Microsoft.VisualStudio.Utilities.NameAttribute>, <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "text" a <xref:Microsoft.VisualStudio.Utilities.OrderAttribute> z před = "default".  
  
     [!code-vb[VSSDKSignatureHelpTest#22](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_22.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#22](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_22.cs)]  
  
2.  Implementace <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSourceProvider.TryCreateSignatureHelpSource%2A> po vytvoření instance `TestSignatureHelpSource`.  
  
     [!code-vb[VSSDKSignatureHelpTest#23](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_23.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#23](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_23.cs)]  
  
## <a name="implementing-the-command-handler"></a>Implementace obslužná rutina  
 Podpis nápovědy obvykle aktivovány (znak a dismissed podle) znaků. Tyto stisknutí kláves dokáže zpracovat implementací <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> tak, aby se aktivuje při přijetí relaci podpis pomoci (znak sebou název známé metody a zavře relace při přijetí) znaků.  
  
#### <a name="to-implement-the-command-handler"></a>K implementaci obslužná rutina  
  
1.  Přidejte třídu s názvem `TestSignatureHelpCommand` , která implementuje <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>.  
  
     [!code-vb[VSSDKSignatureHelpTest#24](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_24.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#24](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_24.cs)]  
  
2.  Přidejte soukromé pole pro <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> adaptéru (který můžete přidat do obslužné rutiny příkazů of řetězu obslužná rutina), textového zobrazení, podpis pomoci zprostředkovatele a relace, <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigator>a další <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>.  
  
     [!code-vb[VSSDKSignatureHelpTest#25](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_25.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#25](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_25.cs)]  
  
3.  Přidejte konstruktor inicializovat těchto polí a přidejte filtr příkaz strukturu filtrů.  
  
     [!code-vb[VSSDKSignatureHelpTest#26](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_26.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#26](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_26.cs)]  
  
4.  Implementace <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> metoda k aktivaci podpis pomoci relace, jakmile přijme příkaz Filtr (znak po jednoho ze známé metoda názvy a pro zavření relace při přijetí) znak sice stále aktivní relace. V každém případě se předají příkaz.  
  
     [!code-vb[VSSDKSignatureHelpTest#27](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_27.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#27](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_27.cs)]  
  
5.  Implementace <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metoda tak, aby vždy předává příkaz.  
  
     [!code-vb[VSSDKSignatureHelpTest#28](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_28.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#28](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_28.cs)]  
  
## <a name="implementing-the-signature-help-command-provider"></a>Implementace zprostředkovatele příkaz podpis nápovědy  
 Můžete zadat příkaz podpis pomoci implementací <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener> při vytvoření textového zobrazení instance obslužná rutina příkazu.  
  
#### <a name="to-implement-the-signature-help-command-provider"></a>Pro implementaci zprostředkovatele podpis pomoci příkaz  
  
1.  Přidejte třídu s názvem `TestSignatureHelpController` , která implementuje <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener> a exportovat je s <xref:Microsoft.VisualStudio.Utilities.NameAttribute>, <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>, a <xref:Microsoft.VisualStudio.Text.Editor.TextViewRoleAttribute>.  
  
     [!code-vb[VSSDKSignatureHelpTest#29](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_29.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#29](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_29.cs)]  
  
2.  Import <xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService> (použít k získání <xref:Microsoft.VisualStudio.Text.Editor.ITextView>daných <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> objektu), <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService> (použít k vyhledání aktuální slovo) a <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpBroker> (pro aktivaci podpis pomoci relace).  
  
     [!code-vb[VSSDKSignatureHelpTest#30](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_30.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#30](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_30.cs)]  
  
3.  Implementace <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener.VsTextViewCreated%2A> metoda po vytvoření instance `TestSignatureCommandHandler`.  
  
     [!code-vb[VSSDKSignatureHelpTest#31](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_31.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#31](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_31.cs)]  
  
## <a name="building-and-testing-the-code"></a>Vytváření a testování kódu  
 K otestování tohoto kódu, sestavte řešení SignatureHelpTest a spusťte ji v experimentální instanci.  
  
#### <a name="to-build-and-test-the-signaturehelptest-solution"></a>Pro sestavení a otestování SignatureHelpTest řešení  
  
1.  Sestavte řešení.  
  
2.  Když spustíte tohoto projektu v ladicím programu, je vytvořena instance druhou instanci sady Visual Studio.  
  
3.  Vytvoření textového souboru a zadejte nějaký text, který obsahuje slovo "Přidat" a levé závorky.  
  
4.  Po zadání levé závorky, měli byste vidět popisek, který zobrazí seznam dvou podpisy `add()` metoda.  
  
## <a name="see-also"></a>Viz také  
 [Návod: Propojení typu obsahu s příponou názvu souboru](../extensibility/walkthrough-linking-a-content-type-to-a-file-name-extension.md)