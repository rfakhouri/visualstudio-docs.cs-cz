---
title: V editoru | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], new - architecture
ms.assetid: 822cbb8d-7ab4-40ee-bd12-44016ebcce81
caps.latest.revision: "31"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1876f334ad1b444b464ecc420767dea90baed6b3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="inside-the-editor"></a>V editoru
Editor se skládá z několika různé subsystémy, které jsou navržené tak, aby editoru samostatné modelu text z textového zobrazení a uživatelské rozhraní.  
  
 Tyto části popisují různé aspekty editoru:  
  
-   [Přehled subsystémů](../extensibility/inside-the-editor.md#overview)  
  
-   [Model textu](../extensibility/inside-the-editor.md#textmodel)  
  
-   [Zobrazení textu](../extensibility/inside-the-editor.md#textview)  
  
 Tyto části popisují funkce editoru:  
  
-   [Značky a třídění](../extensibility/inside-the-editor.md#tagsandclassifiers)  
  
-   [Vylepšení](../extensibility/inside-the-editor.md#adornments)  
  
-   [Projekce](../extensibility/inside-the-editor.md#projection)  
  
-   [Osnova](../extensibility/inside-the-editor.md#outlining)  
  
-   [Vazby myši](../extensibility/inside-the-editor.md#mousebindings)  
  
-   [Operace editoru](../extensibility/inside-the-editor.md#editoroperations)  
  
-   [IntelliSense](../extensibility/inside-the-editor.md#intellisense)  
  
##  <a name="overview"></a>Přehled subsystémů  
  
### <a name="text-model-subsystem"></a>Text modelu subsystému  
 Subsystém modelu textu je zodpovědná za představující text a povolení jeho zpracování. Subsystém modelu text obsahuje <xref:Microsoft.VisualStudio.Text.ITextBuffer> rozhraní, které popisuje posloupnost znaků, který se má zobrazovat v editoru. Tento text můžete upravit, sledovat a jinak s nimi manipulovat, mnoha různými způsoby. Text model také obsahuje typy pro následující aspekty:  
  
-   Služba, která přidruží textové soubory a spravuje čtení a zápis je v systému souborů.  
  
-   Rozdílové služba, která vyhledá minimální rozdíly mezi dvěma pořadí objektů.  
  
-   Systém pro popisující textu ve vyrovnávací paměti z hlediska podmnožiny textu v jiných vyrovnávací paměti.  
  
 Subsystém modelu textu je zdarma konceptů uživatelské rozhraní (UI). Například není zodpovědná za rozložení textu nebo formátování textu a žádná znalost visual vylepšení, které může být spojeno s textem.  
  
 Veřejné typy subsystém text modelu jsou obsažené v Microsoft.VisualStudio.Text.Data.dll a Microsoft.VisualStudio.CoreUtilitiy.dll, které závisí pouze na knihovně základní třídy rozhraní .NET Framework a Managed Extensibility Framework (MEF).  
  
### <a name="text-view-subsystem"></a>Subsystém zobrazení textu  
 Subsystém zobrazení textu je zodpovědná za formátování a zobrazení textu. Typy v této subsystém se dál dělí na dvě vrstvy, v závislosti na tom, jestli typy spoléhají na Windows Presentation Foundation (WPF). Nejdůležitější typy <xref:Microsoft.VisualStudio.Text.Editor.ITextView> a <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextView>, které řídí sadu řádků textu, které se mají zobrazovat a také pomocí kurzoru, výběru a zařízení pro adorning text s použitím prvky uživatelského rozhraní grafického subsystému WPF. Tento subsystém obsahuje také okraje kolem text umožňuje zobrazit oblast. Tyto okraje lze rozšířit a může obsahovat různé druhy obsahu a vizuální efekty. Příkladem okraje jsou číslo řádky zobrazí a přejděte na řádek.  
  
 Veřejné typy subsystém zobrazení textu jsou obsažené v Microsoft.VisualStudio.Text.UI.dll a Microsoft.VisualStudio.Text.UI.Wpf.dll. První sestavení obsahuje prvky nezávislé na platformě a druhá obsahuje prvky specifické pro WPF.  
  
### <a name="classification-subsystem"></a>Klasifikace subsystému  
 Subsystém klasifikace je zodpovědná za určení vlastnosti písmo pro text. Třídění rozdělí text na různých tříd, například "– klíčové slovo" nebo "komentář". Mapa formátu klasifikace platí tyto třídy pro skutečné písma vlastnosti, například "Blue Consolas 10 b". Tyto informace se používá v zobrazení textu při naformátuje a vykreslí text. Označování, který je podrobněji popsané v dále v tomto tématu umožňuje data mají být spojeny s rozsahy textu.  
  
 Veřejné typy subsystém klasifikace jsou obsaženy v Microsoft.VisualStudio.Text.Logic.dll a komunikují s visual aspektů klasifikace, které jsou součástí Microsoft.VisualStudio.Text.UI.Wpf.dll.  
  
### <a name="operations-subsystem"></a>Operace subsystému  
 Subsystém operations definuje chování editoru. Poskytuje implementaci pro příkazů editoru v sadě Visual Studio a systém vrácení zpět.  
  
## <a name="a-closer-look-at-the-text-model-and-the-text-view"></a>Bližší pohled na modelu Text a textového zobrazení  
  
###  <a name="textmodel"></a>Model textu  
 Subsystém modelu text se skládá z různých seskupení typ textu. Mezi ně patří textovou vyrovnávací paměť, text snímky a text rozpětí.  
  
#### <a name="text-buffers-and-text-snapshots"></a>Textové vyrovnávací paměti a snímky textu  
 <xref:Microsoft.VisualStudio.Text.ITextBuffer> Rozhraní představuje posloupnost znaků Unicode, které jsou zakódovány pomocí znakové sady UTF-16, což je kódování používané `String` typu v rozhraní .NET Framework. Textová vyrovnávací paměť můžete nastavit jako trvalý, jako dokument systému souborů, ale není to povinné.  
  
 <xref:Microsoft.VisualStudio.Text.ITextBufferFactoryService> Se používá k vytvoření vyrovnávací paměť prázdný textový nebo textovou vyrovnávací paměť, který je inicializován ze řetězec nebo z <xref:System.IO.TextReader>. Textová vyrovnávací paměť můžete nastavit jako trvalý, systém souborů jako <xref:Microsoft.VisualStudio.Text.ITextDocument>.  
  
 Textová vyrovnávací paměť lze upravovat všechny vlákno, dokud nedojde k vlákno vlastnictví textová vyrovnávací paměť voláním <xref:Microsoft.VisualStudio.Text.ITextBuffer.TakeThreadOwnership%2A>. Potom můžete provést pouze v daném vláknu úpravy.  
  
 Textová vyrovnávací paměť můžete projít mnoha verzí během celé jeho životnosti. Nová verze je generována pokaždé, když je upravit vyrovnávací paměť a neměnné <xref:Microsoft.VisualStudio.Text.ITextSnapshot> reprezentuje obsah dané verze vyrovnávací paměti. Protože text snímky jsou neměnné, dostanete snímku text z libovolného vlákna, bez omezení, i v případě, že vyrovnávací paměť textu, který představuje nadále změnit.  
  
#### <a name="text-snapshots-and-text-snapshot-lines"></a>Text snímky a snímku řádky textu  
 Obsah textu snímku můžete zobrazit jako posloupnosti znaků nebo jako pořadí řádků. Znaky a řádky jsou že obě indexované začínající na nulu. Na snímku prázdný text obsahuje nulový počet znaků a jeden prázdný řádek. Řádek je oddělený žádné platné posloupnost znaků Unicode koncem řádku, nebo začátku nebo konci vyrovnávací paměti. Znaky konce řádku, které jsou explicitně reprezentované ve snímku text a všechny konce řádků ve snímku text mají být stejné.  
  
> [!NOTE]
>  Další informace o ukončování znaků v editoru Visual Studio najdete v tématu [kódování a zalomení](../ide/encodings-and-line-breaks.md).  
  
 Řádek textu je reprezentována <xref:Microsoft.VisualStudio.Text.ITextSnapshotLine> objektu, který můžete získat z textu snímku pro konkrétní řádek číslo nebo znak konkrétní pozici.  
  
#### <a name="snapshotpoints-snapshotspans-and-normalizedsnapshotspancollections"></a>SnapshotPoints, SnapshotSpans a NormalizedSnapshotSpanCollections  
 A <xref:Microsoft.VisualStudio.Text.SnapshotPoint> představuje pozice znaku v snímku. Pozice záruku, že ležet mezi nulou a délka snímku. A <xref:Microsoft.VisualStudio.Text.SnapshotSpan> reprezentuje rozpětí textu ve snímku. Jeho koncová pozice záruku, že ležet mezi nulou a délka snímku. <xref:Microsoft.VisualStudio.Text.NormalizedSnapshotSpanCollection> Se skládá ze sady <xref:Microsoft.VisualStudio.Text.SnapshotSpan> objekty ze stejné snímku.  
  
#### <a name="spans-and-normalizedspancollections"></a>Rozsahy a NormalizedSpanCollections  
 A <xref:Microsoft.VisualStudio.Text.Span> představuje časový interval, který lze použít pro rozpětí textu ve snímku text. Pozice snímku jsou od nuly, tak rozsahy můžete spustit na jakékoli pozici včetně nula. `End` Vlastnost rozpětí je určena součtem z jeho `Start` vlastnost a její `Length` vlastnost. A `Span` neobsahuje znak, který je indexovaný tím `End` vlastnost. Například značka span, který má počáteční = 5 a délka = 3 má End = 8, a obsahuje znaky v místech, 5, 6 a 7. Pro toto rozpětí se 5..8).  
  
 Dva rozsahy intersect v případě, že mají všechny pozice společné, včetně koncová pozice. Proto průnik [3, 5) a [2, 7) je [3, 5) a průnik [3, 5) a [5, 7) je [5, 5). (Všimněte si, že [5, 5) je prázdný rozpětí.)  
  
 Dva rozsahy překrývají, pokud nemají pozic společného, s výjimkou koncová pozice. Prázdný rozpětí nikdy překrývá další rozpětí a překrytí dva rozsahy se nikdy prázdný.  
  
 A <xref:Microsoft.VisualStudio.Text.NormalizedSpanCollection> je seznam rozsahy v pořadí podle vlastnosti určená pro spuštění. V seznamu jsou sloučeny překrývající se nebo sousedících rozpětí. Například danou sadu rozsahy [5..9), [0..1), [3..6), a [9..10), normalizovaný seznam rozsahy je [0..1), [3..10).  
  
#### <a name="itextedit-textversion-and-text-change-notifications"></a>ITextEdit, TextVersion a oznámení o změně textu  
 Obsah textové vyrovnávací paměti můžete změnit pomocí <xref:Microsoft.VisualStudio.Text.ITextEdit> objektu. Vytvoření takového objektu (pomocí jedné z `CreateEdit()` metody <xref:Microsoft.VisualStudio.Text.ITextBuffer>) spustí text transakci, která se skládá z textových úprav. Každý upravit nahrazuje některé rozpětí textu ve vyrovnávací paměti řetězce. Souřadnice a obsah každé úpravy jsou vyjádřeno vzhledem ke snímku vyrovnávací paměti, když transakce byla spuštěna. <xref:Microsoft.VisualStudio.Text.ITextEdit> Objekt upraví souřadnice úpravy, které jsou ovlivněné další úpravy ve stejné transakci.  
  
 Představte si třeba textovou vyrovnávací paměť, která obsahuje tento řetězec:  
  
```  
abcdefghij  
```  
  
 Použít transakci, která obsahuje dvě úpravy, jeden úpravy, který nahrazuje rozpětí v [2..4) pomocí znaku `X` a druhý úpravy, který nahrazuje rozpětí v [6..9) pomocí znaku `Y`. Výsledkem je této vyrovnávací paměti:  
  
```  
abXefYj  
```  
  
 Souřadnice pro druhý úpravy byly počítá s ohledem na obsah vyrovnávací paměti na začátku transakce, jako před použitím první upravit.  
  
 Změny do vyrovnávací paměti se projeví při <xref:Microsoft.VisualStudio.Text.ITextEdit> objektu je potvrzen voláním jeho `Apply()` metoda. Pokud se alespoň jeden neprázdný úpravy, nový <xref:Microsoft.VisualStudio.Text.ITextVersion> se vytvoří nový <xref:Microsoft.VisualStudio.Text.ITextSnapshot> je vytvořen a jeden `Changed` událost se vyvolá. Každá verze text má jiné text snímku. Snímek text představuje stav dokončení textová vyrovnávací paměť po transakci upravit, ale verze text popisuje pouze změny z jednoho snímku na další. Text snímky jsou obecně určen pro použití jednou a pak zrušené, zatímco text verze musí zůstat aktivní nějakou dobu.  
  
 Verze text obsahuje <xref:Microsoft.VisualStudio.Text.INormalizedTextChangeCollection>. Tato kolekce popisuje změny, při použití snímku, vygeneruje následné snímku. Každý <xref:Microsoft.VisualStudio.Text.ITextChange> v kolekci obsahuje znak na pozici změnu, Nahrazený řetězec a náhradní řetězec. Nahrazené řetězec prázdný pro základní vložení, a náhradní řetězec je pro základní odstranění prázdné. Normalizovaný kolekce je vždy `null` pro nejnovější verzi textová vyrovnávací paměť.  
  
 Pouze jeden <xref:Microsoft.VisualStudio.Text.ITextEdit> objektu může být vytvořena instance pro textovou vyrovnávací paměť kdykoli a všechny úpravy textu je potřeba provést na vlákno, které vlastní textová vyrovnávací paměť (pokud vlastnictví byl vyžádaný). Upravit text může být opuštěny v rámci volání jeho `Cancel` metoda nebo jeho `Dispose` metoda.  
  
 <xref:Microsoft.VisualStudio.Text.ITextBuffer>také poskytuje `Insert()`, `Delete()`, a `Replace()` metody, které je podobných najít na <xref:Microsoft.VisualStudio.Text.ITextEdit> rozhraní. Volání metody tyto stejného efektu jako vytváření má <xref:Microsoft.VisualStudio.Text.ITextEdit> objekt, vytvořit podobné volání a potom se použijí úpravy.  
  
#### <a name="tracking-points-and-tracking-spans"></a>Sledování body a sledování rozpětí  
 <xref:Microsoft.VisualStudio.Text.ITrackingPoint> Představuje pozice znaku v textové vyrovnávací paměti. Pokud vyrovnávací paměť je upravit tak, aby způsobí, že pozice znaku se posunou, bodem sledování posune s ním. Například pokud bod sledování určuje pozici 10 ve vyrovnávací paměti a vloženo pět znaků od začátku vyrovnávací paměti, bodem sledování pak odkazuje na pozici 15. Pokud se vložení stane na přesněji pozici odlišené bodem sledování, je dáno jeho chování jeho <xref:Microsoft.VisualStudio.Text.PointTrackingMode>, což může být buď `Positive` nebo `Negative`. Pokud je režim sledování kladné, že bodem sledování odkazuje na stejný znak, který je teď na konci vložení; Pokud je režim sledování záporná, bodem sledování odkazuje na první znak vložené na původní pozici. Je-li znak na pozici, která je reprezentována bod sledování odstraněna, bodem sledování posune na první znak, který následuje odstraněného rozsahu. Například pokud bod sledování odkazuje na znak na pozici 5 a znaky v místech 3 až 6 jsou odstraněny, bodem sledování odkazuje na znak na pozici 3.  
  
 <xref:Microsoft.VisualStudio.Text.ITrackingSpan> Představuje rozsah znaků místo pouze jednu pozici. Její chování je dáno jeho <xref:Microsoft.VisualStudio.Text.SpanTrackingMode>. Pokud je režim rozpětí sledování <xref:Microsoft.VisualStudio.Text.SpanTrackingMode>, sledování rozpětí zvětšuje, aby začlenit text v jeho hran; Pokud je režim rozpětí sledování <xref:Microsoft.VisualStudio.Text.SpanTrackingMode>, sledování rozpětí nebere v úvahu text v jeho okraje. Ale pokud je režim rozpětí sledování <xref:Microsoft.VisualStudio.Text.SpanTrackingMode>, vložení sami aktuální pozice směrem k spuštění a v případě režimu rozpětí sledování <xref:Microsoft.VisualStudio.Text.SpanTrackingMode>, vložení nabízených oznámení na aktuální pozici na konci.  
  
 Získáte umístění bodu sledování nebo rozpětí sledování rozpětí pro všechny snímek textovou vyrovnávací paměť, do které patří. Sledování body a sledování rozpětí může bezpečně na něj odkazovat z libovolného vlákna.  
  
#### <a name="content-types"></a>Typy obsahu  
 Typy obsahu jsou mechanismus pro definování různých druhů obsahu. Typ obsahu může být typ souboru, například "text", "kód" nebo "binární" nebo typ technologie, jako je například "xml", "vb" nebo "c". Slova "pomocí" je například klíčové slovo v jak C# a Visual Basic, ale není v jinými programovací jazyky. Definice klíčového slova, proto byla omezena na "c" a "vb" typy obsahu.  
  
 Typy obsahu jsou použity jako filtr pro vylepšení a další prvky editoru. Mnoho funkcí editoru a rozšíření body jsou definovány na typ obsahu; barevné zvýrazňování textu se například liší pro soubory ve formátu prostého textu, soubory XML a soubory zdrojového kódu jazyka Visual Basic. Textové vyrovnávací paměti jsou obecně přiřazeni typ obsahu, když jsou vytvořené a lze změnit typ obsahu textovou vyrovnávací paměť.  
  
 Typy obsahu několika dědit z jiné typy obsahu. <xref:Microsoft.VisualStudio.Utilities.ContentTypeDefinition> Umožňuje určit více základních typů jako nadřazené položky daného typu obsahu.  
  
 Vývojářům můžete definovat vlastní typy obsahu a registrujte je pomocí <xref:Microsoft.VisualStudio.Utilities.IContentTypeRegistryService>. Mnoho funkcí editoru lze definovat s ohledem na konkrétní typ obsahu pomocí <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>. Například okraje editoru, vylepšení a obslužné rutiny myši můžete definovat tak, že se vztahují pouze na editory, které zobrazí konkrétní typy obsahu.  
  
###  <a name="textview"></a>Zobrazení textu  
 Část zobrazení vzoru model view controller (MVC) definuje textového zobrazení, formátování zobrazení, grafické prvky, jako jsou například posuvník a bez vynechávání. Všechny prvky prezentace, které editoru Visual Studio jsou založené na WPF.  
  
#### <a name="text-views"></a>Zobrazení textu  
 <xref:Microsoft.VisualStudio.Text.Editor.ITextView> Rozhraní je nezávislé na platformě reprezentace textového zobrazení. Se používá hlavně kvůli zobrazení dokumentů v okně, ale může taky sloužit k jiným účelům, například ve formě popisu tlačítka.  
  
 Textového zobrazení odkazuje na různé druhy textové vyrovnávací paměti. <xref:Microsoft.VisualStudio.Text.Editor.ITextView.TextViewModel%2A> Vlastnost odkazuje <xref:Microsoft.VisualStudio.Text.Editor.ITextViewModel> objekt, který odkazuje na tyto tři různé textové vyrovnávací paměti: vyrovnávací paměť dat, což je nejvyšší vyrovnávací paměť dat na úrovni, vyrovnávací paměť pro úpravu, ve které úpravy dojde a pak visual vyrovnávací paměti, což je vyrovnávací paměť, která je zobrazí v zobrazení textu.  
  
 Text je formátován podle třídění, které jsou připojené k základní textová vyrovnávací paměť a je ozdobené s použitím zprostředkovatelů dalších úprav, které jsou připojené k samotném zobrazení textu.  
  
#### <a name="the-text-view-coordinate-system"></a>Souřadnicový systém zobrazení textu  
 Určuje souřadnicový systém zobrazení textu pozice v zobrazení textu. V tomto systému souřadnici x hodnota 0,0 odpovídá na levém okraji textu se zobrazuje a hodnoty y 0,0 odpovídá na horní okraj textu se zobrazuje. Souřadnice x zvyšuje zleva doprava a souřadnici y shora dolů.  
  
 Zobrazení (část textu viditelné v okně text) nelze stejným způsobem vodorovně posunout jako je přesunut svisle oblasti. Zobrazení je vodorovně posunout změnou jeho levou souřadnici tak, aby se přesune s ohledem na kreslicí plochy. Však zobrazení posunout svisle jenom změnou vykresleného textu, což způsobí, že <xref:Microsoft.VisualStudio.Text.Editor.ITextView.LayoutChanged> událost, která má být vyvolána.  
  
 Vzdálenosti v souřadnicový systém odpovídají logické pixelů. Pokud na povrch vykreslování text se zobrazí bez škálování transformace, jednu jednotku v souřadnicový systém vykreslování textu odpovídá jednoho pixelu na zobrazení.  
  
#### <a name="margins"></a>Okraje  
 <xref:Microsoft.VisualStudio.Text.Editor.ITextViewMargin> Rozhraní představuje okraj a umožňuje řízení viditelnost okraj a jeho velikost. Existují čtyři předdefinované okraje, které jsou s názvem "Top", "Vlevo", "Vpravo" a "Dolů" a jsou připojené k nahoru, dolů, doleva nebo pravý okraj zobrazení. Tyto okraje jsou kontejnery, ve kterých se může jinými okraji. Rozhraní definuje metody, které vrátí velikost okraje a viditelnost okraj. Okraje jsou vizuální prvky, které poskytují další informace o textového zobrazení, ke kterému jsou připojené. Například číslo řádku okraj zobrazí čísla řádků pro zobrazení textu. Okraj glyfy zobrazí prvky uživatelského rozhraní.  
  
 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewMarginProvider> Rozhraní zpracovává vytváření a umístění levého okraje. Okraje lze provést řazení s ohledem na jinými okraji. S vyšší prioritou okraje nacházejí blíže k zobrazení textu. Například pokud jsou dva okraje, okraj A a B okraj a okraj B má nižší prioritu než okraj A, okraj B, které se zobrazí vlevo od okraje A.  
  
#### <a name="the-text-view-host"></a>Hostitel zobrazení textu  
 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewHost> Rozhraní obsahuje zobrazení textu a všech sousedících dekorace doprovázejících zobrazení, například posuvníky. Hostitel zobrazení textu také obsahuje okraje, které jsou spojené s ohraničením zobrazení.  
  
#### <a name="formatted-text"></a>Formátovaný Text  
 Text, který se zobrazí v zobrazení textu se skládá z <xref:Microsoft.VisualStudio.Text.Formatting.ITextViewLine> objekty. Každý řádek textového zobrazení odpovídá jeden řádek text v zobrazení textu. Dlouhé řádky v základní textová vyrovnávací paměť může být buď částečně vyznačených (Pokud není povoleno zalamování řádků) nebo rozdělen do více řádků textu zobrazení. <xref:Microsoft.VisualStudio.Text.Formatting.ITextViewLine> Rozhraní obsahuje metody a vlastnosti pro mapování mezi souřadnice a znaky a vylepšení, které může být přidružený k řádku.  
  
 <xref:Microsoft.VisualStudio.Text.Formatting.ITextViewLine>objekty jsou vytvořeny pomocí <xref:Microsoft.VisualStudio.Text.Formatting.IFormattedLineSource> rozhraní. Pokud jste právě zajímá text, který je aktuálně zobrazený v zobrazení, můžete ignorovat zdroji formátování. Pokud vás zajímá ve formátu textu, který není v zobrazení (například pro podporu vyjmutí formátovaného textu a vložte), můžete použít <xref:Microsoft.VisualStudio.Text.Formatting.IFormattedLineSource> formátování textu v textové vyrovnávací paměti.  
  
 Zobrazení textu formáty jeden <xref:Microsoft.VisualStudio.Text.ITextSnapshotLine> najednou.  
  
## <a name="editor-features"></a>Funkce editoru  
 Funkce editoru jsou navrženy tak, aby je oddělená od jeho implementace definici funkce. Editor zahrnuje tyto funkce:  
  
-   Značky a třídění  
  
-   Vylepšení  
  
-   Projekce  
  
-   Sbalování  
  
-   Myši a klíč vazby  
  
-   Operace a primitivní elementy.  
  
-   IntelliSense  
  
###  <a name="tagsandclassifiers"></a>Značky a třídění  
 Značky jsou značky, které jsou přidruženy rozpětí textu. Umožňují prezentaci různými způsoby, například pomocí barevné zvýrazňování textu, podtržení, grafiky nebo automaticky otevíraná okna. Třídění se jeden typ značky.  
  
 Jiné druhy značky jsou <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag> pro zvýraznění textu <xref:Microsoft.VisualStudio.Text.Tagging.OutliningRegionTag> pro práci s přehledy, a <xref:Microsoft.VisualStudio.Text.Tagging.ErrorTag> chyby kompilace.  
  
#### <a name="classification-types"></a>Typy klasifikace  
 <xref:Microsoft.VisualStudio.Text.Classification.IClassificationType> Rozhraní představuje ekvivalenční třída, která je abstraktní kategorie textu. Typy klasifikace lze několik dědit od ostatních typů klasifikace. Programovací jazyk klasifikace může obsahovat třeba "– klíčové slovo", "komentář" a "identifikátor", které dědí "kódu". Přirozeného jazyka klasifikace typy mohou zahrnovat "podstatné jméno", "akce" a "přídavných jmen", které dědí "přirozený jazyk".  
  
#### <a name="classifications"></a>Klasifikace  
 Klasifikaci instance typu určité klasifikace, je obvykle nad rozpětí textu. A <xref:Microsoft.VisualStudio.Text.Classification.ClassificationSpan> se používá k reprezentování klasifikaci. Klasifikace rozpětí můžete představit jako popisek, který popisuje konkrétní rozpětí textu a informuje systém, který tomuto rozpětí textu je typu určité klasifikace.  
  
#### <a name="classifiers"></a>Třídění  
 <xref:Microsoft.VisualStudio.Text.Classification.IClassifier> Mechanismus, která rozdělí text na sadu klasifikace. Třídění musí být definované pro určité typy obsahu a musí být vytvořena instance pro zadaný text vyrovnávací paměti. Klienti musí implementovat <xref:Microsoft.VisualStudio.Text.Classification.IClassifier> zapojit se do textu klasifikace.  
  
#### <a name="classifier-aggregators"></a>Agregátorů třídění  
 Agregátor třídění je mechanismus, který kombinuje všechny třídění pro jednu textovou vyrovnávací paměť do právě jednu sadu klasifikace. Například třídění C# a třídění anglických může vytvořit klasifikace na komentář v souboru C#. Vezměte v úvahu tohoto komentáře:  
  
```  
// This method produces a classifier  
```  
  
 Klasifikátor C# může označovat celý rozsah jako komentář a třídění anglických může klasifikovat "vytvoří" jako "akce" a "způsob" jako "podstatné jméno". Agregátor vytvoří sadu klasifikace nepřekrývají, a typ sady je založen na všechny příspěvky.  
  
 Agregátor třídění je také třídění, protože to naruší text do sady klasifikace. Agregátor třídění také zajistí, že neexistují žádné překrývající se klasifikace a že jsou seřazeny klasifikace. Jednotlivé třídění jsou volně vrátí libovolnou sadu klasifikace, v libovolném pořadí a překrývající se žádným způsobem.  
  
#### <a name="classification-formatting-and-text-coloring"></a>Klasifikace formátování a barevné zvýrazňování textu  
 Formátování textu je příkladem funkce, která je založená na text klasifikace. Ve vrstvě zobrazení textu slouží k určení zobrazení textu v aplikaci. Oblasti formátování textu je závislá na WPF, ale není definici logické klasifikace.  
  
 Formát klasifikace je sada vlastností pro určité klasifikace typ formátování. Tyto formáty dědí formát nadřazený typ klasifikace.  
  
 <xref:Microsoft.VisualStudio.Text.Classification.IClassificationFormatMap> Je mapování z typu klasifikace na sadu vlastností pro formátování textu. Implementace Mapa formátu v editoru zpracovává všechny exporty klasifikace formátů.  
  
###  <a name="adornments"></a>Vylepšení  
 Vylepšení jsou grafické účinky, které přímo nesouvisejí s písma a barev znaků v zobrazení textu. Například je, že podtržení červenou vlnovkou, který slouží k označení-kompilování kódu v řadě programovacích jazyků embedded dalších úprav a popisy tlačítek se automaticky otevírané okno vylepšení. Vylepšení, které jsou odvozeny od <xref:System.Windows.UIElement> a implementovat <xref:Microsoft.VisualStudio.Text.Tagging.ITag>. Jsou dva speciální typy dalších úprav značky <xref:Microsoft.VisualStudio.Text.Tagging.SpaceNegotiatingAdornmentTag>, pro vylepšení, které na stejném místě jako text v zobrazení, a <xref:Microsoft.VisualStudio.Text.Tagging.ErrorTag>, pro vlnovku podtržení.  
  
 Vložené vylepšení jsou obrázky, které tvoří součást zobrazení formátovaný text. Že jsou uspořádány do různých vrstev pořadí Z-order. Existují tři předdefinované vrstvy, následujícím způsobem: text, pomocí kurzoru a výběr. Vývojáři však můžete definovat další vrstvy a seřadit je podle s ohledem na sebe navzájem. Tři druhy embedded vylepšení jsou vylepšení relativního text, (které přesunout, pokud se přesune text a jsou odstraněna při odstranění text), vylepšení relativního zobrazení, (která mají udělat s částmi jiné textové zobrazení) a řídí vlastník vylepšení (na Vývojář musí spravovat jejich umístění).  
  
 Automaticky otevírané okno vylepšení jsou obrázky, které se zobrazují v malém okně výše textového zobrazení, například popisy tlačítek.  
  
###  <a name="projection"></a>Projekce  
 Projekce je technika pro vytváření jiný druh textovou vyrovnávací paměť, která není ve skutečnosti ukládání textu, ale místo toho kombinuje text z jiných textové vyrovnávací paměti. Například vyrovnávací paměť projekce lze řetězení text ze dvou dalších vyrovnávací paměti a zobrazí výsledky, pokud je v pouze jednu vyrovnávací paměti, nebo skrýt části textu v jedné vyrovnávací paměti. Vyrovnávací paměť projekce může fungovat jako zdrojová vyrovnávací paměť do vyrovnávací paměti jiné projekce. Sadu vyrovnávací paměti, které jsou spojené projekce konstruovat ke změně uspořádání text v mnoha různými způsoby. (Takové sady je také označován jako *vyrovnávací paměti grafu*.) Funkce osnovy text sady Visual Studio je implementována pomocí vyrovnávací paměť projekce skrytí sbaleného textu a editoru Visual Studio pro stránky ASP.NET používá projekce pro podporu embedded jazyků, například Visual Basic a C#.  
  
 <xref:Microsoft.VisualStudio.Text.Projection.IProjectionBuffer> Je vytvořená pomocí <xref:Microsoft.VisualStudio.Text.Projection.IProjectionBufferFactoryService>. Projekce vyrovnávací paměť je reprezentována seřazená posloupnost <xref:Microsoft.VisualStudio.Text.ITrackingSpan> objekty, které se označují jako *zdroje rozsahy*. Obsah tyto rozsahy jsou uvedené jako posloupnost znaků. Vyrovnávací paměti text, ze kterých se mají vykreslovat zdroj rozsahy jsou pojmenované *zdroje vyrovnávací paměti*. Klienti vyrovnávací paměti projekce nemají potřeba mít na paměti, že se liší od vyrovnávací paměť běžného textu.  
  
 Vyrovnávací paměť projekce naslouchá událostem, změna textu na zdrojové vyrovnávací paměti. Když text ve zdroji span změny, vyrovnávací paměť projekce souřadnice změněného textu se mapuje na svůj vlastní souřadnice a vyvolává události příslušné změny textu. Představte si třeba zdrojové vyrovnávací paměti A a B a které mají tyto obsah:  
  
```  
A: ABCDE  
B: vwxyz  
```  
  
 Pokud vyrovnávací paměť projekce P je vytvořen ze dvou rozpětí textu, ten, který má všechny vyrovnávací paměti A a další, který obsahuje všechny vyrovnávací paměti B, P má následující obsah:  
  
```  
P: ABCDEvwxyz  
```  
  
 Pokud dílčí řetězec `xy` se odstraní z vyrovnávací paměti B, pak vyrovnávací paměti P vyvolá událost, která určuje, že byly odstraněny na pozice 7 a 8 znaky.  
  
 Vyrovnávací paměť projekce můžete upravovat také přímo. Se rozšíří úprav příslušné zdrojové vyrovnávací paměti. Například pokud řetězec je vložen do vyrovnávací paměti P na pozici 6 (původní pozici znaku "v"), vkládání rozšířena do vyrovnávací paměti B na pozici 1.  
  
 Platí omezení na rozsahy zdroje, které přispívat do vyrovnávací paměti projekce. Zdroj rozpětí nesmí překrývat; umístění, do vyrovnávací paměti projekce nelze mapovat do více než jedno umístění v jakékoli zdrojová vyrovnávací paměť a místo v zdrojová vyrovnávací paměť nelze mapovat do více než jednoho umístění do vyrovnávací paměti projekce. Žádné circularities jsou povolena ve zdrojové vyrovnávací paměti relace.  
  
 Události se vyvolá, když sada zdroje uloží změny projekce vyrovnávací paměti a sadu zdroj zahrnuje změny.  
  
 Vyrovnávací paměť elision je zvláštní druh projekce vyrovnávací paměti. Používá se především pro osnova a pro operace, které rozbalení a sbalení bloky textu. Vyrovnávací paměť elision je založena na jenom jednom zdrojová vyrovnávací paměť a rozsahy ve vyrovnávací paměti elision musejí být seřazeny stejné jako jsou seřazené v zdrojová vyrovnávací paměť.  
  
##### <a name="the-buffer-graph"></a>Graf vyrovnávací paměti  
 <xref:Microsoft.VisualStudio.Text.Projection.IBufferGraph> Rozhraní umožňuje mapování mezi graf vyrovnávacích pamětí projekce. Všechny textové vyrovnávací paměti a projekce vyrovnávací paměti se shromažďují v necyklicky, podobně jako abstraktního syntaktického stromu, které je produkovaný kompilátoru jazyka. Graf je definována nejvyšší vyrovnávací paměti, což může být jakékoli textovou vyrovnávací paměť. Graf vyrovnávací paměti můžete namapovat z bodu v horní vyrovnávací paměť na bod v zdrojová vyrovnávací paměť, nebo z rozpětí v horní vyrovnávací paměť na sadu rozpětí v zdrojová vyrovnávací paměť. Podobně se mapování bod nebo span z zdrojová vyrovnávací paměť na bod v horní vyrovnávací paměti. Grafy vyrovnávací paměti se vytváří pomocí <xref:Microsoft.VisualStudio.Text.Projection.IBufferGraphFactoryService>.  
  
##### <a name="events-and-projection-buffers"></a>Události a projekce vyrovnávací paměti  
 Pokud projekce vyrovnávací paměť je změněn, změny jsou odesílány z vyrovnávací paměti projekce vyrovnávací paměti, které na ní závisí. Po změně všechny vyrovnávací paměti, jsou vyvolány události změny vyrovnávací paměti, počínaje nejhlubší vyrovnávací paměti.  
  
###  <a name="outlining"></a>Osnova  
 Osnova je schopnost rozbalit nebo sbalit různé bloky textu v textovém zobrazení. Osnova je definována jako typ z <xref:Microsoft.VisualStudio.Text.Tagging.ITag>, v stejným způsobem, jak jsou definovány vylepšení. A <xref:Microsoft.VisualStudio.Text.Tagging.OutliningRegionTag> je značku, která definuje oblast text, který můžete rozbalit nebo sbalit. Chcete-li použít osnovy, je nutné importovat <xref:Microsoft.VisualStudio.Text.Outlining.IOutliningManagerService> získat <xref:Microsoft.VisualStudio.Text.Outlining.IOutliningManager>. Osnovy správce vytvoří výčet, sbalí a rozšiřuje jinou bloků, které jsou reprezentovány jako <xref:Microsoft.VisualStudio.Text.Outlining.ICollapsible> objekty a odpovídajícím způsobem vyvolává události.  
  
###  <a name="mousebindings"></a>Vazby myši  
 Vazby myši propojit jiné příkazy pohyb myši. Vazby myš jsou definované za použití <xref:Microsoft.VisualStudio.Text.Editor.IMouseProcessorProvider>, a vazeb klíče jsou definované za použití <xref:Microsoft.VisualStudio.Text.Editor.IKeyProcessorProvider>. <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewHost> Automaticky vytvoří všechny vazby a připojí je k události myši v zobrazení.  
  
 <xref:Microsoft.VisualStudio.Text.Editor.IMouseProcessor> Rozhraní obsahuje předem proces a po zpracování obslužné rutiny události různých myši. K popisovači některá z událostí, můžete přepsat některé metody v <xref:Microsoft.VisualStudio.Text.Editor.MouseProcessorBase>.  
  
###  <a name="editoroperations"></a>Operace editoru  
 Editor operace můžete použít k automatizaci interakci s editoru pro skriptování nebo jiné účely. Můžete importovat <xref:Microsoft.VisualStudio.Text.Operations.IEditorOperationsFactoryService> pro operace přístupu na danou <xref:Microsoft.VisualStudio.Text.Editor.ITextView>. Pak můžete tyto objekty změnit výběr, posuňte zobrazení nebo přesunout znak do různých částí zobrazení.  
  
###  <a name="intellisense"></a>IntelliSense  
 IntelliSense podporuje dokončování příkazů, podpis nápovědy (také označované jako informace o parametrech), rychlé informace a žárovek.  
  
 Dokončování poskytuje rozbalovací seznam potenciální dokončených pro názvy metod, elementů XML a další elementy kódování nebo značek. Obecně platí vyvolá gesto uživatele relaci dokončení. Relace zobrazí seznam potenciální dokončených, a uživatel může vybrat jednu nebo zavření v seznamu. <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionBroker> Je odpovědná za vytváření a spouštění <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSession>. <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSource> Vypočítá <xref:Microsoft.VisualStudio.Language.Intellisense.CompletionSet> dokončení položek pro relaci.  
  
## <a name="see-also"></a>Viz také  
 [Služba jazyka a body rozšíření editoru](../extensibility/language-service-and-editor-extension-points.md)   
 [Editor importy](../extensibility/editor-imports.md)