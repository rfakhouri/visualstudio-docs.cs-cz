---
title: 'Návod: Implementace fragmenty kódu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: adbc5382-d170-441c-9fd0-80faa1816478
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ae260951160bc3d4ed3bb1535f47eb1f33649957
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-implementing-code-snippets"></a>Návod: Implementace fragmenty kódu
Můžete vytvořit fragmenty kódu a zahrnout je do editoru rozšíření, aby uživatelé rozšíření můžete přidat do vlastní kód.  
  
 Fragment kódu je fragment kódu nebo jiného textu, který může být součástí souboru. Chcete-li zobrazit všechny fragmenty kódu, které byly zaregistrovány pro konkrétní programovacích jazyků, na **nástroje** nabídky, klikněte na tlačítko **Správce fragmentů kódu**. Chcete-li vložit fragment kódu v souboru, kde chcete fragment, klikněte pravým tlačítkem klikněte na tlačítko **Vložit fragment** nebo **příkazu Obklopit s**, vyhledejte fragmentu chcete a pak na ni dvakrát kliknete. Stisknutím klávesy TAB nebo SHIFT + TAB ke změně v příslušných částech fragmentu a potom stiskněte klávesu ENTER nebo ESC jejich přijetí. Další informace najdete v tématu [fragmenty kódu](../ide/code-snippets.md).  
  
 Fragment kódu je obsažený v souboru XML, který má příponu názvu souboru .snippet. Fragment může obsahovat pole, která je zvýrazněná po tomto fragmentu kódu je vložen tak, aby uživatel můžete najít a jejich změnu. Soubor fragment kódu také poskytuje informace o **Správce fragmentů kódu** tak, aby mohla zobrazovat název fragmentu kódu v správné kategorii. Informace o schématu fragment kódu najdete v tématu [fragmenty kódu – odkaz schématu](../ide/code-snippets-schema-reference.md).  
  
 Tento názorný postup učí, jak provést tyto úlohy:  
  
1.  Vytvořit a registrovat fragmenty kódu pro konkrétní jazyk.  
  
2.  Přidat **Vložit fragment** příkaz místní nabídky.  
  
3.  Implementovat rozšíření fragment kódu.  
  
 Tento názorný postup je založen na [návod: zobrazení dokončování](../extensibility/walkthrough-displaying-statement-completion.md).  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-and-registering-code-snippets"></a>Vytvoření a registrace fragmenty kódu  
 Fragmenty kódu jsou obvykle přidružený registrované jazykové služby. Však není nutné implementovat <xref:Microsoft.VisualStudio.Package.LanguageService> k registraci fragmenty kódu. Místo toho právě zadejte identifikátor GUID v souboru index fragment kódu a pak použít stejný identifikátor GUID v <xref:Microsoft.VisualStudio.Shell.ProvideLanguageCodeExpansionAttribute> , které přidáte do projektu.  
  
 Následující kroky ukazují, jak vytvářet fragmenty kódu a přidružit konkrétní identifikátor GUID.  
  
1.  Vytvořte následující adresářovou strukturu:  
  
     **%InstallDir%\TestSnippets\Snippets\1033\\**  
  
     kde *InstallDir %* je složku pro instalaci sady Visual Studio. (I když tato cesta se obvykle používá k instalaci fragmenty kódu, můžete jakoukoliv cestu.)  
  
2.  Ve složce \1033\, vytvořte soubor XML s názvem **TestSnippets.xml**. (I když tento název se obvykle používá pro soubor indexu fragment kódu, které můžete zadat libovolný název, dokud obsahuje příponu názvu souboru .xml.) Přidejte následující text a odstranit zástupný symbol GUID a přidat vlastní.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <SnippetCollection>  
        <Language Lang="TestSnippets" Guid="{00000000-0000-0000-0000-000000000000}">  
            <SnippetDir>  
                <OnOff>On</OnOff>  
                <Installed>true</Installed>  
                <Locale>1033</Locale>  
                <DirPath>%InstallRoot%\TestSnippets\Snippets\%LCID%\</DirPath>  
                <LocalizedName>Snippets</LocalizedName>  
            </SnippetDir>  
        </Language>  
    </SnippetCollection>  
    ```  
  
3.  Vytvořte soubor ve složce fragment kódu, pojmenujte ji **testování**`.snippet`a poté přidejte následující text:  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <CodeSnippets  xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">  
        <CodeSnippet Format="1.0.0">  
            <Header>  
                <Title>Test replacement fields</Title>  
                <Shortcut>test</Shortcut>  
                <Description>Code snippet for testing replacement fields</Description>  
                <Author>MSIT</Author>  
                <SnippetTypes>  
                    <SnippetType>Expansion</SnippetType>  
                </SnippetTypes>  
            </Header>  
            <Snippet>  
                <Declarations>  
                    <Literal>  
                      <ID>param1</ID>  
                        <ToolTip>First field</ToolTip>  
                        <Default>first</Default>  
                    </Literal>  
                    <Literal>  
                        <ID>param2</ID>  
                        <ToolTip>Second field</ToolTip>  
                        <Default>second</Default>  
                    </Literal>  
                </Declarations>  
                <References>  
                   <Reference>  
                       <Assembly>System.Windows.Forms.dll</Assembly>  
                   </Reference>  
                </References>  
                <Code Language="TestSnippets">  
                    <![CDATA[MessageBox.Show("$param1$");  
         MessageBox.Show("$param2$");]]>  
                </Code>    
            </Snippet>  
        </CodeSnippet>  
    </CodeSnippets>  
    ```  
  
 Následující kroky ukazují, jak zaregistrovat fragmenty kódu.  
  
#### <a name="to-register-code-snippets-for-a-specific-guid"></a>K registraci fragmenty kódu pro konkrétní identifikátor GUID  
  
1.  Otevřete **CompletionTest** projektu. Informace o tom, jak vytvořit tento projekt najdete v tématu [návod: zobrazení dokončování](../extensibility/walkthrough-displaying-statement-completion.md).  
  
2.  V projektu přidáte odkazy na následující sestavení:  
  
    -   Microsoft.VisualStudio.TextManager.Interop  
  
    -   Microsoft.VisualStudio.TextManager.Interop.8.0  
  
    -   Microsoft.MSXML  
  
3.  V projektu otevřete soubor source.extension.vsixmanifest.  
  
4.  Ujistěte se, že **prostředky** karta obsahuje **VsPackage** obsahu typu a že **projektu** je nastavena na název projektu.  
  
5.  Vyberte projekt CompletionTest a v okně vlastností nastavte **generovat soubor Pkgdef** k **true**. Uložte projekt.  
  
6.  Přidání statického `SnippetUtilities` třídu do projektu.  
  
     [!code-csharp[VSSDKCompletionTest#22](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_1.cs)]
     [!code-vb[VSSDKCompletionTest#22](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_1.vb)]  
  
7.  Ve třídě SnippetUtilities definovat identifikátor GUID a dejte mu hodnotu, která jste použili v souboru SnippetsIndex.xml.  
  
     [!code-csharp[VSSDKCompletionTest#23](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_2.cs)]
     [!code-vb[VSSDKCompletionTest#23](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_2.vb)]  
  
8.  Přidat <xref:Microsoft.VisualStudio.Shell.ProvideLanguageCodeExpansionAttribute> k `TestCompletionHandler` třídy. Tento atribut lze přidat do všech veřejných nebo interní (nestatické) – třída v projektu. (Možná budete muset přidat `using` příkaz pro obor názvů Microsoft.VisualStudio.Shell.)  
  
     [!code-csharp[VSSDKCompletionTest#24](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_3.cs)]
     [!code-vb[VSSDKCompletionTest#24](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_3.vb)]  
  
9. Sestavte a spusťte projekt. V experimentální instanci sady Visual Studio, který se spustí při spuštění projektu, má být zobrazena v tomto fragmentu kódu, který jste právě zaregistrovali **Správce fragmentů kódu** pod **TestSnippets** jazyk.  
  
## <a name="adding-the-insert-snippet-command-to-the-shortcut-menu"></a>Přidání fragmentu příkaz Insert do místní nabídky  
 **Vložit fragment** příkaz není zahrnuta v místní nabídce pro textový soubor. Proto je nutné povolit příkaz.  
  
#### <a name="to-add-the-insert-snippet-command-to-the-shortcut-menu"></a>Chcete-li vložit fragment příkaz Přidat do místní nabídky  
  
1.  Otevřete `TestCompletionCommandHandler` soubor třídy.  
  
     Vzhledem k tomu, že tato třída implementuje <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>, můžete si aktivovat **Vložit fragment** v <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metoda. Než povolíte příkaz, zkontrolujte, že tato metoda není volána uvnitř funkce automatizace vzhledem k tomu, když **Vložit fragment** po kliknutí na příkaz, zobrazí fragment kódu výběr uživatelské rozhraní (UI).  
  
     [!code-csharp[VSSDKCompletionTest#25](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_4.cs)]
     [!code-vb[VSSDKCompletionTest#25](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_4.vb)]  
  
2.  Sestavte a spusťte projekt. V experimentální instance otevřete soubor, který má příponu názvu souboru s příponou ZZZ a pak klepněte pravým tlačítkem myši v něm. **Vložit fragment** příkaz by se měla objevit v místní nabídce.  
  
## <a name="implementing-snippet-expansion-in-the-snippet-picker-ui"></a>Implementace rozšíření fragment kódu v Sběrač fragmentů uživatelského rozhraní  
 V této části ukazuje, jak implementovat rozšíření fragmentu kódu tak, aby Sběrač fragmentů uživatelského rozhraní se zobrazí, když **Vložit fragment** po kliknutí na v místní nabídce. Fragment kódu je také rozšířit, pokud uživatel nezadá zástupce fragmentu kódu a potom stiskne KARTĚ.  
  
 K zobrazení Sběrač fragmentů uživatelského rozhraní a povolit navigaci a přijetí po vložení fragment kódu, použijte <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> metoda. Vlastní vložení jsou zpracována <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionClient.OnItemChosen%2A> metoda.  
  
 Implementace rozšíření fragmentu kódu používá starší <xref:Microsoft.VisualStudio.TextManager.Interop> rozhraní. Když z aktuální třídy editor přeložit pomocí starší verze kódu, mějte na paměti, starší verzi rozhraní použijte kombinaci čísla řádků a sloupců čísla k určení umístění v textové vyrovnávací paměti, že aktuální třídy používají jeden index. Proto pokud vyrovnávací paměť má tři řádky, z nichž každá má deset znaky (a nový řádek, který se počítá jako 1 znak), čtvrtý znak na ve třetím řádku je na pozici 27 v aktuální implementace, ale je na řádku 2, umístěte staré implementace 3.  
  
#### <a name="to-implement-snippet-expansion"></a>K implementaci rozšíření fragmentu kódu  
  
1.  Soubor, který obsahuje `TestCompletionCommandHandler` třídy, přidejte následující `using` příkazy.  
  
     [!code-csharp[VSSDKCompletionTest#26](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_5.cs)]
     [!code-vb[VSSDKCompletionTest#26](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_5.vb)]  
  
2.  Ujistěte se, `TestCompletionCommandHandler` implementaci třídy <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionClient> rozhraní.  
  
     [!code-csharp[VSSDKCompletionTest#27](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_6.cs)]
     [!code-vb[VSSDKCompletionTest#27](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_6.vb)]  
  
3.  V `TestCompletionCommandHandlerProvider` třídy, naimportujte <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService>.  
  
     [!code-csharp[VSSDKCompletionTest#28](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_7.cs)]
     [!code-vb[VSSDKCompletionTest#28](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_7.vb)]  
  
4.  Přidejte do něj privátní pole pro rozšíření rozhraní kódu a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>.  
  
     [!code-csharp[VSSDKCompletionTest#29](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_8.cs)]
     [!code-vb[VSSDKCompletionTest#29](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_8.vb)]  
  
5.  V konstruktoru `TestCompletionCommandHandler` třídy, nastavte následující pole.  
  
     [!code-csharp[VSSDKCompletionTest#30](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_9.cs)]
     [!code-vb[VSSDKCompletionTest#30](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_9.vb)]  
  
6.  Zobrazíte Sběrač fragmentů, když uživatel klikne **Vložit fragment** příkaz, přidejte následující kód, který <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> metoda. (Chcete-li toto vysvětlení lépe čitelný, není zobrazena, Exec() kód, který se používá pro dokončování; místo toho bloky kódu jsou přidány do stávající metodu.) Přidejte následující blok kódu za kód, který kontroluje znak.  
  
     [!code-csharp[VSSDKCompletionTest#31](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_10.cs)]
     [!code-vb[VSSDKCompletionTest#31](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_10.vb)]  
  
7.  Pokud fragment má pole, která lze procházet, rozšíření relace je zůstat otevřené, dokud rozšíření je explicitně přijímán; Pokud fragmentu nemá žádná pole, relace se zavře a se vrátí jako `null` pomocí <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionManager.InvokeInsertionUI%2A> metoda. V <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> metody po Sběrač fragmentů kódu uživatelského rozhraní, které jste přidali v předchozím kroku, přidejte následující kód pro zpracování navigační fragmentu kódu (Pokud je uživatel stiskne klávesu TAB nebo SHIFT + TAB po vložení fragmentu).  
  
     [!code-csharp[VSSDKCompletionTest#32](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_11.cs)]
     [!code-vb[VSSDKCompletionTest#32](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_11.vb)]  
  
8.  Vložit fragment kódu, kdy uživatel nezadá odpovídající zástupce a potom stiskne KARTĚ, přidejte kód, který <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> metoda. Soukromá metoda, která vloží fragmentu budou zobrazeny v pozdější fázi. Přidejte následující kód po navigační kód, který jste přidali v předchozím kroku.  
  
     [!code-csharp[VSSDKCompletionTest#33](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_12.cs)]
     [!code-vb[VSSDKCompletionTest#33](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_12.vb)]  
  
9. Implementace metody <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionClient> rozhraní. V této implementaci jsou jenom metody, které vás zajímají <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionClient.EndExpansion%2A> a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionClient.OnItemChosen%2A>. Jiné metody by měla vrátit právě <xref:Microsoft.VisualStudio.VSConstants.S_OK>.  
  
     [!code-csharp[VSSDKCompletionTest#34](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_13.cs)]
     [!code-vb[VSSDKCompletionTest#34](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_13.vb)]  
  
10. Implementace <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionClient.OnItemChosen%2A> metoda. Pomocná metoda, která ve skutečnosti vloží rozšíření se budeme v pozdější fázi. <xref:Microsoft.VisualStudio.TextManager.Interop.TextSpan> Obsahuje řádek a ve sloupci informace, které můžete získat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>.  
  
     [!code-csharp[VSSDKCompletionTest#35](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_14.cs)]
     [!code-vb[VSSDKCompletionTest#35](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_14.vb)]  
  
11. Metodu privátní vloží fragment kódu, založené na zástupce nebo na název a cesta. Potom zavolá <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansion.InsertNamedExpansion%2A> metoda fragmentem kódu.  
  
     [!code-csharp[VSSDKCompletionTest#36](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_15.cs)]
     [!code-vb[VSSDKCompletionTest#36](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_15.vb)]  
  
## <a name="building-and-testing-code-snippet-expansion"></a>Vytváření a testování rozšíření fragmentu kódu  
 Můžete zkontrolovat, zda fragment kódu rozšíření funguje ve vašem projektu.  
  
1.  Sestavte řešení. Když spustíte tohoto projektu v ladicím programu, je vytvořena instance druhou instanci sady Visual Studio.  
  
2.  Otevřete textový soubor a zadejte nějaký text.  
  
3.  Klikněte pravým tlačítkem někde v textu a pak klikněte na tlačítko **Vložit fragment**.  
  
4.  Sběrač fragmentů uživatelského rozhraní by se automaticky otevírané okno s upozorněním **testování nahrazení pole**. Dvakrát klikněte na místní nabídce.  
  
     Následující fragment kódu, musí být zařazeny.  
  
    ```  
    MessageBox.Show("first");  
    MessageBox.Show("second");  
    ```  
  
     Bez stisknutí klávesy ENTER nebo ESC.  
  
5.  Stiskněte klávesu TAB a SHIFT + TAB k přepnutí mezi "první" a "druhý".  
  
6.  Stisknutím klávesy ENTER nebo ESC přijměte vložení.  
  
7.  V různých část textu zadejte "test" a potom stiskněte klávesu TAB. Vzhledem k tomu, že "test" je zkratka fragment kódu, musí být fragmentu zařazen znovu.  
  
## <a name="next-steps"></a>Další kroky