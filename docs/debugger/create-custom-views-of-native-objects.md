---
title: Vytváření vlastních pohledů nativních objektů
description: Použití rozhraní Natvis přizpůsobit způsob, že sada Visual Studio zobrazí nativní typy v ladicím programu
ms.custom: ''
ms.date: 06/27/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- natvis
dev_langs:
- C++
ms.assetid: 2d9a177a-e14b-404f-a6af-49498eff0bd7
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 01f051faa03e80caa672aee25a6d4abe3104faad
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="create-custom-views-of-native-objects-in-the-visual-studio-debugger"></a>Vytváření vlastních pohledů nativních objektů v ladicím programu sady Visual Studio
Visual Studio Natvis framework umožňuje určit, jak se zobrazí nativní typy v proměnnými ladicího programu sady Visual Studio (například **sledovat** okně **místní hodnoty –** okno a v  **Datatips –**.
  
 Nahrazuje Natvis **autoexp.dat –** soubor, který se používal v dřívějších verzích sady Visual Studio a syntaxe jazyka XML nabídky, lepší diagnostiku, Správa verzí a podpora více souborů.  
  
> [!NOTE]
>  Rozhraní framework Natvis nelze použít pro vizualizaci při:  
>   
>  -  Jsou ladění projektu C++ Windows desktop pomocí ladicího programu typ nastaven na **smíšený**.  
> -   Byste v aplikaci Windows desktop v režimu kompatibility spravované ladění ve smíšeném režimu (**nástroje > Možnosti > ladění > Obecné > použijte režim kompatibility spravované**).  
> -   Ladění Windows desktop aplikace v režimu kompatibility nativní (**nástroje > Možnosti > ladění > Obecné > použijte nativní režim kompatibility**).  
  
##  <a name="BKMK_Why_create_visualizations_"></a> Proč vytváření vizualizací Natvis?  
 Rozhraní framework Natvis slouží k vytvoření vizualizace pravidla pro typy, že které vytvoříte, vývojáři mohou zobrazit je snadno během ladění.  
  
 Například následující obrázek znázorňuje proměnné typu [Windows::UI::Xaml::Controls::TextBox](http://go.microsoft.com/fwlink/?LinkId=258422) , se zobrazí v ladicím programu bez jakékoli vlastní vizualizace použít.  
  
 ![Textové pole Výchozí vizualizace](../debugger/media/dbg_natvis_textbox_default.png "DBG_NATVIS_TextBox_Default")  
  
 Zvýrazněný řádek ukazuje `Text` vlastnost `TextBox` třídy. Hierarchie tříd komplexní ztěžuje tuto hodnotu najdete; Kromě toho ladicího programu není známo, jak interpretovat typ vlastní řetězec používá objekt, takže nevidíte řetězec uchovávat uvnitř textového pole.  
  
 Stejné `TextBox` vypadá mnohem jednodušší v okně proměnné, kdy se mají použít vlastní vizualizace pravidla. Důležité členy třídy lze zobrazit najednou a ladicí program zobrazuje základní řetězcovou hodnotu typu vlastní řetězec.  
  
 ![Textové pole dat pomocí vizualizér](../debugger/media/dbg_natvis_textbox_visualizer.png "DBG_NATVIS_TextBox_Visualizer")  
  
##  <a name="BKMK_Using_Natvis_files"></a> Pomocí souborů Natvis  
 .natvis soubory jsou soubory XML s příponou .natvis. Schéma je definována v **%VSINSTALLDIR%\Xml\Schemas\natvis.xsd**.  
  
 Základní struktura soubor .natvis je jeden nebo více `Type` elementy, kde každý `Type` element reprezentuje položku vizualizace jejíž plně kvalifikovaný název je zadán v typu `Name` atribut.  
  
```xml
<?xml version="1.0" encoding="utf-8"?>  
<AutoVisualizer xmlns="http://schemas.microsoft.com/vstudio/debugger/natvis/2010">  
  <Type Name="MyNamespace::CFoo">  
    .  
    .  
  </Type>  
  
  <Type Name="...">  
    .  
    .  
  </Type>  
</AutoVisualizer>  
```  
  
 Visual Studio poskytuje některé soubory .natvis v **%VSINSTALLDIR%\Common7\Packages\Debugger\Visualizers** složky. Tyto soubory obsahují vizualizace pravidla pro mnoho běžných typů a může sloužit jako příklady při psaní vizualizace pro nové typy.  
  
## <a name="adding-natvis-files-to-your-projects"></a>Přidávání souborů .natvis do vašich projektů  
 Soubory .natvis můžete přidat do libovolného projektu C++.  
  
 Chcete-li přidat nový soubor .natvis, s otevřeného projektu C++, vyberte uzel projektu v **Průzkumníku řešení**a klikněte na tlačítko **Přidat > novou položku > Visual C++ > nástroj > ladicí program vizualizace souboru (.natvis)**. Ladicí program načte Natvis soubory z projektů C++ automaticky. Ve výchozím nastavení jsou Natvis soubory v projektu také vložit do souboru PDB sestavený projektem. To znamená, že při ladění binární vytvořené tento projekt, ladicí program načte soubor Natvis z PDB i v případě, že nemáte otevřený projekt. Pokud nechcete, aby soubor .natvis mají být zahrnuty do pdb, klikněte pravým tlačítkem na soubor .natvis v **Průzkumníku řešení**a v **vlastnosti konfigurace** okno sady **vyloučen ze sestavení**  k **Ano**.  
  
 Doporučuje se, že upravíte soubory Natvis pomocí Visual Studio Any změny provedené při ladění vstoupí v platnost automaticky při ukládání souboru. Můžete také získat z IntelliSense vylepšené prostředí pro úpravy.  
  
 Soubory Natvis, které jsou načteny z PDB platí jenom pro typy modulu, na který odkazuje pdb. Například, pokud Module1.pdb definuje položku pro typ s názvem `Test`, tato položka se použije pouze na **Test** třídy v Module1.dll. Pokud jiný modul také definuje třídu s názvem **Test**, Module1.pdb je natvis položku nelze použít k němu.  
  
##  <a name="BKMK_natvis_location"></a> Nasazení .natvis soubory  
 Pokud váš soubor .natvis se vztahuje pouze na typy, které vytvoříte v projektu sady Visual Studio, nemusíte dělat nic; .natvis je součástí pdb. Můžete, ale přidat .natvis soubory do vašeho adresáře uživatele nebo k adresáři systému Pokud chcete, aby použít pro více projektů.  
  
 Pořadí, ve které .natvis jsou vyhodnocena soubory vypadá takto:  
  
1.  vložený .natvis soubory PDB, kterou ladíte (pokud existuje soubor se stejným názvem v načíst projektu).  
  
2.  .natvis soubory, které jsou součástí načíst projektu jazyka C++ nebo položku nejvyšší úrovně řešení. Tato skupina obsahuje všechny načíst projekty C++, včetně knihovny tříd, ale nezahrnuje projekty jiných jazyků (například nelze načíst soubor .natvis z projektu C#). Pro spustitelný soubor projekty měli byste použít položky řešení pro hostování všechny .natvis soubory, které se již nenacházejí v pdb, protože je k dispozici žádný projekt C++.  
  
3.  Adresář natvis konkrétního uživatele (například **%USERPROFILE%\Documents\Visual Studio 2017\Visualizers** nebo **%USERPROFILE%\My Documents\Visual Studio 2015\Visualizers**).  
  
4.  Adresář Natvis systémové (**%VSINSTALLDIR%\Common7\Packages\Debugger\Visualizers**). Tento adresář je, kde se zkopírují .natvis soubory, které jsou nainstalované s Visual Studio. Pokud máte oprávnění správce, můžete do tohoto adresáře také přidat další soubory.  
  
## <a name="modifying-natvis-files-while-debugging"></a>Změna .natvis souborů při ladění  
 Při ladění projektu, ve kterém je zahrnutá taky můžete upravit soubor .natvis v prostředí IDE. Otevřete soubor v prostředí IDE (pomocí stejné instanci systému Visual Studia, která jsou ladění pomocí), upravte ho a uložte ho. Jakmile je uložen soubor, **sledovat** a **místní hodnoty –** windows je třeba aktualizovat, aby odrážely změny. Pokud upravíte soubor .natvis mimo prostředí IDE, změny se projeví automaticky. Aktualizace systému windows, je možné vyhodnotit **.natvisreload** v **sledovat** okno. Tato akce způsobí, že změny se projeví bez restartování relaci ladění.  
  
 Můžete také přidat nebo odstranit soubory .natvis na řešení, které jsou ladění a Visual Studio. přidá nebo odebere relevantní vizualizace.  
  
 Pokud soubor .natvis je vložen pdb, nelze jej upravovat při ladění.  
  
 Použití **.natvisreload** příkaz když soubor natvis provádíte upgrade na novější verzi (například pokud se změnami do správy zdrojového kódu a chcete načíst nedávné změny tohoto někdo jinak provedené v souboru). Doporučuje se, že upravíte soubory natvis pomocí editoru xml sady Visual Studio.  
  
##  <a name="BKMK_Expressions_and_formatting"></a> Výrazy a formátování  
 Vizualizace Natvis pomocí výrazů C++ zadejte položky, které chcete zobrazit. Kromě vylepšení a omezení výrazů C++ v ladicím programu, které jsou popsány v [kontextu – operátor (C++)](../debugger/context-operator-cpp.md), je třeba si uvědomit následující rozdíly:  
  
-   Natvis výrazy jsou vyhodnocovány v kontextu objektu se vizualizovat, není aktuální rámec zásobníku. Například, pokud používáte `x` ve výrazu Natvis, identifikátor odkazuje na pole s názvem `x` v objektu, se vizualizovat, aby místní proměnné s názvem `x` v aktuálně prováděné funkce. Lokální proměnné ve výrazech Natvis, nelze získat přístup, i když se dostanete globální proměnné.  
  
-   Výrazy Natvis nepovoluje vyhodnocení funkce nebo vedlejší účinky. To znamená, že volání funkcí a operátory přiřazení jsou ignorovány. Protože [ladicího programu vnitřní funkce](../debugger/expressions-in-the-debugger.md#BKMK_Using_debugger_intrinisic_functions_to_maintain_state) jsou vedlejším účinkem free, se může být volně volána jakýkoli výraz Natvis, i když nejsou povoleny jiné volání funkcí.  
  
 K řízení zobrazení výrazu v okně proměnná, můžete použít některý specifikátorů formátu, které jsou popsány v [specifikátory formátu](../debugger/format-specifiers-in-cpp.md#BKMK_Visual_Studio_2012_format_specifiers) části [specifikátory formátu v jazyce C++](../debugger/format-specifiers-in-cpp.md) tématu. Specifikátory formátu jsou ignorovat, pokud položka virtualizace používá se interně pomocí Natvis, například `Size` výrazu v [ArrayItems rozšíření](../debugger/create-custom-views-of-native-objects.md#BKMK_ArrayItems_expansion).  
  
## <a name="natvis-views"></a>Natvis zobrazení  
 Zobrazení Natvis umožňují zobrazit libovolného typu v více než jedním způsobem. Například můžete definovat zobrazení s názvem **jednoduché** , nabízí zjednodušené zobrazení typu. Například je zde vizualizace z `std::vector`:
  
```xml
<Type Name="std::vector&lt;*&gt;">  
    <DisplayString>{{ size={_Mylast - _Myfirst} }}</DisplayString>  
    <Expand>  
        <Item Name="[size]" ExcludeView="simple">_Mylast - _Myfirst</Item>  
        <Item Name="[capacity]" ExcludeView="simple">_Myend - _Myfirst</Item>  
        <ArrayItems>  
            <Size>_Mylast - _Myfirst</Size>  
            <ValuePointer>_Myfirst</ValuePointer>  
        </ArrayItems>  
    </Expand>  
</Type>  
```  
  
 `DisplayString` a `ArrayItems` prvky se používají ve výchozí zobrazení a jednoduché zobrazení při `[size]` a `[capacity]` položky jsou vyloučeny z jednoduchého zobrazení. Můžete použít **, zobrazení** formátovací řetězec zadat alternativní zobrazení. V **sledovat** okno, zadejte jednoduché zobrazení jako **vec,view(simple)**:  
  
 ![Kukátko – okno s jednoduché zobrazení](../debugger/media/watch-simpleview.png "SimpleView sledování")  
  
##  <a name="BKMK_Diagnosing_Natvis_errors"></a> Diagnostikování chyb Natvis  
 Diagnostika Natvis můžete použít k řešení potíží s syntaxe a analyzovat chyby. Když ladicí program výskyt chyb v položce vizualizace, ignoruje chyby a buď zobrazí typu v jeho základním formátu nebo vybere jinou vhodnou vizualizaci. Zjistit, proč se ignoruje položku určité vizualizace a podívejte se, co jsou základní chyby, můžete zapnout diagnostiky Natvis **nástroje > Možnosti > ladění > výstup – okno > Natvis diagnostické zprávy (C++ pouze)** možnost. Chyby se zobrazují v **výstup** okno.  
  
##  <a name="BKMK_Syntax_reference"></a> Reference syntaxe Natvis  
  
###  <a name="BKMK_AutoVisualizer"></a> AutoVisualizer element  
 `AutoVisualizer` Element kořenového uzlu souboru .natvis a obsahuje obor názvů `xmlns:` atribut.  
  
```xml
<?xml version="1.0" encoding="utf-8"?>  
<AutoVisualizer xmlns="http://schemas.microsoft.com/vstudio/debugger/natvis/2010">  
.  
.  
</AutoVisualizer>  
```  
  
###  <a name="BKMK_Type"></a> Typ elementu  
 Základní typ vypadá takto:  
  
```xml
<Type Name="[fully qualified type name]">  
  <DisplayString Condition="[Boolean expression]">[Display value]</DisplayString>  
  <Expand>  
    ...  
  </Expand>  
</Type>  
```  
  
 Určuje:  
  
1.  Jaké typy tuto vizualizaci se mají použít pro ( `Type Name` atributu).  
  
2.  Co hodnotu objektu daného typu by měl vypadat jako ( `DisplayString` element).  
  
3.  Co členy typu by měl vypadat jako když uživatel rozšíří ho v proměnném okně ( `Expand` uzlu).  
  
 **Použitím šablon třídy** `Name` atribut `Type` element přijímá hvězdičku `*` jako zástupný znak, který lze použít pro názvy šablonované tříd:  
  
```xml
<Type Name="ATL::CAtlArray&lt;*&gt;">  
    <DisplayString>{{Count = {m_nSize}}}</DisplayString>  
</Type>  
  
```  
  
 V tomto příkladu se používá stejné vizualizace, zda je objekt `CAtlArray<int>` nebo `CAtlArray<float>`. Pokud je položka konkrétní vizualizace pro `CAtlArray<float>`, pak má přednost před obecné jeden.  
  
 Všimněte si, že parametry šablony lze odkazovat v položce vizualizaci pomocí makra $T1, $T2 a tak dále. Příklady těchto maker, najdete v tématu .natvis soubory dodaný pomocí sady Visual Studio.  
  
####  <a name="BKMK_Visualizer_type_matching"></a> Vizualizér odpovídající typ  
 Pokud položku vizualizace se nepodaří ověřit, se používá k dispozici další vizualizaci.  
  
#### <a name="inheritable-attribute"></a>Zděditelné atribut  
 Můžete určit, zda vizualizace platí pouze pro základní typ nebo základní typ a všechny odvozené typy s nepovinným `Inheritable` atribut. V následujícím příkladu platí jenom pro vizualizaci `BaseClass` typu:  
  
```xml
<Type Name="Namespace::BaseClass" Inheritable="true">  
    <DisplayString>{{Count = {m_nSize}}}</DisplayString>  
</Type>  
```  
  
 Výchozí hodnota `Inheritable` je `true`.  
  
#### <a name="priority-attribute"></a>Atribut s prioritou  
 `Priority` Atribut určuje pořadí, ve kterém se používají alternativní definice, definice selže-li analyzovat. Možné hodnoty `Priority` jsou: `Low`, `MediumLow`,`Medium`, `MediumHigh`, a `High`, a výchozí hodnota je `Medium`.  
  
 Atribut s prioritou by měl použít pouze k rozlišení mezi priority v rámci stejného souboru .natvis není mezi různé soubory.  
  
 V následujícím příkladu se nám nejdřív analyzovat na položku, která odpovídá 2015 STL a pokud to nepomůže analyzovat, používáme položka alternativní verze 2013 STL:  
  
```xml
<!-- VC 2013 -->  
<Type Name="std::reference_wrapper&lt;*&gt;" Priority="MediumLow">  
     <DisplayString>{_Callee}</DisplayString>  
    <Expand>  
        <ExpandedItem>_Callee</ExpandedItem>  
    </Expand>  
</Type>  
  
<!-- VC 2015 -->  
<Type Name="std::reference_wrapper&lt;*&gt;">  
    <DisplayString>{*_Ptr}</DisplayString>  
    <Expand>  
        <Item Name="[ptr]">_Ptr</Item>  
    </Expand>  
</Type>  
```  
  
####  <a name="BKMK_Versioning"></a> Element verze  
 Použití `Version` elementu, který chcete obor vizualizacemi na určitých modulech a jejich verze, která název kolizí můžete minimalizovat a různé vizualizace lze použít pro různé verze typů. Příklad:  
  
```xml
<Type Name="DirectUI::Border">  
  <Version Name="Windows.UI.Xaml.dll" Min="1.0" Max="1.5"/>  
  <DisplayString>{{Name = {*(m_pDO->m_pstrName)}}}</DisplayString>  
  <Expand>  
    <ExpandedItem>*(CBorder*)(m_pDO)</ExpandedItem>  
  </Expand>  
</Type>  
```  
  
 V tomto příkladu je použitelné jen pro vizualizaci `DirectUI::Border` typ v nalezen `Windows.UI.Xaml.dll` z verze 1.0 k 1.5. Přidávání elementů verze rozsahy položka vizualizace konkrétního modulu a verze a snižuje nechtěnému neshody. Ale pokud typ je definován v běžné soubor hlaviček, který je používán jinou moduly, verzí vizualizace není použijí, když typ není zadaný modul.  
  
#### <a name="optional-attribute"></a>Optional – atribut  
 `Optional` Atribut se může zobrazit ve všech uzlech. Pokud žádné dílčím výrazu uvnitř volitelné uzlu se nepodařilo analyzovat, tento uzel se ignoruje, ale zbývající typ elementu je stále platný. V následující typu `[State]` je jiný volitelná, ale `[Exception]` je volitelný.  To znamená, že pokud `MyNamespace::MyClass` obsahuje pole s názvem _`M_exceptionHolder`, bude i nadále zobrazovat `[State]` uzlu a `[Exception]` uzlu, ale pokud `_M_exceptionHolder` chybí, zobrazí se pouze `[State]` uzlu.
  
```xml
<Type Name="MyNamespace::MyClass">  
    <Expand>  
      <Item Name="[State]">_M_State</Item>  
      <Item Name="[Exception]" Optional="true">_M_exceptionHolder</Item>  
    </Expand>  
</Type>  
```  
  
###  <a name="BKMK_Condition_attribute"></a> Atribut podmínky  
 Volitelné `Condition` atribut je k dispozici pro mnoho prvků vizualizace a určuje, kdy by vizualizace pravidla používat. Pokud výraz do atribut podmínku přeloží na `false`, pak není použita zadané elementem pravidlo vizualizace. Pokud se vyhodnotí jako true, nebo pokud neexistuje žádné `Condition` atribut, pak vizualizace pravidlo se použije pro typ. Můžete použít pro tento atribut `if-else` logiku v položkách vizualizace. Například následující vizualizace má dva `DisplayString` prvky pro inteligentní ukazatel typu:  
  
```xml
<Type Name="std::auto_ptr&lt;*&gt;">  
  <DisplayString Condition="_Myptr == 0">empty</DisplayString>  
  <DisplayString>auto_ptr {*_Myptr}</DisplayString>  
  <Expand>  
    <ExpandedItem>_Myptr</ExpandedItem>  
  </Expand>  
</Type>  
  
```  
  
 Když `_Myptr` člen `null`, podmínku první `DisplayString` element překládá `true`tak, aby se zobrazí formulář. Když `_Myptr` člen není `null`, je podmínka vyhodnocena jako `false`a druhá `DisplayString` element se zobrazuje.  
  
### <a name="includeview-and-excludeview-attributes"></a>Atributy IncludeView a ExcludeView  
 Tyto atributy určují prvky, které se nezobrazí nebo nezobrazuje v různá zobrazení. Například uděleno specifikaci Natvis `std::vector`:  
  
```xml
<Type Name="std::vector&lt;*&gt;">  
    <DisplayString>{{ size={_Mylast - _Myfirst} }}</DisplayString>  
    <Expand>  
        <Item Name="[size]" ExcludeView="simple">_Mylast - _Myfirst</Item>  
        <Item Name="[capacity]" ExcludeView="simple">_Myend - _Myfirst</Item>  
        <ArrayItems>  
            <Size>_Mylast - _Myfirst</Size>  
            <ValuePointer>_Myfirst</ValuePointer>  
        </ArrayItems>  
    </Expand>  
</Type>  
```  
  
 Jednoduché zobrazení nezobrazuje [velikost] a [kapacity] položky v režimu jednoduchého zobrazení. Pokud měl použili jsme `IncludeView="simple"` místo `ExcludeView`, `[size]` a `[capacity]` položky by se zobrazit v jednoduché zobrazení, ne ve výchozím zobrazení.  
  
 Můžete použít `IncludeView` a `ExcludeView` atributy na typech i na jednotlivé členy.  
  
###  <a name="BKMK_DisplayString"></a> Element DisplayString  
 A `DisplayString` element určuje řetězec, která se má zobrazit jako hodnotu proměnné. Přijímá libovolný řetězce smíšený s výrazy. Všechno uvnitř složené závorky interpretována jako výraz. Například `DisplayString` položka takto:  
  
```xml
<Type Name="CPoint">  
  <DisplayString>{{x={x} y={y}}}</DisplayString>   
</Type>  
  
```  
  
 Znamená že proměnné typu `CPoint` se zobrazují jako v tomto obrázku:  
  
 ![Pomocí elementu DisplayString](../debugger/media/dbg_natvis_cpoint_displaystring.png "DBG_NATVIS_CPoint_DisplayString")  
  
 V `DisplayString` výrazu `x` a `y`, které jsou členy `CPoint`, jsou uvnitř složené závorky a tak jejich hodnoty jsou vyhodnocovány. Výraz také ukazuje, jak můžete pomocí dvojité složené závorky vyhnuli složené závorky ( `{{` nebo `}}` ).  
  
> [!NOTE]
>  `DisplayString` Element je jediným prvkem, který přijímá libovolný řetězce a syntaxe složených závorek. Všechny ostatní prvky vizualizace přijmout pouze výrazy, které se vyhodnocují pomocí ladicího programu.  
  
###  <a name="BKMK_StringView"></a> StringView  
 `StringView` Element definuje výraz, jehož hodnota přechází k odeslání do vizualizér integrovaný text. Předpokládejme například, že máme následující vizualizaci `ATL::CStringT` typu:  
  
```xml
<Type Name="ATL::CStringT&lt;wchar_t,*&gt;">  
  <DisplayString>{m_pszData,su}</DisplayString>  
</Type>
```  
  
 Zobrazí vizualizace `CStringT` objektu v okně proměnná takto:   
  
 ![Element CStringT DisplayString](../debugger/media/dbg_natvis_displaystring_cstringt.png "DBG_NATVIS_DisplayString_CStringT")  
  
 Přidání `StringView` element označuje ladicí program, že tato hodnota může prohlížet vizualizace text:  
  
```xml
<Type Name="ATL::CStringT&lt;wchar_t,*&gt;">
  <DisplayString>{m_pszData,su}</DisplayString>  
  <StringView>m_pszData,su</StringView>  
</Type>  
```  
  
 Všimněte si ikonu lupy zobrazit vedle hodnota níže. Výběr ikonu spustí vizualizér text, který se zobrazí řetězec, `m_pszData` odkazuje na.  
  
 ![Data CStringT s StringView vizualizér](../debugger/media/dbg_natvis_stringview_cstringt.png "DBG_NATVIS_StringView_CStringT")  
  
> [!NOTE]
>  Všimněte si, že výraz `{m_pszData,su}` zahrnuje specifikátorem formátu C++ `su` zobrazuje hodnota jako řetězec znaků Unicode. V tématu [specifikátory formátu v jazyce C++](../debugger/format-specifiers-in-cpp.md) Další informace.  
  
###  <a name="BKMK_Expand"></a> Rozbalte položku  
 `Expand` Uzel slouží k přizpůsobení podřízené objekty typu vizualizovaných, když ho uživatel rozšíří v proměnné systému windows. Přijímá seznam podřízených uzlů, které definují podřízené elementy.  
  
 `Expand` Uzel je volitelné.  
  
-   Pokud `Expand` uzlu není zadané v položce vizualizace se používají výchozí pravidla rozšíření pro Visual Studio.  
  
-   Pokud `Expand` uzel je zadán bez podřízených uzlů v něm, typ nebude rozšíření v ladicího programu.  
  
####  <a name="BKMK_Item_expansion"></a> Rozšíření položky  
 `Item` Prvek je nejzákladnější a nejběžnější elementu, který chcete použít v `Expand` uzlu. `Item` definuje jeden podřízený element. Předpokládejme například, že máte `CRect` třídy s `top`, `left`, `right`, a `bottom` jako jeho pole a následující položku vizualizaci:  
  
```xml
<Type Name="CRect">  
  <DisplayString>{{top={top} bottom={bottom} left={left} right={right}}}</DisplayString>  
  <Expand>  
    <Item Name="Width">right - left</Item>  
    <Item Name="Height">bottom - top</Item>  
  </Expand>  
</Type>  
  
```  
  
 `CRect` Typ bude vypadat například takto:  
  
 ![CRect s rozšíření element položky](../debugger/media/dbg_natvis_expand_item_crect1.png "DBG_NATVIS_Expand_Item_CRect1")  
  
 Výrazy určené v `Width` a `Height` elementy jsou vyhodnotit a ve sloupci hodnota. `[Raw View]` Uzel se automaticky vytvoří pomocí ladicího programu vždy, když se používá vlastní rozšíření. Je rozbalený výše a zobrazit, jak se liší od jeho vizualizace nezpracovaná zobrazení objektu na snímku obrazovky. Výchozí rozšíření sady Visual Studio vytvoří podstrom pro základní třídy a uvádí všechna data členy základní třídy jako podřízené objekty.  
  
> [!NOTE]
>  Pokud výraz elementu položku odkazuje na komplexního typu, `Item` uzel je rozšíření.  
  
####  <a name="BKMK_ArrayItems_expansion"></a> ArrayItems rozšíření  
 Použití `ArrayItems` uzlu tak, aby měl ladicího programu sady Visual Studio interpretovat typ jako pole a jeho jednotlivé prvky zobrazení. Vizualizaci `std::vector` je dobrým příkladem:  
  
```xml
<Type Name="std::vector&lt;*&gt;">  
  <DisplayString>{{size = {_Mylast - _Myfirst}}}</DisplayString>  
  <Expand>  
    <Item Name="[size]">_Mylast - _Myfirst</Item>  
    <Item Name="[capacity]">(_Myend - _Myfirst)</Item>  
    <ArrayItems>  
      <Size>_Mylast - _Myfirst</Size>  
      <ValuePointer>_Myfirst</ValuePointer>  
    </ArrayItems>  
  </Expand>  
</Type>  
```  
  
 A `std::vector` jednotlivými jednotlivé prvky v rozbaleném v okně proměnné:  
  
 ![pomocí rozšíření ArrayItems std::Vector](../debugger/media/dbg_natvis_expand_arrayitems_stdvector.png "DBG_NATVIS_Expand_ArrayItems_StdVector")  
  
 Minimálně `ArrayItems` uzel musí mít:  
  
1.  A `Size` výraz (který se musí vyhodnotit celé) v ladicím programu pochopit délka pole  
  
2.  A `ValuePointer` výraz, který by měla odkazovat na prvním elementem (která musí být ukazatel typem elementu, který není `void*`).  
  
 Dolní mez pole Výchozí hodnota je 0. Hodnotu lze přepsat pomocí `LowerBound` – element (příklady naleznete v souborech .natvis dodaný pomocí sady Visual Studio).  
  
 Teď můžete použít `[]` operátor s `ArrayItems` rozšíření, například `vector[i]`. [] – Operátor lze použít s žádné vizualizace jednorozměrná pole, která používá `ArrayItems` nebo `IndexListItems`i v případě, že vlastní typ neumožňuje tento operátor (například `CATLArray`).  
  
 Multidimenzionální pole můžete také zadat. Ladicí program potřebuje jen mírně Další informace pro správné zobrazení podřízených elementů v takovém případě:  
  
```xml
<Type Name="Concurrency::array&lt;*,*&gt;">  
  <DisplayString>extent = {_M_extent}</DisplayString>  
  <Expand>  
    <Item Name="extent">_M_extent</Item>  
    <ArrayItems Condition="_M_buffer_descriptor._M_data_ptr != 0">  
      <Direction>Forward</Direction>  
      <Rank>$T2</Rank>  
      <Size>_M_extent._M_base[$i]</Size>  
      <ValuePointer>($T1*) _M_buffer_descriptor._M_data_ptr</ValuePointer>  
    </ArrayItems>  
  </Expand>  
</Type>  
```  
  
 `Direction` Určuje, zda pole hlavní řádek nebo sloupec hlavní pořadí. `Rank` Určuje pořadí pole. `Size` Element přijímá implicitní `$i` parametr, který nahrazuje s indexem dimenze najít délka pole v této dimenzi. Například v předchozím příkladu výše výraz `_M_extent.M_base[0]` získat délku 0-té dimenze `_M_extent._M_base[1]` 1. a tak dále.  
  
 Tady je způsob, jakým dvourozměrná `Concurrency::array` objekt vypadá v ladicím programu:  
  
 ![Dvourozměrná pole s ArrayItems rozšíření](../debugger/media/dbg_natvis_expand_arrayitems_2d.png "DBG_NATVIS_Expand_ArrayItems_2D")  
  
####  <a name="BKMK_IndexListItems_expansion"></a> IndexListItems rozšíření  
 Můžete použít `ArrayItems` rozšíření, pouze v případě, že jsou elementy pole nastíněny souvisle v paměti. Ladicí program získá na další prvek jednoduše zvyšující jeho ukazatele k aktuálnímu elementu. Pro podporu případy, kdy potřebujete upravit index pro uzel hodnoty `IndexListItems` uzly můžete použít. Tady je vizualizace pomocí `IndexListItems` uzlu:  
  
```xml
<Type Name="Concurrency::multi_link_registry&lt;*&gt;">  
  <DisplayString>{{size = {_M_vector._M_index}}}</DisplayString>  
  <Expand>  
    <Item Name="[size]">_M_vector._M_index</Item>  
    <IndexListItems>  
      <Size>_M_vector._M_index</Size>  
      <ValueNode>*(_M_vector._M_array[$i])</ValueNode>  
    </IndexListItems>  
  </Expand>  
</Type>  
```  
  
 Teď můžete použít `[]` operátor s `IndexListItems` rozšíření, například `vector[i]`. `[]` Operátor lze použít s žádné vizualizace jednorozměrná pole, která používá `ArrayItems` nebo `IndexListItems`i v případě, že vlastní typ neumožňuje tento operátor (například `CATLArray`).  
  
 Jediným rozdílem mezi `ArrayItems` a `IndexListItems` je, že `ValueNode` očekává úplné výraz, který se i<sup>tý</sup> element s implicitní `$i` parametr.  
  
####  <a name="BKMK_LinkedListItems_expansion"></a> LinkedListItems rozšíření  
 Pokud typ vizualizovaných představuje odkazovaného seznamu, ladicího programu můžete zobrazit jeho podřízených objektů pomocí `LinkedListItems` uzlu. Tady je vizualizaci `CAtlList` zadejte pomocí této funkce:  
  
```xml
<Type Name="ATL::CAtlList&lt;*,*&gt;">  
  <DisplayString>{{Count = {m_nElements}}}</DisplayString>  
  <Expand>  
    <Item Name="Count">m_nElements</Item>  
    <LinkedListItems>  
      <Size>m_nElements</Size>  
      <HeadPointer>m_pHead</HeadPointer>  
      <NextPointer>m_pNext</NextPointer>  
      <ValueNode>m_element</ValueNode>  
    </LinkedListItems>  
  </Expand>  
</Type>  
```  
  
 `Size` Element odkazuje na seznamu. `HeadPointer` odkazuje na první prvek `NextPointer` odkazuje na další prvek a `ValueNode` odkazuje na hodnotu položky.  
  
-   `NextPointer` a `ValueNode` výrazy jsou vyhodnocovány v kontextu elementu odkazovaného seznamu uzel a není nadřazený typ seznamu. V předchozím příkladu `CAtlList` má `CNode` – třída (nalezen v `atlcoll.h`), která představuje uzel odkazovaného seznamu. `m_pNext` a `m_element` jsou pole této `CNode` třída a není `CAtlList` třídy.  
  
-   `ValueNode` Může být prázdné nebo mají `this` odkazovat na uzel odkazovaného seznamu.  
  
#### <a name="customlistitems-expansion"></a>CustomListItems rozšíření  
 `CustomListItems` Rozšíření umožňuje psát vlastní logiky pro procházení struktura dat, jako je například zatřiďovací tabulku. Měli byste použít `CustomListItems` k vizualizaci dat lze vyjádřit pomocí výrazů C++ struktury, ve které všechno, co potřebujete k vyhodnocení, ale poměrně nehodí tvaru pro `ArrayItems`, `TreeItems`, nebo `LinkedListItems.`  
  
 Vizualizér pro CAtlMap je příkladem kde vynikající `CustomListItems` je vhodné.  
  
```xml
<Type Name="ATL::CAtlMap&lt;*,*,*,*&gt;">  
    <AlternativeType Name="ATL::CMapToInterface&lt;*,*,*&gt;"/>  
    <AlternativeType Name="ATL::CMapToAutoPtr&lt;*,*,*&gt;"/>  
    <DisplayString>{{Count = {m_nElements}}}</DisplayString>  
    <Expand>  
      <CustomListItems MaxItemsPerView="5000" ExcludeView="Test">  
        <Variable Name="iBucket" InitialValue="-1" />  
        <Variable Name="pBucket" InitialValue="m_ppBins == nullptr ? nullptr : *m_ppBins" />  
        <Variable Name="iBucketIncrement" InitialValue="-1" />  
  
        <Size>m_nElements</Size>  
        <Exec>pBucket = nullptr</Exec>  
        <Loop>  
          <If Condition="pBucket == nullptr">  
            <Exec>iBucket++</Exec>  
            <Exec>iBucketIncrement = __findnonnull(m_ppBins + iBucket, m_nBins - iBucket)</Exec>  
            <Break Condition="iBucketIncrement == -1" />  
            <Exec>iBucket += iBucketIncrement</Exec>  
            <Exec>pBucket = m_ppBins[iBucket]</Exec>  
          </If>  
          <Item>pBucket,na</Item>  
          <Exec>pBucket = pBucket->m_pNext</Exec>  
        </Loop>  
      </CustomListItems>  
    </Expand>  
</Type>  
```  

Můžete použít `Exec` ke spouštění kódu uvnitř `CustomListItems` pomocí proměnných a objektů definovaných v rozšíření `CustomListItems` rozšíření. Nemůžete použít `Exec` k vyhodnocení funkce.

Můžete použít logické operátory, aritmetické operátory a operátory přiřazení s `Exec`.

Podporovány jsou následující vnitřní funkce:

- `strlen, wcslen, strnlen, wcsnlen, strcmp, wcscmp, _stricmp, _strcmpi, _wcsicmp, strncmp, wcsncmp, _strnicmp, _wcsnicmp, memcmp, memicmp, wmemcmp, strchr, wcschr, memchr, wmemchr, strstr, wcsstr, __log2, __findNonNull`
- `GetLastError, TlsGetValue, DecodeHString, WindowsGetStringLen, WindowsGetStringRawBuffer, WindowsCompareStringOrdinal, RoInspectCapturedStackBackTrace, CoDecodeProxy, GetEnvBlockLength, DecodeWinRTRestrictedException, DynamicMemberLookup, DecodePointer, DynamicCast`
- `ConcurrencyArray_OperatorBracket_idx // Concurrency::array<>::operator[index<>] and operator(index<>)`
- `ConcurrencyArray_OperatorBracket_int // Concurrency::array<>::operator(int, int, ...)`
- `ConcurrencyArray_OperatorBracket_tidx // Concurrency::array<>::operator[tiled_index<>] and operator(tiled_index<>)`
- `ConcurrencyArrayView_OperatorBracket_idx // Concurrency::array_view<>::operator[index<>] and operator(index<>)`
- `ConcurrencyArrayView_OperatorBracket_int // Concurrency::array_view<>::operator(int, int, ...)`
- `ConcurrencyArrayView_OperatorBracket_tidx // Concurrency::array_view<>::operator[tiled_index<>] and operator(tiled_index<>)`
- `Stdext_HashMap_Int_OperatorBracket_idx`
- `Std_UnorderedMap_Int_OperatorBracket_idx`
- `TreeTraverse_Init // Initializes a new tree traversal`
- `TreeTraverse_Next // Returns nodes in a tree`
- `TreeTraverse_Skip // Skips nodes in a pending tree traversal`
  
####  <a name="BKMK_TreeItems_expansion"></a> TreeItems rozšíření  
 Pokud typ vizualizovaných představuje stromu, můžete provede stromu a zobrazit podřízené pomocí ladicího programu `TreeItems` uzlu. Tady je vizualizaci `std::map` zadejte pomocí této funkce:  
  
```xml
<Type Name="std::map&lt;*&gt;">  
  <DisplayString>{{size = {_Mysize}}}</DisplayString>  
  <Expand>  
    <Item Name="[size]">_Mysize</Item>  
    <Item Name="[comp]">comp</Item>  
    <TreeItems>  
      <Size>_Mysize</Size>  
      <HeadPointer>_Myhead->_Parent</HeadPointer>  
      <LeftPointer>_Left</LeftPointer>  
      <RightPointer>_Right</RightPointer>  
      <ValueNode Condition="!((bool)_Isnil)">_Myval</ValueNode>  
    </TreeItems>  
  </Expand>  
</Type>  
```  
  
 Syntaxe je podobná `LinkedListItems` uzlu. `LeftPointer`, `RightPointer`, a `ValueNode` jsou vyhodnocovány v kontextu třídy uzlu stromu, a `ValueNode` může být prázdné nebo mají `this` odkazovat na uzel stromu.  
  
####  <a name="BKMK_ExpandedItem_expansion"></a> ExpandedItem rozšíření  
 `ExpandedItem` Element slouží k zobrazení vlastností členů základní třídy nebo data, jako kdyby byly podřízené objekty typu vizualizovaných vygenerujte agregované podřízené zobrazení. Vyhodnotí zadaný výraz a podřízených uzlů výsledku se připojí k seznamu podřízené vizualizovaných typu. Předpokládejme například, že máme inteligentní ukazatel typu `auto_ptr<vector<int>>`, obvykle zobrazuje jako:  
  
 ![Automatické&#95;ptr&#60;vektoru&#60;int&#62; &#62; výchozí rozšíření](../debugger/media/dbg_natvis_expand_expandeditem_default.png "DBG_NATVIS_Expand_ExpandedItem_Default")  
  
 Zobrazit hodnoty vektoru, máte k podrobnostem dvě úrovně v okně proměnné prošla _Myptr člen. Přidáním `ExpandedItem` elementu, můžete eliminovat `_Myptr` proměnné z hierarchie a přímo zobrazit elementů vektorové::  
  
```xml
<Type Name="std::auto_ptr&lt;*&gt;">  
  <DisplayString>auto_ptr {*_Myptr}</DisplayString>  
  <Expand>  
    <ExpandedItem>_Myptr</ExpandedItem>  
  </Expand>  
</Type>  
```  
  
 ![Automatické&#95;ptr&#60;vektoru&#60;int&#62; &#62; ExpandedItem rozšíření](../debugger/media/dbg_natvis_expand_expandeditem_visualized.png "DBG_NATVIS_Expand_ExpandedItem_Visualized")  
  
 Následující příklad ukazuje, jak k agregaci vlastnosti ze základní třídy v odvozené třídě. Předpokládejme, že `CPanel` třída odvozená z `CFrameworkElement`. Místo opakující se vlastnosti, které pocházejí z základní `CFrameworkElement` třídy, `ExpandedItem` uzel umožňuje tyto vlastnosti, který bude přidán do seznamu podřízené `CPanel` – třída. **Nd** specifikátor formátu, který vypne vizualizace odpovídající pro odvozené třídy, je nutné v tomto poli. V opačném výraz `*(CFrameworkElement*)this` způsobí, že `CPanel` vizualizace znovu použít, protože vizualizace výchozí typ pravidel porovnávání považuje za nejvhodnější. Pomocí **nd** specifikátor formátu dá pokyn ladicí program na používat vizualizace základní třídu nebo rozšíření výchozí základní třídy, pokud základní třídy nemá vizualizace.  
  
```xml
<Type Name="CPanel">  
  <DisplayString>{{Name = {*(m_pstrName)}}}</DisplayString>  
  <Expand>  
    <Item Name="IsItemsHost">(bool)m_bItemsHost</Item>  
    <ExpandedItem>*(CFrameworkElement*)this,nd</ExpandedItem>  
  </Expand>  
</Type>  
```  
  
####  <a name="BKMK_Synthetic_Item_expansion"></a> Syntetické rozšíření položky  
 Kde `ExpandedItem` element poskytuje plošší zobrazení dat odstraněním hierarchie, `Synthetic` uzel nemá jako opak. Umožňuje vytvořit umělé podřízený prvek (to znamená, podřízený element a která je výsledkem výrazu není). Tento podřízený element může obsahovat vlastní elementy podřízené objekty. V následujícím příkladu, vizualizaci `Concurrency::array` zadejte používá `Synthetic` uzel a zobrazit diagnostické zprávy pro uživatele:  
  
```xml
<Type Name="Concurrency::array&lt;*,*&gt;">  
  <DisplayString>extent = {_M_extent}</DisplayString>  
  <Expand>  
    <Item Name="extent" Condition="_M_buffer_descriptor._M_data_ptr == 0">_M_extent</Item>  
    <ArrayItems Condition="_M_buffer_descriptor._M_data_ptr != 0">  
      <Rank>$T2</Rank>  
      <Size>_M_extent._M_base[$i]</Size>  
      <ValuePointer>($T1*) _M_buffer_descriptor._M_data_ptr</ValuePointer>  
    </ArrayItems>  
    <Synthetic Name="Array" Condition="_M_buffer_descriptor._M_data_ptr == 0">  
      <DisplayString>Array members can be viewed only under the GPU debugger</DisplayString>  
    </Synthetic>  
  </Expand>  
</Type>  
  
```  
  
 ![Concurrency::Array s syntetické element rozšíření](../debugger/media/dbg_natvis_expand_synthetic.png "DBG_NATVIS_Expand_Synthetic")  
  
###  <a name="BKMK_HResult"></a> HResult  
 `HResult` Element umožňuje přizpůsobit informace, které se zobrazí u HRESULT v ladicího programu. `HRValue` Element musí obsahovat hodnotu 32-bit HRESULT, který je k přizpůsobení. `HRDescription` Element obsahuje informace, které se zobrazí v ladicím programu.  
  
```  
  
<HResult Name="MY_E_COLLECTION_NOELEMENTS">  
  <HRValue>0xABC0123</HRValue>  
  <HRDescription>No elements in the collection.</HRDescription>  
</HResult>  
```  
  
###  <a name="BKMK_UIVisualizer"></a> UIVisualizer  
 A `UIVisualizer` element zaregistruje grafické vizualizéru modul plug-in s ladicím programem. Modul plug-in grafické vizualizéru vytvoří dialogové okno nebo jiné rozhraní k zobrazení proměnné nebo objekt způsobem, který je vhodný pro jeho datového typu. Vizualizér modul plug-in musí být vytvořené jako [VSPackage](../extensibility/internals/vspackages.md) a je nutné vystavit služba, která mohou být spotřebovávána ladicího programu. .Natvis soubor obsahuje informace o registraci pro modul plug-in, například jeho název, identifikátor GUID služby zveřejněné a také typy, které můžete vizualizovat.  
  
 Tady je příklad elementu UIVisualizer:  
  
```xml
<?xml version="1.0" encoding="utf-8"?>  
<AutoVisualizer xmlns="http://schemas.microsoft.com/vstudio/debugger/natvis/2010">  
    <UIVisualizer ServiceId="{5452AFEA-3DF6-46BB-9177-C0B08F318025}"   
        Id="1" MenuName="Vector Visualizer"/>  
    <UIVisualizer ServiceId="{5452AFEA-3DF6-46BB-9177-C0B08F318025}"   
        Id="2" MenuName="List Visualizer"/>  
.  
.  
</AutoVisualizer>  
```  
  
 A `UIVisualizer` je identifikována `ServiceId`  -  `Id` atribut pár. `ServiceId` je identifikátor GUID služby vystavené balíček vizualizér `Id` je jedinečný identifikátor, který slouží k odlišení vizualizérech, pokud služba poskytuje více než jeden vizualizér. V předchozím příkladu obsahuje stejnou službu vizualizér dvě vizualizérech.  
  
 `MenuName` Atribut je co uživatelé zobrazí jako název vizualizér po otevření v rozevírací nabídce vedle ikonu lupy ve windows proměnné ladicího programu, například:  
  
 ![Místní nabídky nabídky UIVisualizer](../debugger/media/dbg_natvis_vectorvisualizer.png "DBG_NATVIS_VectorVisualizer")  
  
 Každý typ definované v souboru .natvis musí explicitně seznamu vizualizérech uživatelského rozhraní, které je zobrazit. Ladicí program odpovídá vizualizér odkazy v typ položky tak, aby odpovídaly typy s registrované vizualizérech. Můžete například zadat následující položku pro `std::vector` odkazuje UIVisualizer v našem příkladu předchozí.  
  
```xml
<Type Name="std::vector&lt;int,*&gt;">  
  <UIVisualizer ServiceId="{5452AFEA-3DF6-46BB-9177-C0B08F318025}" Id="1" />  
</Type>  
```  
  
 Můžete zobrazit příklad UIVisualizer v rozšíření sledovat Image použít k zobrazení rastrové obrázky v paměti: [ImageWatch](https://visualstudiogallery.msdn.microsoft.com/e682d542-7ef3-402c-b857-bbfba714f78d)  
  
### <a name="customvisualizer-element"></a>CustomVisualizer element  
 `CustomVisualizer` je bod rozšíření, která určuje příponu VSIX, který může zapisovat k řízení vizualizace v kódu, který běží v sadě Visual Studio. Další informace o vytváření VSIX rozšíření najdete v tématu [Visual Studio SDK](../extensibility/visual-studio-sdk.md). Zápis vlastních vizualizéru je mnohem víc pracovní než zápis definici XML natvis, ale jste bez omezení, o jaké natvis podporuje nebo nepodporuje. Vlastní vizualizérech mít přístup k úplnou sadu rozhraní API, který můžete použít k dotazu a upravit proces pozastaven nebo komunikovat s dalšími částmi sady Visual Studio pro rozšíření ladicí program.  
  
 Můžete použít `Condition`, `IncludeView`, a `ExcludeView` atributy u CustomVisualizer elementů.