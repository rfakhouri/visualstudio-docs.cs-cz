---
title: "Podpora pro fragmenty kódu ve službě jazyk starší | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- snippets, supporting in language services
- code snippets, supporting in language services [managed package framework]
- language services [managed package framework], supporting code snippets
ms.assetid: 7490325b-acee-4c2d-ac56-1cd5db1a1083
caps.latest.revision: "28"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0089e5a8bf85ba352788767c821d95f41ca60eec
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="support-for-code-snippets-in-a-legacy-language-service"></a>Podpora pro fragmenty kódu ve službě jazyk starší verze
Fragment kódu je úsek kódu, který je vložen do zdrojového souboru. Fragment kódu, samotné je šablonu na základě XML s sady polí. Tato pole jsou vyznačené po tomto fragmentu kódu je vložen a může mít různé hodnoty v závislosti na kontextu, ve kterém je vložen fragmentu. Ihned po tomto fragmentu kódu je vložen, může služba jazyka formátu fragmentu.  
  
 Fragment se vloží do režimu speciální úprav, která umožňuje pole fragmentu k navigaci pomocí klávesy TAB. Pole může podporovat IntelliSense stylu rozevíracích nabídek. Uživatel potvrdí zadáním ENTER nebo klávesy ESC fragmentu zdrojový soubor. Další informace o fragmentech, najdete v tématu [fragmenty kódu](../../ide/code-snippets.md).  
  
 Starší verze jazyka služby jsou implementovány jako součást VSPackage, ale novější způsob implementace funkce služby jazyk je použití MEF rozšíření. Další informace naleznete v tématu [návod: implementace fragmenty kódu](../../extensibility/walkthrough-implementing-code-snippets.md).  
  
> [!NOTE]
>  Doporučujeme vám, že začnete používat co nejdříve editoru nové rozhraní API. Tím zvýšit výkon služby jazyk a umožňují využívat výhod nových funkcí editoru.  
  
## <a name="managed-package-framework-support-for-code-snippets"></a>Spravované podpora Framework balíčku pro fragmenty kódu  
 Rozhraní framework spravované balíčku (MPF) podporuje většinu funkcí fragment kódu, čtením šablonu, kterou chcete vkládání fragmentu a povolení speciální režim úprav. Podpora je spravovat prostřednictvím <xref:Microsoft.VisualStudio.Package.ExpansionProvider> třídy.  
  
 Při <xref:Microsoft.VisualStudio.Package.Source> vytvoření instance třídy <xref:Microsoft.VisualStudio.Package.LanguageService.CreateExpansionProvider%2A> metoda v <xref:Microsoft.VisualStudio.Package.LanguageService> třídy se nazývá získat <xref:Microsoft.VisualStudio.Package.ExpansionProvider> objektu (Všimněte si, že základní <xref:Microsoft.VisualStudio.Package.LanguageService> třída vždy vrátí novou <xref:Microsoft.VisualStudio.Package.ExpansionProvider> objekt pro každou <xref:Microsoft.VisualStudio.Package.Source> objekt).  
  
 Sady MPF nepodporuje rozšíření funkce. Funkce rozšíření je s názvem funkce, která vložené v šabloně fragment kódu a vrátí jednu nebo více hodnot, které se mají umístit na pole. Hodnoty se vrátí pomocí jazyka vlastní prostřednictvím služby <xref:Microsoft.VisualStudio.Package.ExpansionFunction> objektu. <xref:Microsoft.VisualStudio.Package.ExpansionFunction> Objekt musí být implementována službou jazyk pro podporu rozšíření funkce.  
  
## <a name="providing-support-for-code-snippets"></a>Zajištění podpory pro fragmenty kódu  
 Povolení podpory pro fragmenty kódu, je nutné zadat nebo nainstalovat fragmenty kódu a je nutné zadat možnosti pro uživatele k vložení tyto fragmenty kódu. Existují tři kroky k povolení podpory pro fragmenty kódu:  
  
1.  Instalace souborů fragment kódu.  
  
2.  Povolení fragmenty kódu služby jazyk.  
  
3.  Vyvolání <xref:Microsoft.VisualStudio.Package.ExpansionProvider> objektu.  
  
### <a name="installing-the-snippet-files"></a>Instalace souborů fragmentu kódu  
 Všechny fragmenty pro jazyk, jsou uloženy jako šablona v soubory XML, obvykle jedna fragment kódu šablona na soubor. Informace o schématu XML pro šablony fragment kódu v [fragmenty kódu – odkaz schématu](../../ide/code-snippets-schema-reference.md). Každá šablona fragmentu kódu je identifikován s ID jazyka. Tento jazyk ID je uvedený v registru a umístí do `Language` atribut \<kód > značky v šabloně.  
  
 Obvykle jsou dvě místa, kde jsou uloženy soubory šablony fragment kódu: 1) Pokud byl nainstalován svůj jazyk a 2) ve složce uživatele. Tato umístění jsou přidány do registru, který sady Visual Studio **Správce fragmentů kódu** můžete najít fragmenty kódu. Složka uživatele je, kde jsou uloženy fragmenty vytvořený uživatelem.  
  
 Složka obvykle rozložení pro soubory šablon nainstalované fragment kódu vypadá takto: *[Kořenová_složka_instalace]*\\*[TestLanguage]*\Snippets\\*[LCID]*\Snippets.  
  
 *[Kořenová_složka_instalace]*  je složka, je váš jazyk nainstalovaný v.  
  
 *[TestLanguage]*  je název jazyka jako název složky.  
  
 *[LCID]*  je ID národního prostředí. Jedná se jak lokalizované verze vaší fragmenty kódu jsou uložené. Například ID národního prostředí pro angličtinu je 1033, takže *[LCID]* je nahrazena 1033.  
  
 Je nutné zadat jeden další soubor a který je indexový soubor, obvykle nazývá SnippetsIndex.xml nebo ExpansionsIndex.xml (můžete použít libovolný platný název souboru končí na .xml). Tento soubor je obvykle uložen ve *[Kořenová_složka_instalace]*\\*[TestLanguage]* složce a určuje přesné umístění složky fragmenty společně s ID jazyka a identifikátor GUID jazyka Služba, která používá fragmenty kódu. Přesnou cestu k souboru indexu je uvést do registru, jak je popsáno dále v "Instalace položky registru". Tady je příklad SnippetsIndex.xml souboru:  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<SnippetCollection>  
    <Language Lang="Testlanguage" Guid="{b614a40a-80d9-4fac-a6ad-fc2868fff7cd}">  
        <SnippetDir>  
            <OnOff>On</OnOff>  
            <Installed>true</Installed>  
            <Locale>1033</Locale>  
            <DirPath>%InstallRoot%\TestLanguage\Snippets\%LCID%\Snippets\</DirPath>  
            <LocalizedName>Snippets</LocalizedName>  
        </SnippetDir>  
    </Language>  
</SnippetCollection>  
```  
  
 \<Jazyk > Značka Určuje ID jazyka ( `Lang` atribut) a služba jazyka identifikátor GUID.  
  
 Tento příklad předpokládá, že jste nainstalovali služby jazyk v instalační složce Nástroje Visual Studio. LCID % se nahradí aktuální ID národního prostředí uživatele Více \<SnippetDir > značky mohou být přidány, jednu pro každý jiný adresář a národní prostředí. Kromě toho fragment kódu složka může obsahovat podsložek, z nichž každý je definovaný v soubor indexu s \<SnippetSubDir > značky, která je součástí \<SnippetDir > značky.  
  
 Uživatelé mohou také vytvářet své vlastní fragmenty pro svůj jazyk. Tyto jsou obvykle uložen ve složce nastavení uživatele, například *[TestDocs]*\Code fragmenty\\*[TestLanguage]*\Test fragmenty kódu, kde *[TestDocs]* je umístění uživatele nastavení složky pro sadu Visual Studio.  
  
 Tyto prvky nahrazení mohou být umístěny v cestě uložené v \<DirPath > značky v souboru indexu.  
  
|Prvek|Popis|  
|-------------|-----------------|  
|LCID %|ID národního prostředí.|  
|% Kořenová_složka_instalace %|Kořenová složka instalace pro Visual Studio, například C:\Program Files\Microsoft Visual Studio 8.|  
|% ProjDir %|Složka obsahující aktuálního projektu.|  
|% ProjItem %|Složka obsahující aktuální položka projektu.|  
|% TestDocs %|Složku ve složce nastavení uživatele, například C:\Documents and Settings\\*[username]*\My Documents\Visual Studio\8.|  
  
### <a name="enabling-code-snippets-for-your-language-service"></a>Povolení služby jazyk fragmenty kódu  
 Fragmenty kódu můžete povolit pro vaši službu jazyk přidáním <xref:Microsoft.VisualStudio.Shell.ProvideLanguageCodeExpansionAttribute> atribut vaše VSPackage (najdete v části [registrace služby jazyk starší](../../extensibility/internals/registering-a-legacy-language-service1.md) podrobnosti). <xref:Microsoft.VisualStudio.Shell.ProvideLanguageCodeExpansionAttribute.ShowRoots%2A> a <xref:Microsoft.VisualStudio.Shell.ProvideLanguageCodeExpansionAttribute.SearchPaths%2A> parametry jsou volitelné, ale by měla obsahovat `SearchPaths` s názvem parametru, aby bylo možné informovat o tom, **Správce fragmentů kódu** umístění vaší fragmenty kódu.  
  
 Následuje příklad použití tento atribut:  
  
```  
[ProvideLanguageCodeExpansion(  
         typeof(TestSnippetLanguageService),  
         "Test Snippet Language",          // Name of language used as registry key  
         0,                               // Resource ID of localized name of language service  
         "Test Snippet Language",        // Name of Language attribute in snippet template  
         @"%InstallRoot%\Test Snippet Language\Snippets\%LCID%\SnippetsIndex.xml",  // Path to snippets index  
         SearchPaths = @"%InstallRoot%\Test Snippet Language\Snippets\%LCID%\")]    // Path to snippets  
```  
  
### <a name="calling-the-expansion-provider"></a>Volání metody rozšíření zprostředkovatele  
 Služba jazyka řídí vkládání žádné fragment kódu, jakož i způsob, jakým je volána vložení.  
  
## <a name="calling-the-expansion-provider-for-code-snippets"></a>Volání metody rozšíření zprostředkovatele pro fragmenty kódu  
 Existují dva způsoby, jak vyvolat poskytovatele rozšíření: pomocí příkazu nabídky nebo pomocí zástupce ze seznamu dokončení.  
  
### <a name="inserting-a-code-snippet-by-using-a-menu-command"></a>Vkládání fragmentu kódu s použitím příkazu nabídky  
 Použití příkazu nabídky k zobrazení prohlížeče fragment kódu, přidejte příkaz nabídky a pak zavolají <xref:Microsoft.VisualStudio.Package.ExpansionProvider.DisplayExpansionBrowser%2A> metoda v <xref:Microsoft.VisualStudio.Package.ExpansionProvider> rozhraní v reakci na tento příkaz nabídky.  
  
1.  Přidejte do souboru .vsct příkazu a tlačítko. Můžete najít tak v postupu [vytvoření rozšíření pomocí příkazu v nabídce](../../extensibility/creating-an-extension-with-a-menu-command.md).  
  
2.  Odvození třídy z <xref:Microsoft.VisualStudio.Package.ViewFilter> třídy a přepsat <xref:Microsoft.VisualStudio.Package.ViewFilter.QueryCommandStatus%2A> metoda označíte, podporu pro nový příkaz nabídky. Tento příklad umožňuje vždy příkaz nabídky.  
  
    ```csharp  
    using Microsoft.VisualStudio.Package;  
  
    namespace TestLanguagePackage  
    {  
        class TestViewFilter : ViewFilter  
        {  
            public TestViewFilter(CodeWindowManager mgr, IVsTextView view)  
                : base(mgr, view)  
            {  
            }  
  
            protected override int QueryCommandStatus(ref Guid guidCmdGroup,  
                                                      uint nCmdId)  
            {  
                int hr = base.QueryCommandStatus(ref guidCmdGroup, nCmdId);  
                // If the base class did not recognize the command then  
                // see if we can handle the command.  
                if (hr == (int)Microsoft.VisualStudio.OLE.Interop.Constants.OLECMDERR_E_UNKNOWNGROUP)  
                {  
                    if (guidCmdGroup == GuidList.guidTestLanguagePackageCmdSet)  
                    {  
                        if (nCmdId == PkgCmdIDList.InvokeCodeSnippetsBrowser)  
                        {  
                            hr = (int)(OLECMDF.OLECMDF_SUPPORTED | OLECMDF.OLECMDF_ENABLED);  
                        }  
                    }  
                }  
                return hr;  
            }  
        }  
    }  
    ```  
  
3.  Přepsání <xref:Microsoft.VisualStudio.Package.ViewFilter.HandlePreExec%2A> metoda v <xref:Microsoft.VisualStudio.Package.ViewFilter> třída získat <xref:Microsoft.VisualStudio.Package.ExpansionProvider> objekt a volání <xref:Microsoft.VisualStudio.Package.ExpansionProvider.DisplayExpansionBrowser%2A> metodu na tento objekt.  
  
    ```csharp  
    using Microsoft.VisualStudio.Package;  
  
    namespace TestLanguagePackage  
    {  
        class TestViewFilter : ViewFilter  
        {  
            public override bool HandlePreExec(ref Guid guidCmdGroup,  
                                               uint nCmdId,  
                                               uint nCmdexecopt,  
                                               IntPtr pvaIn,  
                                               IntPtr pvaOut)  
            {  
                if (base.HandlePreExec(ref guidCmdGroup,  
                                       nCmdId,  
                                       nCmdexecopt,  
                                       pvaIn,  
                                       pvaOut))  
                {  
                    // Base class handled the command.  Do nothing more here.  
                    return true;  
                }  
  
                if (guidCmdGroup == GuidList.guidTestLanguagePackageCmdSet)  
                {  
                    if (nCmdId == PkgCmdIDList.InvokeCodeSnippetsBrowser)  
                    {  
                        ExpansionProvider ep = this.GetExpansionProvider();  
                        if (this.TextView != null && ep != null)  
                        {  
                            bool bDisplayed = ep.DisplayExpansionBrowser(  
                                this.TextView,  
                                "TestLanguagePackage Snippet:",  
                                null,  
                                false,  
                                null,  
                                false);  
                        }  
                        return true;   // Handled the command.  
                    }  
                }  
                return false;   // Did not handle the command.  
            }  
        }  
    }  
  
    ```  
  
     Následující metody v <xref:Microsoft.VisualStudio.Package.ExpansionProvider> třídy se nazývají Visual Studio v uvedeném pořadí během procesu vkládání fragmentu:  
  
4.  <xref:Microsoft.VisualStudio.Package.ExpansionProvider.OnItemChosen%2A>  
  
5.  <xref:Microsoft.VisualStudio.Package.ExpansionProvider.IsValidKind%2A>  
  
6.  <xref:Microsoft.VisualStudio.Package.ExpansionProvider.OnBeforeInsertion%2A>  
  
7.  <xref:Microsoft.VisualStudio.Package.ExpansionProvider.FormatSpan%2A>  
  
8.  <xref:Microsoft.VisualStudio.Package.ExpansionProvider.OnAfterInsertion%2A>  
  
     Po <xref:Microsoft.VisualStudio.Package.ExpansionProvider.OnAfterInsertion%2A> metoda je volána, byla vložena fragmentu a <xref:Microsoft.VisualStudio.Package.ExpansionProvider> objekt je v režimu úprav speciální použít úpravy fragment kódu, který právě byl vložen.  
  
### <a name="inserting-a-code-snippet-by-using-a-shortcut"></a>Vkládání fragmentu kódu pomocí zástupce  
 Implementace zástupce ze seznamu dokončení je mnohem složitější než implementace příkazu nabídky. Zástupce fragmentu kódu je nejprve nutno přidat do seznamu dokončení IntelliSense aplikace word. Pak musí rozpoznat, kdy byla vložena název zástupce fragment kódu v důsledku dokončení. Nakonec musí získat název fragmentu kódu a cesty pomocí názvu zástupce a předejte tyto informace k <xref:Microsoft.VisualStudio.Package.ExpansionProvider.InsertNamedExpansion%2A> metodu <xref:Microsoft.VisualStudio.Package.ExpansionProvider> metoda.  
  
 Pokud chcete přidat zástupce fragment kódu do seznamu dokončení word, přidejte je do <xref:Microsoft.VisualStudio.Package.Declarations> objekt v vaší <xref:Microsoft.VisualStudio.Package.AuthoringScope> třídy. Je třeba se, že identifikujete zástupce jako název fragmentu kódu. Příklad, naleznete v části [návod: získání seznamu z nainstalován fragmenty kódu (starší verze implementace)](../../extensibility/internals/walkthrough-getting-a-list-of-installed-code-snippets-legacy-implementation.md).  
  
 Vkládání zástupce fragment kódu v, můžete zjistit <xref:Microsoft.VisualStudio.Package.Declarations.OnAutoComplete%2A> metodu <xref:Microsoft.VisualStudio.Package.Declarations> třídy. Vzhledem k tomu, že název fragmentu již byl vložen do zdrojového souboru, musí být odebrán, když vložíte rozšíření. <xref:Microsoft.VisualStudio.Package.ExpansionProvider.InsertNamedExpansion%2A> Metoda přebírá značka span, která popisuje bod vložení fragmentu; rozpětí zahrnuje název celý fragment kódu ve zdrojovém souboru, tento název je nahrazena fragmentu.  
  
 Zde je verze <xref:Microsoft.VisualStudio.Package.Declarations> třída, která zpracovává fragment kódu vložení název zástupce. Ostatní metody ve <xref:Microsoft.VisualStudio.Package.Declarations> třídy byly vynechány pro přehlednost. Všimněte si, že trvá konstruktoru této třídy <xref:Microsoft.VisualStudio.Package.LanguageService> objektu. To lze předat ve z vaší verzi <xref:Microsoft.VisualStudio.Package.AuthoringScope> objektu (například vaši implementaci <xref:Microsoft.VisualStudio.Package.AuthoringScope> třída může trvat <xref:Microsoft.VisualStudio.Package.LanguageService> objekt v jeho konstruktoru a předejte tento objekt na vaše `TestDeclarations` konstruktoru třídy).  
  
```csharp  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    internal class TestDeclarations : Declarations  
    {  
        private ArrayList       declarations;  
        private LanguageService languageService;  
        private TextSpan        commitSpan;  
  
        public TestDeclarations(LanguageService langService)  
            : base()  
        {  
            languageService = langService;  
            declarations = new ArrayList();  
        }  
  
        // This method is used to add declarations to the internal list.  
        public void AddDeclaration(TestDeclaration declaration)  
        {  
            declarations.Add(declaration);  
        }  
  
        // This method is called to get the string to commit to the source buffer.  
        // Note that the initial extent is only what the user has typed so far.  
        public override string OnCommit(IVsTextView textView,  
                                        string textSoFar,  
                                        char commitCharacter,  
                                        int index,  
                                        ref TextSpan initialExtent)  
        {  
            // We intercept this call only to get the initial extent  
            // of what was committed to the source buffer.  
            commitSpan = initialExtent;  
  
            return base.OnCommit(textView,  
                                 textSoFar,  
                                 commitCharacter,  
                                 index,  
                                 ref initialExtent);  
        }  
  
        // This method is called after the string has been committed to the source buffer.  
        public override char OnAutoComplete(IVsTextView textView,  
                                            string committedText,  
                                            char commitCharacter,  
                                            int index)  
        {  
            TestDeclaration item = declarations[index] as TestDeclaration;  
            if (item != null)  
            {  
                // In this example, TestDeclaration identifies types with a string.  
                // You can choose a different approach.  
                if (item.Type == "snippet")  
                {  
                    Source src = languageService.GetSource(textView);  
                    if (src != null)  
                    {  
                        ExpansionProvider ep = src.GetExpansionProvider();  
                        if (ep != null)  
                        {  
                            string title;  
                            string path;  
                            int commitLength = commitSpan.iEndIndex - commitSpan.iStartIndex;  
                            if (commitLength < committedText.Length)  
                            {  
                                // Replace everything that was inserted  
                                // so calculate the span of the full  
                                // insertion, taking into account what  
                                // was inserted when the commitSpan  
                                // was obtained in the first place.  
                                commitSpan.iEndIndex += (committedText.Length - commitLength);  
                            }  
  
                            if (ep.FindExpansionByShortcut(textView,  
                                                           committedText,  
                                                           commitSpan,  
                                                           true,  
                                                           out title,  
                                                           out path))  
                            {  
                                ep.InsertNamedExpansion(textView,  
                                                        title,  
                                                        path,  
                                                        commitSpan,  
                                                        false);  
                            }  
                        }  
                    }  
                }  
            }  
            return '\0';  
        }  
    }  
}  
```  
  
 Služba jazyka získá název zástupce, zavolá <xref:Microsoft.VisualStudio.Package.ExpansionProvider.FindExpansionByShortcut%2A> metoda získat název fragmentu kódu a název souboru a kódu. Služba jazyka pak zavolá <xref:Microsoft.VisualStudio.Package.ExpansionProvider.InsertNamedExpansion%2A> metoda v <xref:Microsoft.VisualStudio.Package.ExpansionProvider> třída Vložit fragment kódu. Následující metody se nazývají Visual Studio v uvedeném pořadí v <xref:Microsoft.VisualStudio.Package.ExpansionProvider> třídu během vkládání fragmentu:  
  
1.  <xref:Microsoft.VisualStudio.Package.ExpansionProvider.IsValidKind%2A>  
  
2.  <xref:Microsoft.VisualStudio.Package.ExpansionProvider.OnBeforeInsertion%2A>  
  
3.  <xref:Microsoft.VisualStudio.Package.ExpansionProvider.FormatSpan%2A>  
  
4.  <xref:Microsoft.VisualStudio.Package.ExpansionProvider.OnAfterInsertion%2A>  
  
 Další informace o získání seznamu fragmenty kódu nainstalované služby jazyka najdete v tématu [návod: získání seznamu z nainstalován fragmenty kódu (starší verze implementace)](../../extensibility/internals/walkthrough-getting-a-list-of-installed-code-snippets-legacy-implementation.md).  
  
## <a name="implementing-the-expansionfunction-class"></a>Implementace ExpansionFunction – třída  
 Funkce rozšíření je s názvem funkce, která vložené v šabloně fragment kódu a vrátí jednu nebo více hodnot, které se mají umístit na pole. Za účelem podpory funkcí rozšíření ve službě jazyk, musí odvození třídy z <xref:Microsoft.VisualStudio.Package.ExpansionFunction> třídy a implementovat <xref:Microsoft.VisualStudio.Package.ExpansionFunction.GetCurrentValue%2A> metoda. Pak je nutné přepsat <xref:Microsoft.VisualStudio.Package.LanguageService.CreateExpansionFunction%2A> metoda v <xref:Microsoft.VisualStudio.Package.LanguageService> třídy vracení nové vytvoření instance vaší verze <xref:Microsoft.VisualStudio.Package.ExpansionFunction> třídu pro jednotlivé funkce rozšíření, které podporujete. Pokud podporujete seznamu možných hodnot z rozšíření funkce, je nutné také přepsat <xref:Microsoft.VisualStudio.Package.ExpansionFunction.GetIntellisenseList%2A> metoda v <xref:Microsoft.VisualStudio.Package.ExpansionFunction> třída zobrazíte seznam těchto hodnot.  
  
 Rozšíření funkce, která má argumenty nebo potřebuje přístup k další pole by neměl být přidružen upravitelné pole, jako poskytovatele rozšíření nebyla pravděpodobně inicializována plně o dobu, kterou je volána funkce rozšíření. Funkce rozšíření v důsledku toho není schopný získat hodnotu její argumenty nebo jiné pole.  
  
### <a name="example"></a>Příklad  
 Tady je příklad, jak volat funkci jednoduché rozšíření `GetName` může implementovat. Tato funkce rozšíření připojí číslo název základní třídy pokaždé, když je vytvořena instance funkce rozšíření (která odpovídá pokaždé, když fragmentu kódu související se vloží).  
  
```csharp  
using Microsoft.VisualStudio.Package;  
  
namespace TestLanguagePackage  
{  
    public class TestLanguageService : LanguageService  
    {  
        private int classNameCounter = 0;  
  
        public override ExpansionFunction CreateExpansionFunction(  
            ExpansionProvider provider,  
            string functionName)  
        {  
            ExpansionFunction function = null;  
            if (functionName == "GetName")  
            {  
                ++classNameCounter;  
                function = new TestGetNameExpansionFunction(provider, classNameCounter);  
            }  
            return function;  
        }  
    }  
  
    internal class TestGetNameExpansionFunction : ExpansionFunction  
    {  
        private int nameCount;  
  
        TestGetNameExpansionFunction(ExpansionProvider provider, int counter)  
            : base(provider)  
        {  
            nameCount = counter;  
        }  
  
        public override string GetCurrentValue()  
        {  
            string name = "TestClass";  
            name += nameCount.ToString();  
            return name;  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Funkce služby starší verze jazyka](../../extensibility/internals/legacy-language-service-features1.md)   
 [Registrace služby jazyk starší verze](../../extensibility/internals/registering-a-legacy-language-service1.md)   
 [Fragmenty kódu](../../ide/code-snippets.md)   
 [Návod: Získáním seznamu fragmenty kódu nainstalovaný (implementace starší verze)](../../extensibility/internals/walkthrough-getting-a-list-of-installed-code-snippets-legacy-implementation.md)