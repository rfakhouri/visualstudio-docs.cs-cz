---
title: "Editor obrázků | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.graphics.designer.imageeditor
- vs.graphics.imageeditor
ms.assetid: fc71d502-c548-4863-8afc-12a1d3ec90d4
caps.latest.revision: "45"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8d746d874b7efe18b1bd8dabf15804f1c05b57ca
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="image-editor"></a>Editor obrázků
Tento dokument popisuje, jak pracovat [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Editor obrázků pro zobrazení a úpravám prostředků texture a bitové kopie.  
  
 Můžete použít Editor obrázků pro práci s druhy bohaté texture a obrázkových formátů, které se používají v vývoj aplikací pro rozhraní DirectX – to zahrnuje podporu formátů souboru obrázku oblíbených a barevné kódování, funkce, jako je alpha kanálů a MIP mapování a řadu texture vysoce komprimované, accelerated hardwaru formáty, které podporuje rozhraní DirectX.  
  
## <a name="supported-formats"></a>Podporované formáty  
 Editor obrázků podporuje tyto formáty bitové kopie:  
  
|Název formátu|Přípona názvu souboru|  
|-----------------|-------------------------|  
|Formát PNG|soubor ve formátu PNG|  
|JPEG|JPG, JPEG, JPE, JFIF|  
|Přímé prostor pro kreslení|.DDS|  
|Formát GIF|.GIF|  
|Rastrový obrázek|BMP, DIB|  
|Formát TIFF|.tif, TIFF|  
|TGA (Targa)|TGA|  
  
## <a name="getting-started"></a>Začínáme  
 Tato část popisuje, jak přidat bitovou kopii vašeho [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektu a nakonfigurovat jej pro vaše požadavky.  
  
#### <a name="to-add-an-image-to-your-project"></a>Chcete-li přidat bitovou kopii do projektu  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro projekt, který chcete přidat do a potom vyberte **přidat**, **novou položku**.  
  
2.  V **přidat novou položku** dialogovém **nainstalovaná**, vyberte **grafiky**a pak vyberte příslušný formát pro bitovou kopii. Informace o tom, jak zvolte podle požadavků na formát souboru najdete v následující části.  
  
3.  Zadejte **název** souboru bitové kopie a **umístění** kde se má vytvořit.  
  
4.  Vyberte **přidat** tlačítko.  
  
### <a name="choosing-the-image-format"></a>Výběr formátu obrázku  
 V závislosti na tom, jak budete chtít použít bitovou kopii může být vhodnější než jiné určité formáty souborů. Například některé formáty nemusí podporovat funkce, která potřebujete – jako průhlednost nebo formát konkrétní barvy – nebo nemusí poskytnout vhodný komprese pro typ obsahu bitové kopie, které jste naplánovali.  
  
 Tyto informace můžete zvolit formátu obrázku, který vyhovuje vašim potřebám.  
  
 **Rastrový obrázek (BMP)**  
 Formát obrázku rastrového obrázku. Formát nekomprimované bitové kopie, který podporuje 24bitové barvy. Formát rastrového obrázku nepodporuje průhlednost.  
  
 **Obrázek ve formátu GIF (*.gif)**  
 Formát obrázku formátu GIF (Graphics Interchange). Formát kompresí LZW, beze ztrát bitové kopie, který podporuje až 256 barev. Není vhodný pro fotografie a bitové kopie, které mají významné množství podrobností, barva, ale poskytuje dobrou kompresi poměr pro nízká color bitové kopie, které mají vysoký stupeň soudržnost barev.  
  
 **Obrázek JPG (.jpg)**  
 Formát obrázku odborníky skupiny JPEG (Joint Photographic). Vysoce komprimované, míru ztrát bitovou kopii formátu, který podporuje 24bitové barvy a je vhodný pro obecné účely Komprese obrázků, které mají vysoký stupeň soudržnost barev.  
  
 **Obrázek PNG (.png)**  
 Formát obrázku Portable Network Graphics (PNG). Středně kompresí, beze ztrát bitovou kopii formátu, který podporuje 24bitové barvy a průhlednost alfa. Je vhodná pro přirozené a umělé bitové kopie, ale neposkytuje takové jako míru ztrát formáty například JPG nebo GIF kompresní poměr.  
  
 **Obrázek ve formátu TIFF (.tif)**  
 Formát obrázku Tagged Image File Format (TIFF nebo TIF). Flexibilní bitovou kopii formátu, který podporuje několik schémat komprese.  
  
 **Texture DDS (.dds)**  
 Formát texture nastavení obnovovací prostor (DDS). Texture vysoce komprimované, míru ztrát formátu, který podporuje 24bitové barvy a průhlednost alfa. Poměr jeho komprese může být až 8:1. Je založena na S3 Texture kompresi, která může dekomprimovat na grafickém hardwaru.  
  
 **Obrázek TGA (TGA)**  
 Formát obrázku Truevision grafický adaptér (TGA) (také označované jako Targa). Obrázek kompresí RLE, beze ztrát formátu, který podporuje obě mapované na barvu (barevná paleta) nebo přímo color bitové kopie až 24bitové barvy a průhlednost alfa. Není vhodný pro fotografie a bitové kopie, které mají významné množství podrobností, barva, ale poskytuje dobrou kompresi poměr pro bitové kopie, které mají dlouhou rozpětí stejné barvy.  
  
### <a name="configuring-the-image"></a>Konfigurace bitovou kopii  
 Než začnete pracovat s bitovou kopii, kterou jste právě vytvořili, můžete změnit výchozí konfiguraci. Můžete například změnit jeho dimenze nebo formát barvy, který používá. Informace o konfiguraci těchto a dalších vlastností bitové kopie najdete v tématu [obrázek vlastnosti](#ImageProperties).  
  
> [!NOTE]
>  Před uložením práci, nezapomeňte nastavit **formát barvy** vlastnost, pokud chcete použít formát konkrétní barvy. Pokud formát souboru podporuje komprese, můžete upravit nastavení komprese při uložení souboru poprvé nebo když zvolíte **uložit jako**.  
  
## <a name="working-with-the-image-editor"></a>Práce s Editor obrázků  
 Tato část popisuje, jak pomocí editoru obrázků změníte textury a bitové kopie.  
  
### <a name="image-editor-toolbars"></a>Panely nástrojů Editor obrázků  
 Editor obrázků panely nástrojů obsahovat příkazy, které pomohou práce s obrázky.  
  
 Příkazy, které ovlivňují stav Editor obrázků se nacházejí na **Editor obrázků režimu** nástrojů společně s pokročilé příkazy. Panelu nástrojů se nachází na nejhornější okraji návrhové ploše Editor obrázků. Kreslení jsou umístěny na **Editor obrázků** nástrojů podél krajní levé hrany návrhové ploše Editor obrázků.  
  
 Tady je **Editor obrázků režimu** nástrojů:  
  
 ![Editor obrázků modální nástrojů. ] (../designers/media/digit-tre-modal-toolbar.png "Číslice TRE modální nástrojů")  
  
 Tato tabulka popisuje položky na **Editor obrázků režimu** nástrojů, které jsou uvedeny v pořadí, ve kterém se zobrazí zleva doprava.  
  
|Položka na panelu nástrojů|Popis|  
|------------------|-----------------|  
|**Vyberte**|Umožňuje výběr obdélníkovou oblast bitové kopie. Po výběru oblasti, můžete můžete vyjmout, kopírovat, přesunout, škálovat, otočit, překlopit nebo odstranit. Když je aktivní výběr, nástrojů pro kreslení ovlivní pouze vybrané oblasti.|  
|**Nestandardní výběr**|Umožňuje výběr oblast nestandardní bitové kopie. Po výběru oblasti, můžete můžete vyjmout, kopírovat, přesunout, škálovat, otočit, překlopit nebo odstranit. Když je aktivní výběr, nástrojů pro kreslení ovlivní pouze vybrané oblasti.|  
|**Výběr hůlka**|Umožňuje výběr podobně barevných oblasti obrázku. *Tolerance*– to znamená, maximální rozdíl mezi sousedních barev v rámci které jsou považovány za podobné – lze nakonfigurovat, aby zahrnout menší nebo širší škálu podobné barev. Po výběru oblasti, můžete můžete vyjmout, kopírovat, přesunout, škálovat, otočit, překlopit nebo odstranit. Když je aktivní výběr, nástrojů pro kreslení ovlivní pouze vybrané oblasti.|  
|**Pan**|Umožňuje přesun bitové kopie relativně k rámce okna. V **Panoramování** režimu, vyberte bod obrázku a pak pohyb.<br /><br /> Můžete dočasně aktivovat **Panoramování** režimu tak, že stisknete a podržíte klávesu Ctrl.|  
|**Přiblížení**|Umožňuje zobrazení více nebo méně image podrobností relativně k rámce okna. V **zvětšení** režimu, vyberte bod obrázku a pak přesunout doprava dolů na přiblížit nebo doleva nebo až přiblížení out.<br /><br /> Můžete zvětšit nebo zmenšit podržíte a Ctrl můžete použít kolečko myši nebo stiskněte klávesu znaménko Plus (+) nebo Minus (-).|  
|**Na skutečnou velikost**|Zobrazí bitovou kopii pomocí vztahu 1:1 mezi pixelů bitové kopie a pixelů na obrazovce.|  
|**Nejlepší přiblížení**|Zobrazí úplnou bitovou kopii v rámce okna.|  
|**Zvětšení šířky**|Zobrazí celou šířku obrázku v rámce okna.|  
|**Mřížky**|Povolí nebo zakáže mřížky, který ukazuje hranice pixelů. Dokud zvětšení bitovou kopii, se nemusí zobrazit mřížky.|  
|**Další úroveň MIP zobrazení**|Aktivuje další větší MIP úrovni v řetězu MIP mapy. Úroveň active MIP se zobrazí na návrhovou plochu. Tato položka je dostupná jenom pro textury, které mají MIP úrovně.|  
|**Zobrazení předchozí MIP úrovně**|Aktivuje další menší MIP úrovni v řetězu MIP mapy. Úroveň active MIP se zobrazí na návrhovou plochu. Tato položka je dostupná jenom pro textury, které mají MIP úrovně.|  
|**Červený kanál**<br /><br /> **Kanál zelená**<br /><br /> **Modrá kanálu**<br /><br /> **Alfa kanálu**|Povolí nebo zakáže určité barevný kanál. **Poznámka:** systematičtěji povolením nebo zakázáním kanály barev, můžete izolovat problémy, které se vztahují na jeden nebo více z nich. Můžete třeba zjistit nesprávný průhlednost alfa.|  
|**Pozadí**|Povolí nebo zakáže zobrazení prostřednictvím transparentní částí obrázku na pozadí. Můžete nakonfigurovat, jak se zobrazí na pozadí a vybrat z těchto možností:<br /><br /> **Šachovnice**<br /> Používá zelenou barvu společně s barvu pozadí zadané pro zobrazení na pozadí jako šachovnicový vzor. Tuto možnost můžete použít k lepšímu více zřejmá transparentní částí obrázku.<br /><br /> Bílé pozadí<br /> Barva bílé používá pro zobrazení na pozadí.<br /><br /> Začernit pozadí<br /> Používá černé barvy pro zobrazení na pozadí.<br /><br /> Animace pozadí<br /> Posouvá šachovnicový vzor pomalu. Tuto možnost můžete použít k lepšímu více zřejmá transparentní částí obrázku.|  
|**Vlastnosti**|Případně otevře nebo zavření **vlastnosti** okno.|  
|**Upřesnit**|Obsahuje další příkazy a možnosti.<br /><br /> **Filtry**<br /><br /> Poskytuje několik běžných filtry bitové kopie: **černobílý**, **rozostření**, **Brighten**, **ztmavit**, **detekce okraje**, **Reliéf**, **invertování barev**, **Ripple**, **sépii**, a **Zostřit**.<br /><br /> **Moduly grafiky**<br /><br /> **Vykreslení s D3D11**<br /> Direct3D – 11 používá k vykreslení návrhovou plochu Editor obrázků.<br /><br /> **Vykreslení s D3D11WARP**<br /> Direct3D – 11 Windows Advanced Rasterizační platformy (Osnova) používá k vykreslení návrhovou plochu Editor obrázků.<br /><br /> **Nástroje**<br /><br /> **Překlopit vodorovných**<br /> Transponuje bitovou kopii kolem jeho vodorovné nebo x, osy.<br /><br /> **Překlopit Vertical**<br /> Transponuje bitovou kopii kolem jeho vertical nebo y, osy.<br /><br /> **Generovat Mips**<br /> Generuje MIP úrovně pro bitovou kopii. Pokud MIP úrovně již existují, se znovu vytvoří z největší MIP úrovně. Veškeré změny, které byly provedeny na menší MIP úrovně budou ztraceny. Pokud chcete uložit MIP úrovně, které se mají vygenerovat, musí používat formát .dds Pokud chcete uložit obrázek.<br /><br /> **Zobrazení**<br /><br /> **Obnovovací frekvence**<br /> Když je povolené, zobrazí v pravém horním rohu na návrhovou plochu snímků za sekundu. Frekvence snímků je počet snímků, které jsou zpracovány za sekundu. **Tip:** můžete **Upřesnit** tlačítko poslední příkaz spusťte znovu.|  
  
 Tady je **Editor obrázků** panelu nástrojů.  
  
 ![Editor obrázků panelu nástrojů](../designers/media/digit-tre-toolbar.png "číslice. TRE nástrojů")  
  
 Následující tabulka popisuje položky na **Editor obrázků** nástrojů, které jsou uvedeny v pořadí, ve kterém se zobrazí shora dolů.  
  
|Položka na panelu nástrojů|Popis|  
|------------------|-----------------|  
|**Tužky**|Výběr active barva se použije k vykreslení tahu alias. Můžete nastavit barvy a tloušťky tahu v **vlastnosti** okno.|  
|**Štětce**|Výběr active barva se použije k vykreslení tahu vyhlazené. Můžete nastavit barvy a tloušťky tahu v **vlastnosti** okno.|  
|**Rozprašovač**|Výběr active barva se použije k vykreslení tahu vyhlazené, který smíchá společně s bitovou kopii a že bude sytější jako funkce čas. Můžete nastavit barvy a tloušťky tahu v **vlastnosti** okno.|  
|**Kapátko**|Nastaví aktivní barva výběr barvy vybraných pixelů.|  
|**Vyplnění**|Výběr active barva se použije k vyplnění oblasti obrázku. Ovlivněné oblast je definován jako pixelů, kdy se používá výplň, společně s každou pixelů, který je připojený ke svému pixelů stejné barvy a který je stejné barvy sám sebe. Výplň je použit v rámci aktivní výběr, je omezené oblasti ovlivněný výběrem.<br /><br /> Ve výchozím nastavení je spolu s ovlivněných oblast bitovou kopii podle jeho alfa součást smíšení active barva výběru. Pokud chcete přepsat oblasti ovlivněných pomocí active barva výběru, stiskněte a podržte klávesu Shift při použití nástroje výplně.|  
|**Mazání**|Nastaví pixelů na plně průhlednou barvu, pokud bitovou kopii podporuje kanálu alfa. Barva pozadí aktivní, jinak hodnota nastaví pixelů.|  
|**Řádek**, **obdélníku**, **zaoblený obdélník**, **třemi tečkami**|Kreslení obrazce na bitovou kopii. Můžete nastavit barvy a Tloušťka obrysu v **vlastnosti** okno.<br /><br /> Kreslení na primitivní, který má stejné šířky a výšky, stiskněte a podržte stisknutou klávesu Shift při kreslení.|  
|**Text**|Kreslení textu pomocí výběr barev popředí. Barva pozadí je určen podle výběr barvu pozadí. Alfa hodnota výběru barva pozadí pro průhledné pozadí, musí být 0. Při oblasti textu je aktivní, můžete nastavit, zda text vykreslením s tahu vyhlazené a můžete nastavit text **hodnotu**, **písma**, **velikost**a stylu –**Bold**, **Italics**, nebo **podtržené**– v **vlastnosti** okno. Obsah a vzhled textu je dokončené, když je již aktivní oblasti textu.|  
|**Otočit**|Otočí obrázek 90 stupňů po směru hodinových ručiček.|  
|**Uvolnění dočasné paměti**|Ořízne obrázek, který se aktivní výběr.|  
  
### <a name="working-with-mip-levels"></a>Práce s MIP úrovně  
 Některé bitové kopie formáty – například prostor pro nastavení obnovovací (.dds) – podpora pro úrovně MIP texture místo úroveň z – podrobnosti (mez Stanovitelnosti). Informace o tom, jak vygenerovat a pracovat s úrovní MIP najdete v tématu [postupy: vytvoření a úprava MIP úrovně](../designers/how-to-create-and-modify-mip-levels.md)  
  
### <a name="working-with-transparency"></a>Práce s průhlednosti  
 Některé bitové kopie formáty – například prostor pro nastavení obnovovací (.dds) – podporují průhlednost. Existuje několik způsobů, že průhlednost lze použít v závislosti na nástroj, že používáte. Určete úroveň průhlednosti pro výběr barev, v **vlastnosti** nastavte **A** (alfa) součást výběr barev. Tady je způsob různé druhy nástroje pro řízení použití průhlednost:  
  
|Nástroj|Popis|  
|----------|-----------------|  
|**Tužky**, **štětce**, **rozprašovač**, **řádku**, **obdélníku**, **zaoblený obdélník**, **Elipsy**, **textu**|A přizpůsobte active barva výběru společně s bitovou kopii, v **vlastnosti** okno, rozbalte **kanály** skupinu vlastností a sadu **kreslení** zaškrtávací políčko je na  **Alpha** kanálu a pak kreslení normálně.<br /><br /> Kreslení pomocí active barva výběr a ponechejte alfa bitové kopie na místě, zrušte **kreslení** políčko z **Alpha** kanálu a pak kreslení normálně.|  
|**Vyplnění**|A přizpůsobte active barva výběru společně s bitovou kopii, vyberte právě oblasti k vyplnění.<br /><br /> Použít active barva výběru – včetně hodnotu alfa kanálu – přepsat bitovou kopii, stiskněte a podržte stisknutou klávesu Shift a potom zvolte oblasti k vyplnění.|  
  
###  <a name="ImageProperties"></a>Vlastnosti bitové kopie  
 Můžete použít **vlastnosti** okno zadat různé vlastnosti bitové kopie. Například můžete nastavit vlastnosti Šířka a výška obrázku.  
  
 Následující tabulka popisuje vlastnosti bitové kopie.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|Šířka|Šířka bitovou kopii.|  
|Výška|Výška obrázku.|  
|Bitů na Pixel|Počet bitů, které představují každý pixelů. Hodnota této vlastnosti závisí na **formát barvy** bitové kopie.|  
|Transparentní výběr|**Hodnota TRUE,** a přizpůsobte vrstvě výběr společně s hlavní bitové kopie, podle hodnoty alfa vrstvě výběr; v opačném **False**. Tato položka je dostupná jenom pro bitové kopie, které podporují alfa.|  
|Formát|Barva formát obrázku. V závislosti na formát obrázku lze zadat různých formátech barev. Formát barvy definuje počet a typ kanály barev, které jsou zahrnuty v bitové kopie a velikost a kódování různých kanálů.|  
|Úroveň MIP|Aktivní MIP úroveň. Tato položka je dostupná jenom pro textury, které mají MIP úrovně.|  
|Počet MIP úroveň|Celkový počet úrovní MIP v bitové kopii. Tato položka je dostupná jenom pro textury, které mají MIP úrovně.|  
|Počet snímků|Celkový počet rámců v bitové kopii. Tato položka je dostupná jenom pro bitové kopie, které podporují texture pole.|  
|Rámec|Aktuální rámečku. Lze zobrazit pouze první snímek; všechny ostatní snímky jsou ztraceny, když se uloží bitovou kopii.|  
|Hloubka řez počet|Celkový počet řezů hloubka v bitové kopii. Tato položka je dostupná jenom pro bitové kopie, které podporují textury svazku.|  
|Hloubka řez|Aktuální hloubka řez. Lze zobrazit pouze první řez; Další řezy jsou ztraceny, když se uloží bitovou kopii.|  
  
> [!NOTE]
>  Protože **otočit podle** vlastnost se vztahuje na všechny nástroje a vybrané oblasti, zobrazí se vždy v dolní části **vlastnosti** okno společně s další vlastnosti nástroje. **Otočit podle** je vždy zobrazit, protože celého obrázku je implicitně vybrána, když není žádný výběr nebo aktivní nástroj. Další informace o **otočit podle** vlastnost, najdete v části [vlastnosti nástroje](#ToolProperties).  
  
#### <a name="resizing-images"></a>Změna velikosti obrázků  
 Tady jsou dva způsoby, jak změnit velikost obrázku. Editor obrázků v obou případech používá bi lineární interpolace pro převzorkování bitovou kopii.  
  
-   V **vlastnosti** okno, zadejte nové hodnoty pro **šířka** a **výška** vlastnosti.  
  
-   Vyberte celého obrázku a použijte ke změně velikosti obrázku ohraničení značek.  
  
### <a name="working-with-tools"></a>Práce s nástroji  
  
#### <a name="selected-regions"></a>Vybrané oblasti  
 Výběr v editoru obrázků definovat oblasti bitové kopie, které jsou aktivní – to znamená, oblast nebude mít vliv nástroje a transformace. Když je aktivní výběr, nejsou oblasti mimo vybrané oblasti vliv Většina nástrojů a transformace. Pokud není aktivní výběr, celého obrázku je aktivní.  
  
 Většina nástrojů –**tužky**, **štětce**, **rozprašovač**, **vyplnění**, **mazání**a primitiv 2-D – a transformace –**otočit**, **Trim**, **Invertovat barvy**, **Překlopit vodorovně**, a **Překlopit svisle** – jsou omezené nebo definované aktivní výběr. Však některé nástroje –**kapátko** a **Text**– a transformace –**generovat Mips**– neovlivní žádné aktivní výběr; tyto nástroje vždy chovat, jako kdyby celý bitová kopie je aktivní výběr.  
  
 Při výběru oblasti, stiskněte a podržte stisknutou klávesu Shift můžete vybrat proporční (hranaté); výběr, jinak hodnota není omezené.  
  
##### <a name="resizing-selections"></a>Možnosti změny velikosti  
 Po výběru oblasti, můžete změnit velikost ho či jeho obsahem obrázku tak, že změníte velikost značky výběr. Když měníte vybrané oblasti, můžete použít následující modifikační klávesy můžete změnit chování vybrané oblasti při změně velikosti (když stisknete a podržíte klíč jako můžete změnit velikost).  
  
 CTRL  
 Zkopíruje obsah vybrané oblasti, než se změnila velikost. Neporušené původní bitové kopie při změně velikosti kopie.  
  
 Posunutí  
 Změní velikost vybrané oblasti v poměru k jeho původní velikost.  
  
 ALT  
 Změní velikost oblasti výběru. Zůstane bitovou kopii ponechat beze změny.  
  
 Zde jsou kombinace kláves platný modifikátor:  
  
|CTRL|Posunutí|ALT|Popis|  
|----------|-----------|---------|-----------------|  
||||Změní velikost obsahu vybrané oblasti.|  
||Posunutí||Úměrně změní obsah vybrané oblasti.|  
|||ALT|Změní velikost vybrané oblasti. Definuje novou oblast výběru.|  
||Posunutí|ALT|Úměrně změní vybrané oblasti. Definuje novou oblast výběru.|  
|CTRL|||Zkopíruje a poté změní obsah vybrané oblasti.|  
|CTRL|Posunutí||Zkopíruje a úměrně změní obsah vybrané oblasti.|  
  
####  <a name="ToolProperties"></a>Vlastnosti nástroje  
 Nástroj je vybráno, můžete použít **vlastnosti** okna zadejte podrobnosti o tom, jak ovlivňuje bitovou kopii. Například můžete nastavit tloušťka **tužky** nástroje nebo barvu **štětce** nástroj.  
  
 Můžete nastavit barvu popředí a barvu pozadí. Obě podporují alfa kanálu zajistit krytí definovaný uživatelem. Nastavení budou platit pro všechny nástroje. Pokud používáte myši, levým tlačítkem myši odpovídá barvu popředí a odpovídá pravým tlačítkem myši na barvu pozadí.  
  
 Následující tabulka popisuje vlastnosti nástroje.  
  
|Nástroj|Vlastnosti|  
|----------|----------------|  
|Všechny nástroje a možnosti|**Otočit podle**<br /> Definuje dobu, ve stupních, že platnost výběru nebo nástroj otočen ve směru hodinových ručiček.|  
|**Tužky**, **štětce**, **rozprašovač**, **mazání**|**Tloušťka**<br /> Definuje velikost oblasti, která jsou ovlivněná nástroj.|  
|**Text**|**Vyhlazení**<br /> Kreslení textu, který má vyhlazené okraje. To dává hladší vzhled textu.<br /><br /> **Hodnota**<br /> Text, které se mají vykreslovat.<br /><br /> **Písma**<br /> Písmo použité k vykreslení text.<br /><br /> **Velikost**<br /> Velikost textu.<br /><br /> **Bold**<br /> Díky tučné písmo.<br /><br /> **Italics**<br /> Umožňuje výběr kurzívy písmo.<br /><br /> **Podtržené**<br /> Díky písmo podtržené.|  
|**Primitivní 2-D**|**Vyhlazení**<br /> Nakreslí primitivních elementů, které mají vyhlazené okraje. Tato funkce je hladší vzhled.<br /><br /> **Tloušťka**<br /> Určuje tloušťku čáry, která tvoří hranici primitivní vlastnost.<br /><br /> **RADIUS X**<br /> (Jenom zaoblený obdélník) Definuje zaokrouhlení radius pro horní a dolní hrany primitivní vlastnost.<br /><br /> **RADIUS Y**<br /> (Jenom zaoblený obdélník) Definuje zaokrouhlení radius levé a pravé hrany primitivní vlastnost.|  
|**Tužky**, **štětce**, **rozprašovač**, **primitivní 2-D**|**Kanály**<br /> Povolí nebo zakáže určité barevné kanály pro zobrazování a kreslení. Pokud **zobrazení** je nastavit pro konkrétní barevný kanál, tento kanál je vidět na obrázku; jinak se nezobrazuje. Pokud **kreslení** nastavená pro konkrétní barevný kanál, že kanál je ovlivněných podle kreslení operace; jinak, není.|  
|**Výběr hůlka**, **vyplnění**|**Tolerance**<br /> Definuje maximální rozdíl mezi sousedních barev v rámci které jsou považovány za podobné, tak, aby méně nebo více podobné barvy jsou vytvářeny součástí ovlivněných nebo vybrané oblasti. Ve výchozím nastavení hodnota je 32, což znamená, že jsou považovány za sousedících pixelů v rámci 32 odstínech původní barvu (světlejší nebo tmavšího) jako součást oblasti.|  
  
## <a name="keyboard-shortcuts"></a>Klávesové zkratky  
  
|Příkaz|Klávesové zkratky|  
|-------------|------------------------|  
|Přepnout na **vyberte** režimu|S|  
|Přepnout na **zvětšení** režimu|Z|  
|Přepnout na **Panoramování** režimu|K|  
|Vybrat vše|Ctrl+A|  
|Odstranit aktuální výběr|Odstranit|  
|Zrušit aktuální výběr|Escape|  
|Přiblížit|Ctrl + kolečko myši dopředu<br /><br /> Ctrl+PageUp<br /><br /> Znaménko plus (+)|  
|Oddálit|Ctrl kolečko myši zpětné<br /><br /> CTRL lektora<br /><br /> Znaménko minus (-)|  
|Posunutí obrazu nahoru|Kolečko myši dozadu<br /><br /> PageDown|  
|Posunutí obrazu dolů|Kolečko myši dopředu<br /><br /> PageUp|  
|Posouvání obrázek vlevo|Shift + kolečko myši dozadu<br /><br /> Kolečko myši doleva<br /><br /> SHIFT + lektora|  
|Posouvání právo bitové kopie|Shift + kolečko myši dopředu<br /><br /> Kolečko myši doprava<br /><br /> Shift + PageUp|  
|Na skutečnou velikost|CTRL + 0 (nula).|  
|Přizpůsobení bitové kopie do okna|CTRL + G, Ctrl + F|  
|Přizpůsobit obraz šířky oken|CTRL + G, Ctrl + I|  
|Přepnutí mřížky|CTRL + G, kombinaci kláves Ctrl + G|  
|Oříznutí obrázku pro aktuální výběr|CTRL + G, Ctrl + C|  
|Zobrazit další (vyšší podrobnosti) MIP úroveň|CTRL + G, kombinace kláves Ctrl + 6|  
|Zobrazit předchozí (nižší podrobností) MIP úroveň|CTRL + G, kombinace kláves Ctrl + 7|  
|Přepnutí červenou barvu kanálu|CTRL + G, kombinace kláves Ctrl + 1|  
|Přepnutí zelenou barvu kanálu|CTRL + G, kombinace kláves Ctrl + 2|  
|Přepnutí modrou barvu kanálu|CTRL + G, kombinace kláves Ctrl + 3|  
|Přepněte kanálu alfa (průhlednost)|CTRL + G, kombinace kláves Ctrl + 4|  
|Přepnutí alfa šachovnicový vzor|CTRL + G, Ctrl + B|  
|Přepnout na nestandardní výběr nástroj|L|  
|Přepnout na výběr hůlka|M|  
|Přepínač tak, aby tužka, nástroj|P|  
|Přepínač tak, aby zdokonalit nástroj|B|  
|Přepínač tak, aby vyplnit – nástroj|F|  
|Přepnout na nástroj mazání|E|  
|Přepnout na text|T|  
|Přepnout na nástroj barva – vybrat (kapátko)|I|  
|Přesuňte aktivní výběr a její obsah.|Klávesy se šipkami.|  
|Změnit velikost aktivní výběr a její obsah.|CTRL + klávesy se šipkami|  
|Přesunete aktivní výběr, ale nikoli jeho obsah.|Kláves SHIFT + ŠIPKA|  
|Změnit velikost aktivní výběr, ale nikoli jeho obsah.|Ctrl + Shift + šipka klíče|  
|Potvrdit aktuální vrstva|Vrátí|  
|Snížení sílu nástroj|[|  
|Zvýšit sílu nástroj|]|  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Práce s 3D prostředky pro hry a aplikace](../designers/working-with-3-d-assets-for-games-and-apps.md)|Obsahuje přehled nástroje, které můžete použít v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] pro práci s prostředky grafiky například textury a bitové kopie, 3D modely a shaderu účinky.|  
|[Editor modelu](../designers/model-editor.md)|Popisuje postup použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] modelu Editor pro práci s 3D modely.|  
|[Návrhář shaderu](../designers/shader-designer.md)|Popisuje postup použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] shaderu Designer pro práci s shadery.|