---
title: Obrázek knihovna prohlížeč | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 9d9c7fbb-ebae-4b20-9dd8-3c9070c0d0d1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ee0be99b307955017b896f70019dfc05481717c9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="image-library-viewer"></a>Image Viewer knihovny
Nástroj Visual Studio Image Viewer knihovny můžete načíst a hledání manifesty bitové kopie, které uživateli umožňují s nimi manipulovat stejným způsobem, který by Visual Studio. Uživatel může změnit pozadí, velikosti, DPI, vysoký kontrast a další nastavení. Nástroj také zobrazí informace o načtení pro každý manifest bitové kopie a informace o zdroji každé bitové kopie v manifestu bitové kopie. Tento nástroj je užitečný pro:  
  
1.  Diagnostikování chyb  
  
2.  Zajistit atributy jsou správně nastavené v manifestech vlastní image  
  
3.  Hledání bitové kopie v katalogu bitové kopie Visual Studio, aby obrázky, které vyhovovat styl sady Visual Studio můžete použít rozšíření sady Visual Studio  
  
 ![Bitové kopie knihovny prohlížeč nejdůležitější](../../extensibility/internals/media/image-library-viewer-hero.png "obrázku nejdůležitější prohlížeč knihovny")  
  
 **Přezdívka bitové kopie**  
  
 Obrázek Přezdívka (nebo Přezdívka pro zkrácení) je pár GUID:ID, který jednoznačně identifikuje prostředek bitové kopie nebo bitové kopie seznamu prostředek v knihovně.  
  
 **Soubory manifestu obrázků**  
  
 Soubory manifestu (.imagemanifest) bitové kopie jsou soubory XML, které definují sadu prostředků bitové kopie, zástupných názvů, které představují tyto prostředky a skutečné bitové kopie nebo bitové kopie, které představují každý prostředek. Manifesty bitové kopie můžete definovat samostatné bitové kopie nebo bitové kopie jsou uvedené pro starší verze podpora uživatelského rozhraní. Kromě toho jsou atributy, které lze nastavit na prostředku nebo na jednotlivé bitové kopie za každý prostředek změnit, kdy a jak se zobrazují tyto prostředky.  
  
 **Schéma manifestu bitové kopie**  
  
 Manifest dokončení obrázek vypadá takto:  
  
```xml  
<ImageManifest>  
      <!-- zero or one Symbols elements -->  
      <Symbols>  
        <!-- zero or more Guid, ID, or String elements -->  
      </Symbols>  
      <!-- zero or one Images elements -->  
      <Images>  
        <!-- zero or more Image elements -->  
      </Images>  
      <!-- zero or one ImageLists elements -->  
      <ImageLists>  
        <!-- zero or more ImageList elements -->  
      </ImageLists>  
</ImageManifest>  
```  
  
 **Symboly**  
  
 Jak docílit přehlednosti a údržby, manifest bitové kopie můžete použít symboly pro hodnoty atributu. Symboly jsou definovány takto:  
  
```xml  
<Symbols>  
      <Import Manifest="manifest" />  
      <Guid Name="ShellCommandGuid" Value="8ee4f65d-bab4-4cde-b8e7-ac412abbda8a" />  
      <ID Name="cmdidSaveAll" Value="1000" />  
      <String Name="AssemblyName" Value="Microsoft.VisualStudio.Shell.UI.Internal" />  
</Symbols>  
```  
  
|||  
|-|-|  
|**Dílčí element**|**Definice**|  
|Importovat|Importuje symboly daném souboru manifestu pro použití v aktuální manifestu.|  
|Identifikátor GUID|Symbol představuje identifikátor GUID a formátování identifikátor GUID se musí shodovat.|  
|ID|Symbol představuje ID a musí být nezáporné celé číslo.|  
|String|Symbol představuje hodnotu libovolný řetězec.|  
  
 Symboly jsou velká a malá písmena a odkazované pomocí $(symbol-name) syntaxe:  
  
```xml  
<Image Guid="$(ShellCommandGuid)" ID="$(cmdidSaveAll)" >  
      <Source Uri="/$(AssemblyName);Component/Resources/image.xaml" />  
</Image>  
```  
  
 Některé symboly jsou předdefinovány pro všechny manifesty. Ty mohou být použity v identifikátoru Uri atributu \<zdroje > nebo \<Import > elementu, který chcete cesty odkazů v místním počítači.  
  
|||  
|-|-|  
|**Symbol**|**Popis**|  
|CommonProgramFiles|Hodnota proměnné prostředí % CommonProgramFiles %|  
|LocalAppData|Hodnota proměnné prostředí % LocalAppData %|  
|ManifestFolder|Ve složce obsahující soubor manifestu|  
|MyDocuments|Úplná cesta ke složce Dokumenty aktuálního uživatele|  
|ProgramFiles|Hodnota proměnné prostředí % ProgramFiles %|  
|Systém|Složky Windows\System32|  
|WinDir|Hodnota proměnné prostředí % WinDir %|  
  
 **Obrázek**  
  
 \<Image > element definuje obrázek, který může odkazovat přezdívka. Identifikátor GUID a ID, které dohromady tvoří Přezdívka bitové kopie. Přezdívka pro bitovou kopii musí být jedinečný v rámci celého obrázku knihovny. Pokud má více než jeden obrázek dané přezdívka, první z nich došlo při vytváření knihovny je ten, který je zachován.  
  
 Musí obsahovat alespoň jeden zdroj. I když velikost jazykově neutrální zdroje poskytne nejlepší výsledky napříč širokým spektrem velikostí, se nevyžadují. Pokud služby se zobrazí výzva pro bitovou kopii velikosti není definovaná v \<Image > elementu a neexistuje žádný zdroj velikost jazykově neutrální, služba zvolit nejlepší velikost konkrétní zdroj a škálování na požadovanou velikost.  
  
```xml  
<Image Guid="guid" ID="int" AllowColorInversion="true/false">  
      <Source ... />  
      <!-- optional additional Source elements -->  
</Image>  
```  
  
|||  
|-|-|  
|**Atribut**|**Definice**|  
|Identifikátor GUID|[Vyžaduje] Část GUID Přezdívka bitové kopie|  
|ID|[Vyžaduje] Část ID Přezdívka bitové kopie|  
|AllowColorInversion|[Volitelné, výchozí true] Určuje, jestli bitovou kopii můžete mít jeho barvy prostřednictvím kódu programu obrácený při použití na tmavý pozadí.|  
  
 **Zdroj**  
  
 \<Zdroje > element definuje jediný zdroj zdroj obrázku (XAML a PNG).  
  
```xml  
<Source Uri="uri" Background="background">  
      <!-- optional NativeResource element -->  
 </Source>  
```  
  
|||  
|-|-|  
|**Atribut**|**Definice**|  
|identifikátor URI|[Vyžaduje] Identifikátor URI, který definuje, kde lze načíst obrázek z. Může být jeden z následujících akcí:<br /><br /> -A [Pack URI](http://msdn.microsoft.com/en-US/library/aa970069\(v=vs.100\).aspx) pomocí aplikace: / / / autority<br /><br /> – Odkaz na absolutní součásti prostředků<br /><br /> – Cesta k souboru, který obsahuje nativní prostředků|  
|Pozadí|[Nepovinné] Určuje, co na druhu pozadí, které zdroj je určena k použití.<br /><br /> Může být jeden z následujících akcí:<br /><br /> - *Lehký*: zdroji lze použít na světle pozadí.<br /><br /> - *Tmavý*: zdroji lze použít v tmavý pozadí.<br /><br /> - *Funkce Vysoký kontrast*: zdroji lze použít na všechny pozadí v režimu vysokého kontrastu.<br /><br /> - *HighContrastLight*: zdroji lze použít na světle pozadí v režimu vysokého kontrastu.<br /><br /> -*HighContrastDark*: zdroji lze použít na tmavý pozadí v režimu vysokého kontrastu.<br /><br /> Pokud **pozadí** atribut vynechán, zdroji lze použít na všechny pozadí.<br /><br /> Pokud **pozadí** je *Light*, *tmavý*, *HighContrastLight*, nebo *HighContrastDark*, barvy zdroje jsou nikdy obrácený. Pokud **pozadí** je tento parametr vynechán, nebo nastavte *funkce Vysoký kontrast*, řídí inverzi barev zdroj obrázku **AllowColorInversion** atribut.|  
  
 A \<zdroje > element může obsahovat právě jeden z následujících volitelné dílčí prvky:  
  
||||  
|-|-|-|  
|**Element**|**Atributy (všechna požadovaná)**|**Definice**|  
|\<Velikost >|Hodnota|Zdroj se použije pro bitové kopie na danou velikost (v jednotkách zařízení). Image bude čtvereček.|  
|\<SizeRange >|MinSize, MaxSize|Zdroj se použije pro obrázky z MinSize k MaxSize (v jednotkách zařízení) (včetně). Image bude čtvereček.|  
|\<Dimenze >|Šířky, výšky|Zdroj se použije pro Image dané šířky a výšky (v jednotkách zařízení).|  
|\<DimensionRange >|Hodnota MinWidth, MinHeight,<br /><br /> MaxWidth MaxHeight|Zdroj se použije pro bitové kopie z minimální šířky a výšky maximální šířky a výšky (v jednotkách zařízení) (včetně).|  
  
 A \<zdroje > element může obsahovat také volitelný \<NativeResource > dílčí element, který definuje \<zdroje > načtené z nativní sestavení namísto spravované sestavení.  
  
```xml  
<NativeResource Type="type" ID="int" />  
```  
  
|||  
|-|-|  
|**Atribut**|**Definice**|  
|Typ|[Vyžaduje] Typ nativní prostředku, XAML nebo PNG|  
|ID|[Vyžaduje] Celočíselnou část ID nativní prostředků|  
  
 **ImageList**  
  
 \<ImageList > element definuje kolekci bitové kopie, které mohou být vráceny v jednom pruhů. Pruh je založen na vyžádání, podle potřeby.  
  
```xml  
<ImageList>  
      <ContainedImage Guid="guid" ID="int" External="true/false" />  
      <!-- optional additional ContainedImage elements -->  
 </ImageList>  
```  
  
|||  
|-|-|  
|**Atribut**|**Definice**|  
|Identifikátor GUID|[Vyžaduje] Část GUID Přezdívka bitové kopie|  
|ID|[Vyžaduje] Část ID Přezdívka bitové kopie|  
|Externí|[Volitelné, výchozí hodnota je false] Určuje, zda obrázek Přezdívka odkazuje na obrázek v aktuální manifestu.|  
  
 Chcete-li obrázek definované v aktuální manifestu nemá Přezdívka pro bitovou kopii obsažené. Pokud nelze nalézt bitovou kopii obsažené v knihovně bitovou kopii, bitovou kopii prázdné zástupný symbol se použije na příslušné místo.  
  
## <a name="how-to-use-the-tool"></a>Postup použití nástroje  
 **Ověření manifestu vlastní image**  
  
 Pokud chcete vytvořit vlastní manifest, doporučujeme, použijete nástroj ManifestFromResources k generovat manifest. Pro ověření vlastní manifest, spusťte Image Viewer knihovny a vyberte soubor > nastavit cesty... Tím otevřete dialogové okno prohledávaných adresářů. Tento nástroj používat adresáři pro hledání načíst manifesty bitové kopie, ale také použije ho mohly najít soubory .dll, které obsahují obrázků v manifestu, takže nezapomeňte zahrnout manifest i adresáře knihovny DLL v tomto dialogu.  
  
 ![Obrázek hledání prohlížeč knihovny](../../extensibility/internals/media/image-library-viewer-search.png "bitové kopie knihovny prohlížeč vyhledávání")  
  
 Klikněte na tlačítko **přidat...**  vyberte nové prohledávaných adresářů pro vyhledávání manifesty a jejich odpovídající knihovny DLL. Tento nástroj se mějte na paměti tyto adresáře vyhledávání a jejich může být zapnout nebo vypnout pomocí zaškrtnutí adresář.  
  
 Ve výchozím nastavení nástroj pokusí se najít instalační adresář Visual Studio a tyto adresáře přidat do seznamu hledání adresáře. Můžete ručně přidat adresáře, které nástroj nenajde.  
  
 Jakmile jsou načteny všechny manifesty, tento nástroj slouží k přepnutí **pozadí** barvy, **DPI**, **vysoký kontrast**, nebo **grayscaling** pro bitové kopie, aby uživatel můžete vizuálně prohlédnout prostředky bitovou kopii k ověření, že jsou správně vykreslení pro různá nastavení.  
  
 ![Obrázek pozadí prohlížeč knihovny](../../extensibility/internals/media/image-library-viewer-background.png "obrázku pozadí prohlížeč knihovny")  
  
 Barva pozadí lze nastavit pro lehké, světlý nebo vlastní hodnota. Výběrem "Vlastních barev" otevřete dialogové okno Výběr barvy a přidat vlastní barvy do spodní části pole se seznamem pozadí pro později snadno odvolání.  
  
 ![Bitové kopie knihovny prohlížeč vlastních barev](../../extensibility/internals/media/image-library-viewer-custom-color.png "bitové kopie knihovny prohlížeč vlastních barev")  
  
 Výběr Přezdívka image zobrazí informace o každé skutečné bitové kopie za tento Přezdívka v podokně podrobností bitové kopie na pravé straně. V podokně také umožňuje uživatelům kopírovat Přezdívka podle názvu nebo podle GUID:ID nezpracované hodnoty.  
  
 ![Obrázek bitové kopie podrobnosti ke knihovně prohlížeč](../../extensibility/internals/media/image-library-viewer-image-details.png "bitové kopie knihovny podrobnosti Image Viewer")  
  
 Informace zobrazené pro každý zdroj bitové kopie zahrnuje jaký druh pozadí k zobrazení, zda může být motivu nebo podporuje vysoký kontrast, jaké velikosti je platná pro nebo zda je velikost jazykově neutrální a určuje, zda obrázek pochází z nativní sestavení.  
  
 ![Image Viewer knihovny můžete motiv](../../extensibility/internals/media/image-library-viewer-can-theme.png "Image Viewer knihovny můžete motiv")  
  
 Při ověření manifestu bitové kopie, doporučujeme nasadit manifest a bitové kopie knihovny DLL v jejich skutečné umístění. Ověří se, že všechny relativní cesty fungují správně a že knihovna obrázků můžete najít a načíst manifest a bitové kopie knihovny DLL.  
  
 **Hledání image katalogu KnownMonikers**  
  
 Pro lepší shodu stylů v sadě Visual Studio, můžete použít rozšíření sady Visual Studio obrázků v katalogu bitové kopie Visual Studio místo vytváření a používání vlastní. To má výhodu není potřeba udržovat tyto bitové kopie a zaručuje, takže by měl vypadat správné v všechna nastavení DPI, které podporuje Visual Studio bude mít obrázek vysokou hodnotou DPI základní image.  
  
 Knihovna prohlížeč image umožňuje manifestu má proběhnout tak, aby uživatel můžete najít přezdívka, který představuje prostředek bitové kopie a použít tuto Přezdívka v kódu. Chcete-li vyhledat bitové kopie, do vyhledávacího pole zadejte požadovanou hledaný termín a stiskněte Enter. Stavový řádek v dolní části se zobrazí, kolik odpovídajících položek nebyly nalezeny mimo celkový počet bitových kopií ve všech manifesty.  
  
 ![Bitové kopie knihovny prohlížeč filtru](../../extensibility/internals/media/image-library-viewer-filter.png "bitové kopie knihovny prohlížeč filtru")  
  
 Při hledání monikery bitové kopie v existující manifesty, doporučujeme, abyste vyhledat a používat pouze monikery Visual Studio Image katalogu, jiné záměrně veřejně přístupná zástupných názvů nebo vlastní vlastních zástupných názvů. Pokud používáte neveřejní zástupných názvů, uživatelské rozhraní se můžou porušit nebo jeho Image způsoby změnily neočekávané Pokud nebo při změně nebo aktualizaci těchto neveřejní monikery a bitové kopie.  
  
 Vyhledávání podle identifikátoru GUID je navíc možné. Tento typ vyhledávání je užitečné pro filtrování dolů v seznamu jediný manifest nebo jednu část manifestu případě manifestu obsahuje více identifikátorů GUID.  
  
 ![Bitové kopie knihovny prohlížeč filtru GUID](../../extensibility/internals/media/image-library-viewer-filter-guid.png "bitové kopie knihovny prohlížeč filtru GUID")  
  
 Nakonec vyhledávání podle ID je možné také.  
  
 ![Bitové kopie knihovny prohlížeč filtr ID](../../extensibility/internals/media/image-library-viewer-filter-id.png "bitové kopie ID filtru prohlížeč knihovny")  
  
## <a name="notes"></a>Poznámky  
  
-   Ve výchozím nastavení nástroj načte v několika manifesty bitové kopie v sadě Visual Studio Instalační adresář existuje. Je pouze jedna, který má veřejně použití monikery **Microsoft.VisualStudio.ImageCatalog** manifest. Identifikátor GUID: ae27a6b0-e345-4288-96df-5eaf394ee369 (provést **není** přepsat identifikátoru GUID v vlastní manifestu) typu: KnownMonikers  
  
-   Nástroj pokusí při spuštění načíst všechny manifesty bitové kopie, které najde, tak může trvat několik sekund, aplikace se objeví ve skutečnosti. Při načítání manifesty může být také pomalými nebo nereagujícími.  
  
## <a name="sample-output"></a>Vzorový výstup  
 Tento nástroj negeneruje žádný výstup.