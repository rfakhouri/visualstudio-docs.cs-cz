---
title: Návrhář shaderů
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: conceptual
f1_keywords:
- vs.graphics.designer.effectdesigner
- vs.graphics.shaderdesigner
ms.assetid: 5db09a16-b82c-4ba3-8ec9-630cdc109397
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 641db475998d62df534353824f9d58a01c8d1792
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="shader-designer"></a>Návrhář shaderů

Tento dokument popisuje, jak pracovat [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] shaderu návrháři k vytváření, úpravě a exportovat vlastní vizuálních efektů, které jsou známé jako *shadery*.

Návrhář shaderu můžete vytvořit vlastní vizuální efekty pro hry nebo aplikace, i v případě, že nevíte HLSL programování. Pokud chcete vytvořit shaderu v Návrháři shaderu, právě rozložení ho jako graf; To znamená, přidejte na návrhovou plochu *uzly* , představují data a operace a pak proveďte připojení mezi nimi můžete definovat, jak operace zpracovat data. V každém uzlu operace je k dispozici náhled účinek tohoto bodu tak, aby můžete vizualizovat její výsledek. Toky dat prostřednictvím uzlů směrem k poslední uzel, který představuje výstup shaderu.

## <a name="supported-formats"></a>Podporované formáty

Návrhář shaderu podporuje tyto formáty shaderu:

|Název formátu|Přípona souboru|Podporované operace (zobrazení, úpravy, Export)|
|-----------------|--------------------|-------------------------------------------------|
|Jazyk shaderu orientovaného grafu|.dgsl|Zobrazení, úpravy|
|Shaderu HLSL (zdrojový kód)|.hlsl|Export|
|Shaderu HLSL (bajtového kódu)|.CSO|Export|
|Hlavička C++ (HLSL bajtového kódu pole)|.h|Export|

## <a name="get-started"></a>Začínáme

Tato část popisuje postup přidání DGSL shaderu k vaší [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektu a obsahuje základní informace, které vám pomůže začít.

### <a name="to-add-a-dgsl-shader-to-your-project"></a>Chcete-li přidat shaderu DGSL do projektu

1.  V **Průzkumníku řešení**, otevřete místní nabídku pro projekt, který chcete přidat shaderu k a potom vyberte **přidat**, **novou položku**.

2.  V **přidat novou položku** dialogovém **nainstalovaná**, vyberte **grafiky**a potom vyberte **Visual shaderu grafu (.dgsl)**.

3.  Zadejte **název** souboru shaderu a **umístění** kde se má vytvořit.

4.  Vyberte **přidat** tlačítko.

### <a name="the-default-shader"></a>Výchozí shaderu

Pokaždé, když vytvoříte shaderu DGSL, začne jako minimální shaderu, který má právě **bodu barva** uzlu, který je připojen k **konečnou barvu** uzlu. I když tento shaderu je úplný a funkční, mnoho neprovádí. Proto je prvním krokem při vytváření shaderu pracovní často odstranit **bodu barva** uzlu nebo odpojení z **konečnou barvu** uzlu, aby uvolnil prostor pro další uzly.

## <a name="work-with-the-shader-designer"></a>Pracovat s návrhářem shaderu

Následující části popisují, jak používat návrháře shaderu pro práci s vlastní shadery.

### <a name="shader-designer-toolbars"></a>Panely nástrojů Návrhář shaderu

Návrháře shaderu, které obsahují panely nástrojů příkazy, které pomáhají, se kterými můžete pracovat DGSL shaderu grafy.

Příkazy, které ovlivňují stav návrháře shaderu jsou umístěny na **režimu návrháře shaderu** panelu nástrojů v hlavní [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] okno. Návrh nástroje a příkazy jsou umístěny na **shaderu Návrhář** panelu nástrojů na návrhovou plochu návrháře shaderu.

Tady je **režimu návrháře shaderu** nástrojů:

![Modální nástrojů shaderu návrháře. ] (../designers/media/digit-dsd-modal-toolbar.png "Číslice DSD modální nástrojů")

Tato tabulka popisuje položky na **režimu návrháře shaderu** nástrojů, které jsou uvedeny v pořadí, ve kterém se zobrazí zleva doprava:

|Položka na panelu nástrojů|Popis|
|------------------|-----------------|
|**Vyberte**|Umožňuje interakci s uzly a okraje v grafu. V tomto režimu můžete vybrat uzly a přesunout nebo je odstranit, a můžete vytvořit okraje nebo je rozdělit.|
|**Posouvání**|Umožňuje přesun graf shaderu relativně k rámce okna. Posunete zobrazení, vyberte bod na návrhovou plochu a přesunout ji.<br /><br /> V **vyberte** režimu, stiskněte a podržte klávesu Ctrl k aktivaci **Panoramování** dočasně režimu.|
|**Přiblížení**|Umožňuje zobrazení více nebo méně shaderu grafu podrobností relativně k rámce okna. V **zvětšení** režimu, vyberte bod na návrhovou plochu a potom přesunout doprava dolů na přiblížit nebo doleva nebo až přiblížení out.<br /><br /> V **vyberte** režimu, můžete stiskněte a podržte klávesu Ctrl zvětšit nebo zmenšit pomocí kolečko myši.|
|**Nejlepší přiblížení**|Zobrazí graf úplné shaderu v rámce okna.|
|**Režim vykreslování v reálném čase**|Pokud je povolena v reálném čase vykreslování, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ho překreslí na návrhovou plochu, i když je provedena žádná akce uživatele. Tento režim je užitečný při práci se shadery, které se mění v průběhu času.|
|**Náhled s oblasti**|Když je povolené, model oblasti slouží k zobrazení náhledu shaderu. Lze povolit pouze jeden preview tvar najednou.|
|**Náhled s datové krychle**|Když je povolené, model datové krychle se používá k zobrazení náhledu shaderu. Lze povolit pouze jeden preview tvar najednou.|
|**Preview s cylindr**|Když je povolené, model cylindr slouží k zobrazení náhledu shaderu. Lze povolit pouze jeden preview tvar najednou.|
|**Náhled s kuželem**|Když je povolené, model kužele slouží k zobrazení náhledu shaderu. Lze povolit pouze jeden preview tvar najednou.|
|**Náhled s teapot**|Když je povolené, model teapot slouží k zobrazení náhledu shaderu. Lze povolit pouze jeden preview tvar najednou.|
|**Náhled s roviny**|Když je povolené, model rovinou slouží k zobrazení náhledu shaderu. Lze povolit pouze jeden preview tvar najednou.|
|**Panel nástrojů**|Případně zobrazí nebo skryje **sada nástrojů**.|
|**Vlastnosti**|Můžete také zobrazí nebo skryje **vlastnosti** okno.|
|**Pokročilé**|Obsahuje pokročilé příkazy a možnosti.<br /><br /> **Export**: umožňuje exportovat shaderu v různých formátech.<br /><br /> **Exportovat jako**: Exportuje shaderu buď HLSL zdrojový kód nebo jako kompilované shaderu. Další informace o tom, jak exportovat shadery najdete v tématu [postupy: Export shaderu](../designers/how-to-export-a-shader.md).<br /><br /> **Grafika moduly**: umožňuje výběr zobrazovací jednotky, která se používá k zobrazení na návrhovou plochu.<br /><br /> **Vykreslení s D3D11**: 11 Direct3D – používá k vykreslení návrhovou plochu návrháře shaderu.<br /><br /> **Vykreslení s D3D11WARP**: používá Direct3D – 11 Windows Advanced Rasterizační platformy (Osnova) k vykreslení návrhovou plochu návrháře shaderu.<br /><br /> **Zobrazení**: umožňuje výběr další informace o návrháři shaderu.<br /><br /> **Míra s rámečkem**: když je povolené, zobrazí aktuální obnovovací frekvence v pravém horním rohu na návrhovou plochu. Frekvence snímků je počet snímků, které jsou zpracovány za sekundu.  Tato možnost je užitečná, když povolíte **režimu vykreslování v reálném čase** možnost.|

> [!TIP]
> Můžete **Upřesnit** tlačítko poslední příkaz spusťte znovu.

### <a name="work-with-nodes-and-connections"></a>Práce s uzly a připojení

Použití **vyberte** režimu přidávat, odstraňovat, změnit umístění, připojení a konfiguraci uzlů. Zde je postup provádění těchto základních operací:

#### <a name="to-perform-basic-operations-in-select-mode"></a>K provádění základních operací v režimu vyberte

-   Tady je jak:

    -   Chcete-li přidat uzel do grafu, vyberte ho v **sada nástrojů** a poté ho přesuňte na plochu návrháře.

    -   Chcete-li odebrat uzel z grafu, vyberte ho a potom stiskněte klávesu Delete.

    -   Chcete-li změnit umístění uzlu, vyberte ho a potom ho přesunout do nového umístění.

    -   Chcete-li připojit dva uzly, přesunete do vstupní Terminálové tohoto uzlu výstupu terminál jeden uzel. Může být připojen pouze terminály, které mají kompatibilní typy. Řádek mezi terminály znázorňuje připojení.

    -   Odebrat připojení na místní nabídku pro jednu z připojených terminály, zvolte **rozdělit odkazy**.

    -   Chcete-li konfigurovat vlastnosti uzlu, vyberte uzel a pak na **vlastnosti** okno, zadejte nové hodnoty pro vlastnosti.

### <a name="preview-shaders"></a>Shadery Preview

Abyste lépe pochopili, jak se objeví shaderu ve vaší aplikaci, můžete nakonfigurovat, jak je zobrazen náhled vaší vliv. Sblížit vaší aplikace, můžete zvolit jeden z několika tvarů vykreslení, nakonfigurujte textury a dalších materiálech parametrů, povolit animace založené na čase důsledky, a zkontrolujte preview z různých úhlů.

#### <a name="shapes"></a>Obrazce

Návrhář shaderu obsahuje šest obrazce – oblasti, datové krychle, cylindr, kužel, teapot a rovinou – můžete zobrazit náhled vaší shaderu. V závislosti na shaderu určité tvarů může získáte lepší náhled.

Zvolte preview tvaru, v **shaderu Návrhář režimy** nástrojů vyberte obrazec, který chcete.

#### <a name="textures-and-material-parameters"></a>Podstatným parametry a textury
 Mnohé shadery spoléhají na textury a vlastnosti materiálu k vytvoření jedinečné vzhled pro každý typ objektu ve vaší aplikaci. Pokud chcete zobrazit, co bude vaše shaderu vypadat ve vaší aplikaci, můžete nastavit textury a podstatným vlastnosti, které se použijí k vykreslení ve verzi preview tak, aby odpovídaly textury a parametry, které můžete použít ve vaší aplikaci.

##### <a name="to-bind-a-different-texture-to-a-texture-register-or-to-modify-other-material-parameters"></a>Svázat různé texture texture registrace, nebo upravte ostatní podstatným parametry

1.  V **vyberte** režimu, vyberte na prázdnou oblast na návrhovou plochu. To způsobí, že **vlastnosti** okna zobrazte globální shaderu vlastnosti.

2.  V **vlastnosti** okno, zadejte nové hodnoty pro vlastnosti texture a parametrů, které chcete změnit.

Zde jsou shaderu parametry, které můžete upravit:

|Parametr|Vlastnosti|
|---------------|----------------|
|**Texture 1** - **Texture 8**|**Přístup k**: **veřejné** umožňující vlastnost, která má být nastaven z editoru modelu, jinak hodnota **privátní**.<br /><br /> **Název souboru**: úplná cesta texture souboru, který je přidružen tento texture registrace.|
|**Materiály vedlejším**|**Přístup k**: **veřejné** umožňující vlastnost, která má být nastaven z editoru modelu, jinak hodnota **privátní**.<br /><br /> **Hodnota**: rozptýlených barva aktuální pixelů kvůli nepřímých - nebo vedlejším - osvětlení.|
|**Rozptýlené materiály**|**Přístup k**: **veřejné** umožňující vlastnost, která má být nastaven z editoru modelu, jinak hodnota **privátní**.<br /><br /> **Hodnota**: barvu, která popisuje, jak aktuální pixelů rozptýlí přímé osvětlení.|
|**Materiály Emissive**|**Přístup k**: **veřejné** umožňující vlastnost, která má být nastaven z editoru modelu, jinak hodnota **privátní**.<br /><br /> **Hodnota**: barva podíl aktuální pixelů kvůli samoobslužné zadaný osvětlení.|
|**Zrcadlová materiály**|**Přístup k**: **veřejné** umožňující vlastnost, která má být nastaven z editoru modelu, jinak hodnota **privátní**.<br /><br /> **Hodnota**: barvu, která popisuje, jak aktuální pixelů odráží přímé osvětlení.|
|**Podstatným zrcadlová napájení**|**Přístup k**: **veřejné** umožňující vlastnost, která má být nastaven z editoru modelu, jinak hodnota **privátní**.<br /><br /> **Hodnota**: exponent, která definuje intenzitou zrcadlová světla na aktuální pixelů.|

#### <a name="time-based-effects"></a>Založené na čase efekty

Některé shadery mít založené na čase komponenty, která animuje účinek. Pokud chcete zobrazit, co účinek vypadá v akci, verze preview má aktualizovat několikrát za sekundu. Ve výchozím nastavení je ve verzi preview pouze aktualizovat při změně shaderu; Toto chování změnit, aby mohli zobrazit založené na čase důsledky, budete muset povolit vykreslování v reálném čase.

Chcete-li povolit v reálném čase vykreslování, na panelu nástrojů návrháře shaderu zvolte **vykreslování v reálném čase**.

#### <a name="examine-the-effect"></a>Zkontrolujte účinek

Mnohé shadery jsou ovlivněné proměnných, například zobrazení úhel nebo směrovou osvětlení. Zjistit, jak reagovat účinek mění tyto proměnné, můžete volně Otočit tvar preview a sledovat, jak se chová shaderu.

Chcete-li otočit obrazec, stiskněte a podržte **Alt**a poté vyberte libovolného bodu na návrhovou plochu a přesunout ho.

### <a name="export-shaders"></a>Export shadery

Před použitím shaderu ve vaší aplikaci, musíte ho exportovat ve formátu, který funguje s technologií DirectX.

Shadery můžete exportovat jako HLSL zdrojový kód nebo jako kompilované shaderu. HLSL zdrojového kódu se exportují do textového souboru, který má příponu názvu souboru .hlsl. Nezpracovaná binární soubor, který má příponu názvu souboru .cso nebo do souboru C++ hlavičky (), který kóduje shaderu do pole, je možné exportovat shaderu.

Další informace o tom, jak exportovat shadery najdete v tématu [postupy: Export shaderu](../designers/how-to-export-a-shader.md).

## <a name="keyboard-shortcuts"></a>Klávesové zkratky

|Příkaz|Klávesové zkratky|
|-------------|------------------------|
|Přepnout na **vyberte** režimu|Ctrl+G, Gtrl+Q<br /><br /> S|
|Přepnout na **zvětšení** režimu|Ctrl+G, Ctrl+Z<br /><br /> Z|
|Přepnout na **Panoramování** režimu|Ctrl+G, Ctrl+P<br /><br /> K|
|Vybrat vše|Ctrl+A|
|Odstranit aktuální výběr|Odstranit|
|Zrušit aktuální výběr|Escape|
|Přiblížit|Ctrl + kolečko myši dopředu<br /><br /> Znaménko plus (+)|
|Oddálit|Ctrl kolečko myši zpětné<br /><br /> Znaménko minus (-)|
|Posouvání návrhovou plochu nahoru|Kolečko myši dozadu<br /><br /> PageDown|
|Posouvání návrhovou plochu dolů|Kolečko myši dopředu<br /><br /> PageUp|
|Posun vlevo na návrhovou plochu|Shift + kolečko myši dozadu<br /><br /> Kolečko myši doleva<br /><br /> SHIFT + lektora|
|Posun vpravo návrhové plochy|Shift + kolečko myši dopředu<br /><br /> Kolečko myši doprava<br /><br /> Shift + PageUp|
|Přesunout fokus klávesnice do jiného uzlu|Klávesy se šipkami|
|Vyberte uzel, který má právě fokus klávesnice (přidá do skupiny výběr uzlu)|SHIFT + MEZERNÍK|
|Přepnutí výběr uzlu, který má právě fokus klávesnice|Ctrl + mezerník|
|Přepněte aktuální výběr (pokud nejsou vybrány žádné uzly, vyberte uzel, který má právě fokus klávesnice)|MEZERNÍK|
|Aktuální výběr přesunout nahoru|Shift + šipka nahoru|
|Aktuální výběr přesunout dolů|Shift + šipka dolů|
|Aktuální výběr přesunout doleva.|Shift + šipka doleva|
|Přesunout aktuální výběr vpravo|Shift + šipka vpravo.|

## <a name="related-topics"></a>Související témata

|Název|Popis|
|-----------|-----------------|
|[Práce s 3D prostředky pro hry a aplikace](../designers/working-with-3-d-assets-for-games-and-apps.md)|Obsahuje přehled [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástroje, které můžete použít pro práci s textury a bitové kopie, 3D modely a shaderu účinky.|
|[Editor obrázků](../designers/image-editor.md)|Popisuje postup použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Editor obrázků pro práci s textury a bitové kopie.|
|[Editor modelů](../designers/model-editor.md)|Popisuje postup použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] modelu Editor pro práci s 3D modelů.|