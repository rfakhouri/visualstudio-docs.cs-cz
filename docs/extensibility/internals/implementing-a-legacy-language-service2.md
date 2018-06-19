---
title: Implementace starší verze jazyka Service2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- language services [managed package framework], implementing
ms.assetid: 5bcafdc5-f922-48f6-a12e-6c8507a79a05
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d54572bc3b105af01ed42b01a27f363da80d58de
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31134988"
---
# <a name="implementing-a-legacy-language-service"></a>Implementace služby jazyk starší verze
Pokud chcete implementovat jazyk služby pomocí rozhraní spravované balíčku (MPF), musí odvození třídy z <xref:Microsoft.VisualStudio.Package.LanguageService> třídy a implementovat následující abstraktní metody a vlastnosti:  
  
-   <xref:Microsoft.VisualStudio.Package.LanguageService.GetLanguagePreferences%2A> – Metoda  
  
-   <xref:Microsoft.VisualStudio.Package.LanguageService.GetScanner%2A> – Metoda  
  
-   <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> – Metoda  
  
-   <xref:Microsoft.VisualStudio.Package.LanguageService.Name%2A> Vlastnost  
  
 O implementaci těchto metod a vlastností, naleznete v příslušné části níže podrobnosti.  
  
 Pro podporu dalších funkcí, může mít vaše služba jazyka na odvození třídy z jednoho z třídy služeb jazykové sady MPF; například pro podporu další příkazy, musí odvození třídy z <xref:Microsoft.VisualStudio.Package.ViewFilter> třídy a přepsat několik metod zpracování příkazu (najdete v části <xref:Microsoft.VisualStudio.Package.ViewFilter> podrobnosti). <xref:Microsoft.VisualStudio.Package.LanguageService> Třída poskytuje několik metod, které se nazývají k vytvoření nové instance různých tříd a přepsat metodu odpovídající vytvoření zajistit instanci třídě. Například je nutné přepsat <xref:Microsoft.VisualStudio.Package.LanguageService.CreateViewFilter%2A> metoda v <xref:Microsoft.VisualStudio.Package.LanguageService> třída vrátit instanci vlastní <xref:Microsoft.VisualStudio.Package.ViewFilter> třídy. Najdete v části "Vytvoření instance třídy vlastní" Další informace.  
  
 Vaše služba jazyka může taky poskytovat vlastní ikony, které se používají na mnoha místech. Například když se zobrazí seznam dokončení technologie IntelliSense, každou položku v seznamu může mít ikonu přidružena, označit položku jako metodu, třídu, obor názvů, vlastnost, nebo vše, co je nezbytné pro svůj jazyk. Tyto ikony se používají ve všech seznamech IntelliSense, **navigační panel**a v **seznam chyb** okno úkolu. Najdete v části "Služba jazyka bitové kopie" níže podrobnosti.  
  
## <a name="getlanguagepreferences-method"></a>GetLanguagePreferences – metoda  
 <xref:Microsoft.VisualStudio.Package.LanguageService.GetLanguagePreferences%2A> Metoda vždy vrátí stejné instanci <xref:Microsoft.VisualStudio.Package.LanguagePreferences> třídy. Můžete použít základní <xref:Microsoft.VisualStudio.Package.LanguagePreferences> třídy, pokud není nutné žádné další předvolby pro vaši službu jazyka. Třídy služeb jazykové sady MPF předpokládá přítomnost alespoň základní <xref:Microsoft.VisualStudio.Package.LanguagePreferences> třídy.  
  
### <a name="example"></a>Příklad  
 Tento příklad ukazuje Typická implementace <xref:Microsoft.VisualStudio.Package.LanguageService.GetLanguagePreferences%2A> metoda. Tento příklad používá základní <xref:Microsoft.VisualStudio.Package.LanguagePreferences> třídy.  
  
```csharp  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    public class TestLanguageService : LanguageService  
    {  
        private LanguagePreferences m_preferences;  
  
        public override LanguagePreferences GetLanguagePreferences()  
        {  
            if (m_preferences == null)  
            {  
                m_preferences = new LanguagePreferences(this.Site,  
                                                        typeof(TestLanguageService).GUID,  
                                                        this.Name );  
                m_preferences.Init();  
            }  
            return m_preferences;  
        }  
    }  
}  
```  
  
## <a name="getscanner-method"></a>GetScanner – metoda  
 Tato metoda vrací instanci třídy <xref:Microsoft.VisualStudio.Package.IScanner> objekt, který implementuje řádkový analyzátor nebo skener použitý pro získání tokeny a typy a aktivační události. Tento skener se používá v <xref:Microsoft.VisualStudio.Package.Colorizer> třídy pro zabarvení skeneru se dá použít taky jako prelude složitější analýzy operace získání typy tokenů a aktivační události. Je nutné zadat třídu, která implementuje <xref:Microsoft.VisualStudio.Package.IScanner> rozhraní a musí implementovat na všechny metody <xref:Microsoft.VisualStudio.Package.IScanner> rozhraní.  
  
### <a name="example"></a>Příklad  
 Tento příklad ukazuje Typická implementace <xref:Microsoft.VisualStudio.Package.LanguageService.GetScanner%2A> metoda. `TestScanner` Třída implementuje <xref:Microsoft.VisualStudio.Package.IScanner> rozhraní (to není znázorněné).  
  
```csharp  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    public class TestLanguageService : LanguageService  
    {  
        private TestScanner m_scanner;  
  
        public override IScanner GetScanner(IVsTextLines buffer)  
        {  
            if (m_scanner == null)  
            {  
                m_scanner = new TestScanner(buffer);  
            }  
            return m_scanner;  
        }  
    }  
}  
    internal class TestScanner : IScanner  
    {  
        private IVsTextBuffer m_buffer;  
        string m_source;  
  
        public TestScanner(IVsTextBuffer buffer)  
        {  
            m_buffer = buffer;  
        }  
  
        bool IScanner.ScanTokenAndProvideInfoAboutIt(TokenInfo tokenInfo, ref int state)  
        {  
            tokenInfo.Type = TokenType.Unknown;  
            tokenInfo.Color = TokenColor.Text;  
            return true;  
        }  
  
        void IScanner.SetSource(string source, int offset)  
        {  
            m_source = source.Substring(offset);  
        }  
    }  
  
```  
  
## <a name="parsesource-method"></a>ParseSource – metoda  
 Analyzuje zdrojový soubor na základě počtu různé důvody. Tato metoda je uvedena <xref:Microsoft.VisualStudio.Package.ParseRequest> objekt, který popisuje, co se očekává z konkrétní operaci analýzy. <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> Metoda vyvolá složitější analyzátor, který určuje funkcionalitu tokenu a obor. <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> Metoda se používá v podpoře pro operace IntelliSense, jakož i závorek. I když tyto pokročilé operace nepodporují, stále, musíte se vrátit platnou <xref:Microsoft.VisualStudio.Package.AuthoringScope> objekt a která vyžaduje, abyste vytvořte třídu, která implementuje <xref:Microsoft.VisualStudio.Package.AuthoringScope> rozhraní a provádět všechny metody tohoto rozhraní. Všechny metody můžete vrátit hodnotu null. hodnoty ale <xref:Microsoft.VisualStudio.Package.AuthoringScope> samotného objektu nesmí mít hodnotu null.  
  
### <a name="example"></a>Příklad  
 Tento příklad ukazuje na minimální implementace <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> metoda a <xref:Microsoft.VisualStudio.Package.AuthoringScope> třída dostatečná lze umožnit službě jazyk pro kompilaci a fungovat bez ve skutečnosti podpora pokročilejší funkce.  
  
```csharp  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    public class TestLanguageService : LanguageService  
    {  
        public override AuthoringScope ParseSource(ParseRequest req)  
        {  
            return new TestAuthoringScope();  
        }  
    }  
  
    internal class TestAuthoringScope : AuthoringScope  
    {  
        public override string GetDataTipText(int line, int col, out TextSpan span)  
        {  
            span = new TextSpan();  
            return null;  
        }  
  
        public override Declarations GetDeclarations(IVsTextView view,  
                                                     int line,  
                                                     int col,  
                                                     TokenInfo info,  
                                                     ParseReason reason)  
        {  
            return null;  
        }  
  
        public override string Goto(VSConstants.VSStd97CmdID cmd, IVsTextView textView, int line, int col, out TextSpan span)  
        {  
            span = new TextSpan();  
            return null;  
        }  
  
        public override Methods GetMethods(int line, int col, string name)  
        {  
            return null;  
        }  
}  
```  
  
## <a name="name-property"></a>Name – vlastnost  
 Tato vlastnost vrací název služba jazyka. Musí to být stejný jako název věnovat, když služba jazyka byl zaregistrován. Tento název se používá v počet míst, nejvýraznější z nich je <xref:Microsoft.VisualStudio.Package.LanguagePreferences> třídu, kde název se používá pro přístup k registru. Název, vrátí tato vlastnost nesmí lokalizované, protože se používá v registru pro položku registru a názvy klíčů.  
  
### <a name="example"></a>Příklad  
 Tento příklad ukazuje jeden případné použití <xref:Microsoft.VisualStudio.Package.LanguageService.Name%2A> vlastnost. Upozorňujeme, že je zde název pevně: skutečný název mají získávat ze souboru prostředků, je možné při registraci služba jazyka (najdete v části [registrace služby jazyk starší](../../extensibility/internals/registering-a-legacy-language-service1.md)).  
  
```csharp  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    public class TestLanguageService : LanguageService  
    {  
        public override string Name  
        {  
            get { return "Test Language"; }  
        }  
    }  
}  
```  
  
## <a name="instantiating-custom-classes"></a>Vytváření instancí vlastní třídy  
 Následující metody v zadané třídy může být přepsáno za instance vlastní verzí jednotlivé třídy.  
  
### <a name="in-the-languageservice-class"></a>Ve třídě LanguageService  
  
|Metoda|Vrátí – třída|Popis|  
|------------|--------------------|-----------------|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateCodeWindowManager%2A>|<xref:Microsoft.VisualStudio.Package.CodeWindowManager>|Pro podporu vlastních doplňky textového zobrazení.|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateDocumentProperties%2A>|<xref:Microsoft.VisualStudio.Package.DocumentProperties>|Pro podporu vlastní vlastnosti dokumentu.|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateDropDownHelper%2A>|<xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars>|Pro podporu **navigační panel**.|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateExpansionFunction%2A>|<xref:Microsoft.VisualStudio.Package.ExpansionFunction>|K podpoře funkce v šablonách fragmentu kódu.|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateExpansionProvider%2A>|<xref:Microsoft.VisualStudio.Package.ExpansionProvider>|Pro podporu fragmenty kódu (Tato metoda není obvykle potlačena).|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateParseRequest%2A>|<xref:Microsoft.VisualStudio.Package.ParseRequest>|Pro podporu přizpůsobení <xref:Microsoft.VisualStudio.Package.ParseRequest> struktury (Tato metoda není obvykle potlačena).|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateSource%2A>|<xref:Microsoft.VisualStudio.Package.Source>|Pro podporu formátování zdrojového kódu, zadání komentáře znaků a přizpůsobení metoda podpisy.|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateViewFilter%2A>|<xref:Microsoft.VisualStudio.Package.ViewFilter>|Pro podporu příkazy další nabídky.|  
|<xref:Microsoft.VisualStudio.Package.Source.GetColorizer%2A>|<xref:Microsoft.VisualStudio.Package.Colorizer>|Pro podporu, zvýraznění syntaxe (Tato metoda není obvykle potlačena).|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.GetLanguagePreferences%2A>|<xref:Microsoft.VisualStudio.Package.LanguagePreferences>|Pro podporu přístupu k jazykové předvolby. Tuto metodu, musí být implementována, ale můžete vrátit instance základní třídy.|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.GetScanner%2A>|<xref:Microsoft.VisualStudio.Package.IScanner>|K zajištění analyzátor používá k identifikaci typy tokenů na řádek. Tato metoda musí být implementována a <xref:Microsoft.VisualStudio.Package.IScanner> musí být odvozen od.|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A>|<xref:Microsoft.VisualStudio.Package.AuthoringScope>|K zajištění analyzátor používá k identifikaci funkce a obor v rámci celý zdrojový soubor. Tato metoda musí být implementována a musí vracet instanci vaší verzi <xref:Microsoft.VisualStudio.Package.AuthoringScope> třídy. Pokud všechny, které chcete podporovat je zvýraznění syntaxe (což vyžaduje, aby <xref:Microsoft.VisualStudio.Package.IScanner> analyzátor vrátil z <xref:Microsoft.VisualStudio.Package.LanguageService.GetScanner%2A> metoda), musíte nic v této metodě než vrátit verzi <xref:Microsoft.VisualStudio.Package.AuthoringScope> třídu, jejíž všechny metody vrátit hodnotu null. hodnoty.|  
  
### <a name="in-the-source-class"></a>Ve třídě zdroje  
  
|Metoda|Vrátí – třída|Popis|  
|------------|--------------------|-----------------|  
|<xref:Microsoft.VisualStudio.Package.Source.CreateCompletionSet%2A>|<xref:Microsoft.VisualStudio.Package.CompletionSet>|Pro přizpůsobení zobrazení seznamy dokončení IntelliSense (Tato metoda není obvykle potlačena).|  
|<xref:Microsoft.VisualStudio.Package.Source.CreateErrorTaskItem%2A>|<xref:Microsoft.VisualStudio.Package.DocumentTask>|Pro podporu značky v seznamu úkolů seznam chyb; Konkrétně podpora pro funkce nad rámec otevření souboru a přechod na řádek, který chybu způsobil.|  
|<xref:Microsoft.VisualStudio.Package.Source.CreateMethodData%2A>|<xref:Microsoft.VisualStudio.Package.MethodData>|Pro přizpůsobení zobrazení popisů tlačítek informace o parametru IntelliSense.|  
|<xref:Microsoft.VisualStudio.Package.Source.GetCommentFormat%2A>|<xref:Microsoft.VisualStudio.Package.CommentInfo>|Pro podporu přidávání poznámek kódu.|  
|<xref:Microsoft.VisualStudio.Package.Source.CreateAuthoringSink%2A>|<xref:Microsoft.VisualStudio.Package.AuthoringSink>|Pro shromažďování informací o během operace analýzy.|  
  
### <a name="in-the-authoringscope-class"></a>Ve třídě AuthoringScope  
  
|Metoda|Vrátí – třída|Popis|  
|------------|--------------------|-----------------|  
|<xref:Microsoft.VisualStudio.Package.AuthoringScope.GetDeclarations%2A>|<xref:Microsoft.VisualStudio.Package.Declarations>|Poskytuje seznam deklarace například členy nebo typy. Tuto metodu, musí být implementována, ale může vrátit hodnotu null. Pokud tato metoda vrátí objekt platný, objekt musí být instance vaší verzi <xref:Microsoft.VisualStudio.Package.Declarations> třídy.|  
|<xref:Microsoft.VisualStudio.Package.AuthoringScope.GetMethods%2A>|<xref:Microsoft.VisualStudio.Package.Methods>|Poskytuje seznam metoda podpisy pro daný kontext. Tuto metodu, musí být implementována, ale může vrátit hodnotu null. Pokud tato metoda vrátí objekt platný, objekt musí být instance vaší verzi <xref:Microsoft.VisualStudio.Package.Methods> třídy.|  
  
## <a name="language-service-images"></a>Služba jazyka bitové kopie  
 Chcete-li zadat seznam ikon používaných v celém služba jazyka, přepište <xref:Microsoft.VisualStudio.Package.LanguageService.GetImageList%2A> metoda v <xref:Microsoft.VisualStudio.Package.LanguageService> třídy a vrátit <xref:System.Windows.Forms.ImageList> obsahující ikony. Základní <xref:Microsoft.VisualStudio.Package.LanguageService> třída načte výchozí sadu ikon. Vzhledem k tomu, že zadáte přesný obrázek indexu na těchto místech, které je třeba ikony, jak uspořádat vlastní seznamu obrázků je zcela na vás.  
  
### <a name="images-used-in-intellisense-completion-lists"></a>Obrázků použitých v seznamy dokončení IntelliSense  
 Index bitové kopie je pro seznamy dokončení IntelliSense, zadaná pro každou položku v <xref:Microsoft.VisualStudio.Package.Declarations.GetGlyph%2A> metodu <xref:Microsoft.VisualStudio.Package.Declarations> třídy, která je nutné přepsat, pokud chcete zadat index bitové kopie. Hodnota vrácená z <xref:Microsoft.VisualStudio.Package.Declarations.GetGlyph%2A> metoda je index do seznamu obrázků zadané <xref:Microsoft.VisualStudio.Package.CompletionSet> konstruktoru třídy, je stejné seznamu obrázků vrácená z <xref:Microsoft.VisualStudio.Package.LanguageService.GetImageList%2A> metoda v <xref:Microsoft.VisualStudio.Package.LanguageService> – třída (můžete změnit které seznamu obrázků na použít pro <xref:Microsoft.VisualStudio.Package.CompletionSet> Pokud přepíšete <xref:Microsoft.VisualStudio.Package.Source.CreateCompletionSet%2A> metoda v <xref:Microsoft.VisualStudio.Package.Source> třídy zadejte jinou bitovou kopii seznamu).  
  
### <a name="images-used-in-the-navigation-bar"></a>Obrázků použitých v navigačním panelu  
 **Navigační panel** zobrazuje seznam typů a členů a používá se pro rychlý navigační můžete zobrazit ikony. Tyto ikony jsou získávány z <xref:Microsoft.VisualStudio.Package.LanguageService.GetImageList%2A> metoda v <xref:Microsoft.VisualStudio.Package.LanguageService> třídy a nelze ji přepsat speciálně pro **navigační panel**. Indexy, které používají pro každou položku v polích se seznamem jsou zadány, když jsou vyplněna seznamy představující polích se seznamem <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> metoda v <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> – třída (najdete v části [podporu pro navigační panel ve službě jazyk starší](../../extensibility/internals/support-for-the-navigation-bar-in-a-legacy-language-service.md)). Tyto bitové kopie indexy jsou získány nějakým způsobem z analyzátor, obvykle prostřednictvím vaší verzi <xref:Microsoft.VisualStudio.Package.Declarations> třídy. Jak jsou získány indexy je zcela na vás.  
  
### <a name="images-used-in-the-error-list-task-window"></a>Obrázků použitých v úloh okno Seznam chyb  
 Vždy, když <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> analyzátor – metoda (najdete v části [analyzátoru služby starší verze jazyka a skener](../../extensibility/internals/legacy-language-service-parser-and-scanner.md)) dojde k chybě a aby se chyba předá <xref:Microsoft.VisualStudio.Package.AuthoringSink.AddError%2A> metoda v <xref:Microsoft.VisualStudio.Package.AuthoringSink> třídy, v hlásíchybu **Seznam chyb** okno úkolu. Ikony lze přidružit jednotlivé položky, které se zobrazí v okně úlohy a tuto ikonu pocházejí ze seznamu stejnou bitovou kopii, kterou vrátil <xref:Microsoft.VisualStudio.Package.LanguageService.GetImageList%2A> metoda v <xref:Microsoft.VisualStudio.Package.LanguageService> třídy. Výchozí chování sady MPF třídy je nezobrazovat bitovou kopii s chybovou zprávou. Toto chování však můžete přepsat odvozením třídy od <xref:Microsoft.VisualStudio.Package.Source> třídy a přepsání <xref:Microsoft.VisualStudio.Package.Source.CreateErrorTaskItem%2A> metoda. V této metody vytvoříte novou <xref:Microsoft.VisualStudio.Package.DocumentTask> objektu. Před vrácením tento objekt, můžete použít <xref:Microsoft.VisualStudio.Shell.Task.ImageIndex%2A> vlastnost <xref:Microsoft.VisualStudio.Package.DocumentTask> objekt, který chcete nastavit index bitové kopie. To by vypadat podobně jako v následujícím příkladu. Všimněte si, že `TestIconImageIndex` je výčet, který obsahuje seznam všech ikon a je specifická pro tento příklad. Můžete mít jiný způsob identifikace ikony ve službě jazyk.  
  
```csharp  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.Shell;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    class TestSource : Source  
    {  
        public override DocumentTask CreateErrorTaskItem(  
            TextSpan          span,  
            string            filename,  
            string            message,  
            TastPriority      priority,  
            TaskCategory      category,  
            MARKERTYPE        markerType,  
            TaskErrorCategory errorCategory)  
        {  
            DocumentTask taskItem = base.CreateErrorTaskItem(  
                                           span,  
                                           filename,  
                                           message,  
                                           priority,  
                                           category,  
                                           markerType,  
                                           errorCategory);  
            if (errorCategory == TaskErrorCategory.Error)  
            {  
                taskItem.ImageIndex = TestIconImageIndex.Error;  
            }  
            return taskItem;  
        }  
    }  
}  
```  
  
## <a name="the-default-image-list-for-a-language-service"></a>Výchozí seznam obrázků pro služba jazyka  
 Seznam obrázků výchozí součástí základní třídy služeb jazykové sady MPF obsahuje počet ikony přidružené k více běžných prvků jazyka. Hromadným tyto ikony jsou uspořádány do sady šesti variace, odpovídající přístup koncepty veřejné, interní, přítele chráněný, privátní, a zástupce. Například může mít různé ikony pro metodu v závislosti na tom, zda je veřejný, chráněný nebo soukromé.  
  
 Následující výčet určuje typické názvy sadě a Určuje přidružený index. Například založené na výčtu, můžete index obrázku pro chráněná metoda jako `(int)IconImageIndex.Method + (int)IconImageIndex.AccessProtected`. Názvy v tento výčet podle potřeby můžete změnit.  
  
```csharp  
public enum IconImageIndex  
        {  
            // access types  
            AccessPublic = 0,  
            AccessInternal = 1,  
            AccessFriend = 2,  
            AccessProtected = 3,  
            AccessPrivate = 4,  
            AccessShortcut = 5,  
  
            Base = 6,  
            // Each of the following icon type has 6 versions,  
            //corresponding to the access types  
            Class = Base + 0,  
            Constant = Base + 1,  
            Delegate = Base + 2,  
            Enumeration = Base + 3,  
            EnumMember = Base + 4,  
            Event = Base + 5,  
            Exception = Base + 6,  
            Field = Base + 7,  
            Interface = Base + 8,  
            Macro = Base + 9,  
            Map = Base + 10,  
            MapItem = Base + 11,  
            Method = Base + 12,  
            OverloadedMethod = Base + 13,  
            Module = Base + 14,  
            Namespace = Base + 15,  
            Operator = Base + 16,  
            Property = Base + 17,  
            Struct = Base + 18,  
            Template = Base + 19,  
            Typedef = Base + 20,  
            Type = Base + 21,  
            Union = Base + 22,  
            Variable = Base + 23,  
            ValueType = Base + 24,  
            Intrinsic = Base + 25,  
            JavaMethod = Base + 26,  
            JavaField = Base + 27,  
            JavaClass = Base + 28,  
            JavaNamespace = Base + 29,  
            JavaInterface = Base + 30,  
            // Miscellaneous icons with one icon for each type.  
            Error = 187,  
            GreyedClass = 188,  
            GreyedPrivateMethod = 189,  
            GreyedProtectedMethod = 190,  
            GreyedPublicMethod = 191,  
            BrowseResourceFile = 192,  
            Reference = 193,  
            Library = 194,  
            VBProject = 195,  
            VBWebProject = 196,  
            CSProject = 197,  
            CSWebProject = 198,  
            VB6Project = 199,  
            CPlusProject = 200,  
            Form = 201,  
            OpenFolder = 202,  
            ClosedFolder = 203,  
            Arrow = 204,  
            CSClass = 205,  
            Snippet = 206,  
            Keyword = 207,  
            Info = 208,  
            CallBrowserCall = 209,  
            CallBrowserCallRecursive = 210,  
            XMLEditor = 211,  
            VJProject = 212,  
            VJClass = 213,  
            ForwardedType = 214,  
            CallsTo = 215,  
            CallsFrom = 216,  
            Warning = 217,  
        }  
```  
  
## <a name="see-also"></a>Viz také  
 [Implementace služby jazyk starší verze](../../extensibility/internals/implementing-a-legacy-language-service1.md)   
 [Přehled služby starší verze jazyka](../../extensibility/internals/legacy-language-service-overview.md)   
 [Registrace služby jazyk starší verze](../../extensibility/internals/registering-a-legacy-language-service1.md)   
 [Analyzátor a skener služby starší verze jazyka](../../extensibility/internals/legacy-language-service-parser-and-scanner.md)