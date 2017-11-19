---
title: Editor modelu | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.graphics.designer.3dscene
- vs.graphics.modelviewer
ms.assetid: 5edf1a30-9307-43c3-9b8b-831217be0104
caps.latest.revision: "36"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2b7176a0aed65a9595730247d857dc0c263dc0cb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="model-editor"></a>Editor modelů
Tento dokument popisuje, jak pracovat [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Editor modelu zobrazení, vytvoření a změna 3D modelů.  
  
 Editor modelů můžete použít k vytvoření základních 3D modelů od začátku nebo k zobrazení a úpravám složitějších 3D modelů, které byly vytvořeny pomocí plnohodnotných nástrojů pro 3D modelování. Editor modelů podporuje několik formátů 3D modelů, které jsou používány při vývoji aplikace v rozhraní DirectX.  
  
## <a name="supported-formats"></a>Podporované formáty  
 Editor modelů podporuje tyto formáty modelů:  
  
|Název formátu|Přípona souboru|Podporované operace (zobrazení, úpravy, vytváření)|  
|-----------------|--------------------|-------------------------------------------------|  
|Soubor AutoDesk FBX Interchange|.fbx|Zobrazení, úpravy, vytváření|  
|Soubor DAE standardu Collada|.dae|Zobrazení, úpravy (změny DAE standardu Collada jsou uloženy ve formátu FBX.)|  
|OBJ|.obj|Zobrazení, úpravy (změny souborů OBJ jsou uloženy ve formátu FBX.)|  
  
## <a name="getting-started"></a>Začínáme  
 Tato část popisuje postup přidání 3D modelu pro vaše [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektu a poskytuje základní informace, které potřebujete, abyste mohli začít.  
  
#### <a name="to-add-a-3-d-model-to-your-project"></a>Přidání 3D modelu do projektu  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro projekt, který chcete přidat do a potom vyberte **přidat**, **novou položku**.  
  
2.  V **přidat novou položku** dialogovém **nainstalovaná**, vyberte **grafiky**a potom vyberte **3D scény (.fbx)**.  
  
3.  Zadejte **název** souboru modelu a **umístění** kde se má vytvořit.  
  
4.  Vyberte **přidat** tlačítko.  
  
### <a name="axis-orientation"></a>Orientace osy  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]podporuje každých orientaci 3D osy a načte informace orientace osy z modelu formáty souborů, které ji podporují. Pokud není zadaný žádný orientace osy, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve výchozím nastavení používá pravou rukou souřadnicový systém. **Osy indikátor** se zobrazí aktuální orientace osy v pravém horním rohu na návrhovou plochu. Na **indikátor osy**, red představuje osy x, zelená představuje osy y a blue představuje osy z.  
  
### <a name="beginning-your-3-d-model"></a>Zahájení 3D modelu  
 V editoru modelu každý nový objekt začne vždy jako jednu ze základních tvarů 3D – nebo *primitiv*– které jsou integrovány do editoru modelu. Chcete-li vytvořit nové a jedinečné objekty, přidáte ke scéně primitiv a změníte jeho tvar úpravou vrcholů. U složitých tvarů přidáte další vrcholy pomocí vysunutí nebo dílčího dělení a následnou úpravou. Informace o tom, jak přidat primitivní objekt do vaší scény najdete v tématu [vytváření a import 3D objekty](#Adding3DObjects). Informace o tom, jak přidat další vrcholy k objektu, najdete v tématu [úprav objektů](#ModifyingObjects).  
  
## <a name="working-with-the-model-editor"></a>Práce s editorem modelů  
 Následující části popisují způsob použití editoru modelů pro práci s 3D modely.  
  
### <a name="model-editor-toolbars"></a>Panely nástrojů editoru modelů  
 Panely nástrojů Editoru modelů obsahují příkazy, které vám pomohou pracovat se 3D modely.  
  
 Příkazy, které ovlivňují stav Editor modelu jsou umístěny na **modelu Editor režimu** panelu nástrojů v hlavní [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] okno. Nástroje pro modelování a skriptované příkazy jsou umístěny na **modelu Editor** panelu nástrojů na návrhovou plochu Editor modelu.  
  
 Tady je **modelu Editor režimu** nástrojů:  
  
 ![Modální nástrojů modelu Viewer. ] (../designers/media/digit-mre-modal-toolbar.png "Číslice MRE modální nástrojů")  
  
 Tato tabulka popisuje položky na **modelu Editor režimu** nástrojů, které jsou uvedeny v pořadí, ve kterém se zobrazí zleva doprava.  
  
|Položka na panelu nástrojů|Popis|  
|------------------|-----------------|  
|**Vyberte**|Umožňuje výběr bodů, okrajů, ploch nebo objektů ve scéně podle aktivního režimu výběru.|  
|**Pan**|Umožňuje pohyb 3D scény relativně k rámu okna. K posouvání vyberte bod ve scéně a pohybujte jím.<br /><br /> V **vyberte** režimu, stiskněte a podržte klávesu Ctrl k aktivaci **Panoramování** dočasně režimu.|  
|**Přiblížení**|Umožňuje zobrazení více či méně detailů scény relativně k rámu okna. V **zvětšení** režimu, vyberte bod v scény a pak přesunout doprava dolů na přiblížit nebo doleva nebo až přiblížení out.<br /><br /> V **vyberte** režimu, můžete zvětšit nebo zmenšit pomocí kolečka myši, stiskněte a podržte klávesu Ctrl.|  
|**Obíhání**|Umístí zobrazení na kruhovou dráhu okolo vybraného objektu. Pokud není vybrán žádný objekt, středem trasy je počátek scény. **Poznámka:** tento režim neobsahuje žádné ovlivňuje při **pravoúhlé** projekce je povoleno.|  
|**Místní World**|Pokud je tato položka povolena, transformace na vybraném objektu pobíhají v globálním prostoru. Jinak transformace na vybraném objektu probíhají v místním prostoru.|  
|**Pivot režimu**|Tato položka je povoleno, transformace mít vliv na umístění a orientaci *bodu otáčení* vybraného objektu (bodem pivot definuje center překlad, změny velikosti a oběh operací.) Transformace jinak ovlivní umístění a orientaci geometrie objektu ve vztahu k bodu otáčení.|  
|**Osy X zámku**|Omezuje manipulaci s objekty na ose x. Platí pouze při použití prostřední části pomůcky manipulátoru.|  
|**Osy Y zámku**|Omezuje manipulaci s objekty na ose y. Platí pouze při použití prostřední části pomůcky manipulátoru.|  
|**Zámek Z osy**|Omezuje manipulaci s objekty na ose z. Platí pouze při použití prostřední části pomůcky manipulátoru.|  
|**Objekt rámce**|Orámuje vybraný objekt, aby se nacházel ve středu zobrazení.|  
|**Zobrazení**|Nastaví orientaci zobrazení. Zde jsou dostupné orientace:<br /><br /> **Přední**<br /> Umístí zobrazení před scénu.<br /><br /> **Zpět**<br /> Umístí zobrazení za scénu.<br /><br /> **Vlevo**<br /> Umístí zobrazení vlevo od scény.<br /><br /> **Vpravo**<br /> Umístí zobrazení vpravo od scény.<br /><br /> **Horní**<br /> Umístí zobrazení nad scénu.<br /><br /> **Dolní**<br /> Umístí zobrazení pod scénu. **Poznámka:** Toto je jediným způsobem, jak změnit směr zobrazení při **pravoúhlé** projekce je povoleno.|  
|**Projekce**|Nastaví druh projekce použitý pro vykreslení scény. Zde jsou dostupné projekce:<br /><br /> **Perspektivy**<br /> V perspektivní projekci se objekty více vzdálené od bodu pozorování zdají být menší a sbíhají se k jednomu vzdálenému bodu.<br /><br /> **Pravoúhlé**<br /> V pravoúhlé projekci se objekty jeví jako stejně velké bez ohledu na jejich vzdálenost od bodu pozorování. Není zobrazena žádná konvergence. Když **pravoúhlé** projekce povoleno, nelze použít **obíhání** režimu k umístění zobrazení.|  
|**Styl kreslení**|Nastaví, jak jsou objekty ve scéně vykresleny. Zde jsou dostupné styly:<br /><br /> **Přenosová rámce**<br /> Je-li tato možnost povolena, objekty jsou vykresleny jako objekty wireframe.<br /><br /> **Overdraw**<br /> Pokud je tato možnost povolena, objekty jsou vykreslovány pomocí doplňkového prolnutí. Tuto možnost můžete použít k zobrazení rozsahu překreslování, ke kterému dochází na scéně.<br /><br /> **Ploché stínované**<br /> Je-li tato možnost povolena, objekty jsou vykreslovány základním světelným modelem s plochým stínem. Tuto možnost můžete použít k jednoduššímu zobrazení ploch objektu.<br /><br /> Pokud žádná z těchto možností není povolena, každý objekt je vykreslen pomocí materiálu, který je na něj použit.|  
|**Režim vykreslování v reálném čase**|Pokud je povolena v reálném čase vykreslování, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ho překreslí na návrhovou plochu, i když je provedena žádná akce uživatele. Tento režim je užitečný při práci se shadery, které se mění v průběhu času.|  
|**Přepnutí mřížky**|Po povolení této položky se zobrazí mřížka. Jinak se mřížka nezobrazí.|  
|**Sada nástrojů**|Případně zobrazí nebo skryje **sada nástrojů**.|  
|**Osnova dokumentu**|Případně zobrazí nebo skryje **Osnova dokumentu** okno.|  
|**Vlastnosti**|Případně zobrazí nebo skryje **vlastnosti** okno.|  
|**Upřesnit**|Obsahuje pokročilé příkazy a možnosti.<br /><br /> **Moduly grafiky**<br /><br /> **Vykreslení s D3D11**<br /> Používá rozhraní Direct3D 11 k vykreslení plochy návrhu editoru modelů.<br /><br /> **Vykreslení s D3D11WARP**<br /> Používá rozhraní Direct3D 11 WARP (Windows Advanced Rasterization Platform) k vykreslení plochy návrhu editoru modelů.<br /><br /> **Scény správy**<br /><br /> **Import**<br /> Importuje objekty z jiného souboru 3D modelu do aktuální scény.<br /><br /> **Připojení k nadřazené**<br /> Určí první z více vybraných objektů jako nadřazený objekt zbývajících vybraných objektů.<br /><br /> **Odpojení od nadřazeného**<br /> Odpojí vybraný objekt od nadřazeného objektu. Vybraný objekt stane *kořenový objekt* v scény. Kořenový objekt nemá nadřazený objekt.<br /><br /> **Vytvoření skupiny**<br /> Seskupí vybrané objekty na stejné úrovni.<br /><br /> **Merge – objekty**<br /> Kombinuje vybrané objekty do jednoho objektu.<br /><br /> **Vytvořit nový objekt z výběru mnohoúhelníku**<br /> Odebere vybrané plochy z aktuálního objektu a přidá na scénu nový objekt, který tyto plochy obsahuje.<br /><br /> **Nástroje**<br /><br /> **Překlopit zrušení mnohoúhelníku**<br /> Převrátí vybrané mnohoúhelníky tak, že jejich pořadí obtáčení a normála povrchu se převrátí.<br /><br /> **Odeberte všechny animace**<br /> Odebere data animace z objektů.<br /><br /> **Triangulovat**<br /> Převede vybraný objekt na trojúhelníky.<br /><br /> **Zobrazení**<br /><br /> Odstranění odvrácených stran<br /> Povolí nebo zakáže odstranění odvrácených stran.<br /><br /> **Obnovovací frekvence**<br /> Zobrazí frekvenci snímků v pravém horním rohu plochy návrhu. Frekvence snímků je počet snímků, které jsou zpracovány za sekundu.<br /><br /> Tato možnost je užitečná, když povolíte **režimu vykreslování v reálném čase** možnost.<br /><br /> **Zobrazit vše**<br /> Zobrazí všechny objekty ve scéně. To obnoví **Hidden** vlastnosti každého objektu na **False**.<br /><br /> **Zobrazit vzhled normál**<br /> Zobrazí normály pro každou plochu.<br /><br /> **Zobrazit chybí materiály**<br /> Zobrazí speciální texturu u objektů, ke kterým není přiřazen materiál.<br /><br /> **Zobrazit Pivot**<br /> Povolí nebo zakáže zobrazení značky na osách 3D v bodě otáčení aktivního výběru.<br /><br /> **Zobrazit zástupný symbol uzly**<br /> Zobrazí zástupné uzly. Zástupný uzel je vytvořen při seskupení objektů.<br /><br /> **Zobrazit kolmice**<br /> Zobrazí normálu každého vrcholu. **Tip:** můžete **skripty** tlačítko Poslední skript znovu spustit.|  
  
 Tady je **modelu Editor** nástrojů:  
  
 ![Panel nástrojů prohlížeče modelu](../designers/media/digit-mre-toolbar.png "číslice-MRE-panelu nástrojů")  
  
 Následující tabulka popisuje položky na **modelu Editor** nástrojů, které jsou uvedeny v pořadí, ve kterém se zobrazí shora dolů.  
  
|Položka na panelu nástrojů|Popis|  
|------------------|-----------------|  
|**Převede**|Posune výběr.|  
|**Škálování**|Změní velikost výběru.|  
|**Otočit**|Otočí výběr.|  
|**Vyberte bod**|Nastaví **režim výběru** vyberte jednotlivé body na objekt.|  
|**Vybrat okraj**|Nastaví **režim výběru** vybrat okraj (řádek mezi dvě vrcholy) na objekt.|  
|**Vyberte vzhled**|Nastaví **režim výběru** vyberte řez objektu.|  
|**Vyberte objekt**|Nastaví **režim výběru** vyberte celý objekt.|  
|**Tvarování**|Vytvoří další plochu a připojí ji k vybrané ploše.|  
|**Rozdělit**|Rozdělí každou vybranou plochu na více ploch. Pro vytvoření nových ploch se přidají nové vrcholy – jeden uprostřed původní plochy a jeden uprostřed každé hrany – které jsou poté spojeny s původními vrcholy. Počet přidaných ploch se rovná počtu hran původní plochy.|  
  
### <a name="controlling-the-view"></a>Ovládání zobrazení  
 3D scéna je vykreslena podle zobrazení, které si lze představit jako virtuální fotoaparát obsahující umístění a orientaci. Chcete-li změnit umístění a orientace, použijte ovládací prvky zobrazení na **modelu Editor režimu** panelu nástrojů.  
  
 Následující tabulka popisuje primární ovládací prvky zobrazení.  
  
|Ovládací prvek zobrazení|Popis|  
|------------------|-----------------|  
|**Pan**|Umožňuje pohyb 3D scény relativně k rámu okna. K posouvání vyberte bod ve scéně a pohybujte jím.<br /><br /> V **vyberte** režimu, stiskněte a podržte klávesu Ctrl k aktivaci **Panoramování** dočasně režimu.|  
|**Přiblížení**|Umožňuje zobrazení více či méně detailů scény relativně k rámu okna. V **zvětšení** režimu, vyberte bod v scény a pak přesunout doprava dolů na přiblížit nebo doleva nebo až přiblížení out.<br /><br /> V **vyberte** režimu, můžete zvětšit nebo zmenšit pomocí kolečka myši, stiskněte a podržte klávesu Ctrl.|  
|**Obíhání**|Umístí zobrazení na kruhovou dráhu okolo vybraného objektu. Pokud není vybrán žádný objekt, středem trasy je počátek scény. **Poznámka:** tento režim neobsahuje žádné ovlivňuje při **pravoúhlé** projekce je povoleno.|  
|**Objekt rámce**|Orámuje vybraný objekt, aby se nacházel ve středu zobrazení.|  
  
 Zobrazení je vytvořeno virtuálním fotoaparátem, ale je také definováno projekcí. Projekce definuje, jaké tvary a objekty v zobrazení jsou přeloženy do pixelů na povrchu návrhu. Na **modelu Editor** nástrojů, můžete zvolit buď **perspektivy** nebo **pravoúhlé** projekce.  
  
|Projekce|Popis|  
|----------------|-----------------|  
|**Perspektivy**|V perspektivní projekci se objekty více vzdálené od bodu pozorování zdají být menší a sbíhají se k jednomu vzdálenému bodu.|  
|**Pravoúhlé**|V pravoúhlé projekci se objekty jeví jako stejně velké bez ohledu na jejich vzdálenost od bodu pozorování. Není zobrazena žádná konvergence. Když **pravoúhlé** projekce povoleno, nelze použít **obíhání** režimu na pozici zobrazení libovolně.|  
  
 Může být užitečné zobrazit 3D scénu ze známého umístění a úhlu, například když chcete porovnat dvě podobné scény. V tomto scénáři editor modelů poskytuje několik předdefinovaných zobrazení. Používání předdefinovaných zobrazení, v **modelu Editor režimu** nástrojů vyberte **zobrazení**a potom zvolte předdefinovaných zobrazení, které chcete – přední zpět, vlevo, vpravo, nahoru nebo dolů. V těchto zobrazeních virtuální kamera snímá přímo počátek scény. Například pokud se rozhodnete **zobrazení horní**, kamera virtuální vypadá v původu scény z přímo nad ním.  
  
### <a name="viewing-additional-geometry-details"></a>Zobrazení dalších podrobností o geometrii  
 Pro lepší pochopení 3D objektu nebo scény můžete zobrazit další podrobnosti geometrie, jako jsou normály pro každý vrchol, normály pro každou plochu, body otáčení aktivního výběru a další podrobnosti. Chcete povolit nebo zakázat, na **modelu Editor** nástrojů vyberte **skripty**, **zobrazení**a potom vyberte ten, který chcete.  
  
###  <a name="Adding3DObjects"></a>Vytvoření a import 3D objekty  
 Přidání předdefinovaný tvar 3D scény, v **sada nástrojů**, vyberte příslušnou možnost, chcete a poté ho přesuňte na plochu návrháře. Nové tvary jsou umístěny v počátku scény. Nabízí Editor modelu sedm tvarů: **kuželový**, **datové krychle**, **cylindr**, **disk**, **roviny**,  **Oblasti**, a **Teapot**.  
  
 K importu 3D objekt ze souboru, na **modelu Editor** nástrojů vyberte **Upřesnit**, **scény správu**, **importovat**a pak zadejte soubor, který chcete importovat.  
  
### <a name="transforming-objects"></a>Transformace objektů  
 Můžete *transformace* objekt změnou jeho **otočení**, **škálování**, a **překlad** vlastnosti. *Otočení* orientuje objekt použitím následných otáčení kolem osy x, osy y a osy z definované jeho pivot bodu. Každá specifikace otočení má tři komponenty – x, y a z v uvedeném pořadí – které jsou zadány ve stupních. **Škálování** změní objekt roztáhnout zadaný faktorem podél os jeden nebo více na svůj bod pivot střed. *Překlad* vyhledá objekt v prostorovém 3 prostoru relativně k nadřazenému místo jeho pivot bodu.  
  
 Objekt můžete transformovat pomocí nástrojů pro modelování nebo nastavením vlastností.  
  
##### <a name="to-transform-an-object-by-using-modeling-tools"></a>Transformace objektu pomocí nástrojů pro modelování  
  
1.  V **vyberte** režimu, vyberte objekt, který chcete transformace. Překrytí wireframe udává, že objekt je vybrán.  
  
2.  Na **modelu Editor** nástrojů, vyberte **přeložit**, **škálování**, nebo **otočit** nástroj. Pro vybraný objekt se zobrazí otočení, změna velikosti nebo manipulátor otočení.  
  
3.  K provedení transformace použijte manipulátor. Pro transformace otočení a změny velikosti je manipulátor indikátorem osy. Najednou můžete změnit jen jednu osu nebo všechny osy současně pomocí bílé krychle ve středu indikátoru. Pro otáčení je manipulátor koule tvořená kruhy s kódováním barev, které odpovídají osám x (červená), y (zelená) a z (modrá). K vytvoření požadovaného otočení je třeba změnit každou osu jednotlivě.  
  
##### <a name="to-transform-an-object-by-setting-its-properties"></a>Transformace objektu nastavením jeho vlastností  
  
1.  V **vyberte** režimu, vyberte objekt, který chcete transformace. Překrytí wireframe udává, že objekt je vybrán.  
  
2.  V **vlastnosti** okno, zadejte hodnoty pro **otočení**, **škálování**, a **překlad** vlastnosti.  
  
    > [!IMPORTANT]
    >  Pro **otočení** vlastnost určení stupně otočení kolem každé tři osy. Otáčení probíhá postupně. Ujistěte se tedy, že je otáčení správně naplánováno nejprve podle osy x, poté y a poté z.  
  
 Použitím nástrojů modelování můžete vytvářet transformace rychle, ale nikoli přesně. Nastavením vlastností objektu můžete určit transformace přesně, ale nikoli rychle. Doporučujeme použít nástroje modelování tak, abyste se dostali „dostatečně blízko“ k požadovaným transformacím, a poté doladit hodnoty vlastností.  
  
 Pokud nechcete použít manipulátory, můžete povolit režim volného tvaru. Na **modelu Editor** nástrojů vyberte **skripty**, **nástroje**, **manipulaci libovolného tvaru s** povolit (nebo zakázat) režim volného tvaru. V režimu volného tvaru můžete začít manipulaci v libovolném bodě plochy návrhu namísto bodu manipulátoru. V režimu volného tvaru můžete omezit změny některých os zamčením těch, které nechcete změnit. Na **modelu Editor režimu** nástrojů zvolit libovolnou kombinaci **zámku X**, **zámku Y**, a **zámku Z** tlačítka.  
  
 Může být výhodné pracovat s objekty pomocí přichycení k mřížce. Na **modelu Editor režimu** nástrojů vyberte **Snap** povolit (nebo zakázat) přichycení k mřížce. Pokud je povolena možnost přichycení k mřížce, jsou přednastaveny omezené přírůstky pro posunutí, otočení a změnu velikosti.  
  
### <a name="working-with-the-pivot-point"></a>Práce s bodem otáčení  
 Bod otáčení objektu definuje jeho střed rotace a změnu měřítka. Bod otáčení objektu můžete změnit, abyste změnili způsob, jak je objekt ovlivněn transformacemi rotace a měřítka. Na **modelu Editor režimu** nástrojů vyberte **Pivot režimu** do režimu pivot povolit (nebo zakázáno). Pokud je povolen režim pivotu, zobrazí se v bodu otáčení vybraného projektu indikátor malé osy. Pak můžete použít **překlad** a **otočení** nástrojů k manipulaci s bodem pivot.  
  
 Ukázka, která ukazuje, jak používat bod pivot, najdete v části [postupy: úprava bodu Pivot 3D modelu](../designers/how-to-modify-the-pivot-point-of-a-3-d-model.md).  
  
### <a name="world-and-local-modes"></a>Globální a místní režimy  
 Překlad a otočení může dojít v buď místní systém souřadnic (nebo *místní rámce z odkaz*) objekt, nebo v souřadnicový systém na světě (nebo *world rámce z – reference*). Otáčení globálního referenčního snímku je nezávislé na otáčení objektu. Výchozí nastavení je místní režim. Chcete povolit (nebo zakázat) world režimu, na **modelu Editor režimu** nástrojů, vyberte **WorldLocal** tlačítko.  
  
###  <a name="ModifyingObjects"></a>Změny objektů  
 Tvar 3D objektu můžete změnit přesunutím nebo odstraněním jeho vrcholů, hran a ploch. Editor modelu je ve výchozím nastavení v *objekt režimu*, takže můžete vybrat a transformace celé objekty. Pokud chcete vybrat body, okraje nebo plochy, zvolte příslušný režim výběru. Na **modelu Editor režimu** nástrojů vyberte **režimy výběru**a potom zvolte režim, který chcete.  
  
 Vyloučením nebo dělením můžete vytvořit další vrcholy. Vyloučení duplikuje vrcholy plochy (koplanární sadu vrcholů), které zůstávají spojeny duplikovanými vrcholy. Dělení přidá vrcholy pro vytvoření několika ploch tam, kde byla dříve jen jedna. Pro vytvoření nových ploch se přidají nové vrcholy – jeden uprostřed původní plochy a jeden uprostřed každé hrany – které jsou poté spojeny s původními vrcholy. Počet přidaných ploch se rovná počtu hran původní plochy. V obou případech můžete nové vrcholy posunout, otočit a změnit jejich velikost, čímž změníte geometrii celého objektu.  
  
##### <a name="to-extrude-a-face-from-an-object"></a>Vyloučení plochy z objektu  
  
1.  V režimu výběru plochy vyberte plochu, kterou chcete vyloučit.  
  
2.  Na **modelu Editor** nástrojů vyberte **skripty**, **nástroje**, **vytlačení**.  
  
##### <a name="to-subdivide-faces"></a>Rozdělení ploch  
  
1.  V režimu výběru plochy vyberte plochy, které chcete rozdělit. Protože rozdělení vytváří nová data hrany, rozdělení všech ploch současně poskytuje konzistentnější výsledky, když plochy sousedí.  
  
2.  Na **modelu Editor** nástrojů vyberte **skripty**, **nástroje**, **Subdivide**.  
  
 Můžete také triangulovat plochy, sloučit objekty a převést mnohoúhelníkové výběry do nových objektů. Triangulace vytvoří další hrany, takže jiné než trojúhelníkové plochy jsou převedeny na optimální počet trojúhelníků; neposkytuje však další podrobnosti o geometrii. Slučování kombinuje vybrané objekty do jednoho objektu. Nové objekty je možné vytvořit pomocí mnohoúhelníkového výběru.  
  
##### <a name="to-triangulate-a-face"></a>Postup triangulace plochy  
  
1.  V režimu výběru plochy vyberte plochu, kterou chcete triangulovat.  
  
2.  Na **modelu Editor** nástrojů vyberte **skripty**, **nástroje**, **Triangulate**.  
  
##### <a name="to-merge-objects"></a>Sloučení objektů  
  
1.  V režimu výběru objektů vyberte objekty, které chcete sloučit.  
  
2.  Na **modelu Editor** nástrojů vyberte **skripty**, **nástroje**, **sloučení objekty**.  
  
##### <a name="to-create-an-object-from-a-polygon-selection"></a>Vytvoření objektu z mnohoúhelníkového výběru  
  
1.  V režimu výběru plochy vyberte plochy, ze kterých chcete vytvořit nový objekt.  
  
2.  Na **modelu Editor** nástrojů vyberte **skripty**, **nástroje**, **vytvořit nový objekt z výběru mnohoúhelníku**.  
  
### <a name="working-with-materials-and-shaders"></a>Práce s materiály a shadery  
 Vzhled objektu je určen interakcí osvětlení scény a materiálu objektu. Materiály jsou definovány vlastnostmi, které popisují, jak povrch reaguje na různé typy světla, a programem shader, který vypočítá konečnou barvu každého obrazového bodu na povrchu objektu na základě informací o osvětlení, map textur, map normál a dalších dat.  
  
 Editor modelů poskytuje tyto výchozí materiály:  
  
|Materiál|Popis|  
|--------------|-----------------|  
|Ztemnit|Vykreslí povrch bez jakéhokoli simulovaného světla.|  
|Lambert|Vykreslí povrch se simulovaným osvětlením okolí a difúzním světlem.|  
|Phong|Vykreslí povrch se simulovaným osvětlením okolí, difúzním světlem a se zrcadlovými světly.|  
  
 Každý z těchto materiálů použije jednu texturu na povrch objektu. Můžete nastavit různé textury pro každý objekt, který používá materiál.  
  
 Pokud chcete upravit, jak daný objekt reaguje na různé zdroje světla ve scéně, můžete změnit vlastnosti osvětlení materiálu nezávisle na jiných objektech, které materiál používají. Tato tabulka popisuje běžné vlastnosti osvětlení:  
  
|Vlastnost osvětlení|Popis|  
|-----------------------|-----------------|  
|Okolní|Popisuje, jakým způsobem je povrch ovlivněn okolním osvětlením.|  
|Rozptýlené|Popisuje, jakým způsobem je povrch ovlivněn směrovými a bodovými světly.|  
|Zářivé|Popisuje, jak povrch vyzařuje světlo, nezávisle na ostatním osvětlení.|  
|Odlesk|Popisuje, jakým způsobem povrch odráží směrová a bodová světla.|  
|Síla odlesku|Popisuje šířku a intenzitu odlesků.|  
  
 V závislosti na tom, co materiál podporuje, můžete změnit jeho vlastnosti osvětlení, textury a další data. V **vyberte** režimu, vyberte objekt, jehož materiály, které chcete změnit, a potom v **vlastnosti** změňte **MaterialAmbient**,  **MaterialDiffuse**, **MaterialEmissive**, **MaterialSpecular**, **MaterialSpecularPower**, nebo jiné dostupné vlastnosti. Materiálu můžou zpřístupnit až osm textury, jehož vlastnosti jsou pojmenované postupně z **Texture1** k **Texture8**.  
  
 K odebrání všech materiály objekt, na **modelu Editor** nástrojů vyberte **skripty**, **materiály**, **odebrat materiály**.  
  
 Můžete použít **shaderu Návrhář** vytvořit vlastní shaderu materiály, které můžete použít pro objekty na vaše 3D scény. Informace o tom, jak vytvořit vlastní shaderu materiály najdete v tématu [shaderu Návrhář](../designers/shader-designer.md). Informace o tom, jak používat vlastní shaderu materiálech k objektu, najdete v tématu [postupy: použití shaderu 3D modelu](../designers/how-to-apply-a-shader-to-a-3-d-model.md).  
  
### <a name="scene-management"></a>Správa scény  
 Scény můžete spravovat jako hierarchii objektů. Pokud je v hierarchii uspořádáno více objektů, jakékoli posunutí, změna velikosti nebo otočení nadřazeného uzlu ovlivní také podřízené objekty. To je užitečné, když chcete vytvořit složité objekty nebo scény z více základních objektů.  
  
 Můžete použít **Osnova dokumentu** okna zobrazení hierarchie scény a vyberte uzly scény. Když vyberete uzel v osnově, můžete použít **vlastnosti** okna upravit její vlastnosti.  
  
 Hierarchii objektů můžete vytvořit buď tím, že jeden z nich stanovíte nadřazený ostatním, nebo jejich seskupením společně jako uzly na stejné úrovni zástupného symbolu, které fungují jako nadřazené.  
  
##### <a name="to-create-a-hierarchy-that-has-a-parent-object"></a>Vytvoření hierarchie, která má nadřazený objekt  
  
1.  V **vyberte** režim, vyberte dvě nebo více objektů. První, který vyberete, bude nadřazený objekt.  
  
2.  Na **modelu Editor** nástrojů vyberte **skripty**, **scény správu**, **připojení k nadřazené**.  
  
##### <a name="to-create-a-hierarchy-of-sibling-objects"></a>Vytvoření hierarchie objektů na stejné úrovni  
  
1.  V **vyberte** režim, vyberte dvě nebo více objektů. Vytvoří se zástupný objekt, který se stane jejich nadřazeným objektem.  
  
2.  Na **modelu Editor** nástrojů vyberte **skripty**, **scény správu**, **vytvořit skupinu**.  
  
 Editor modelů používá k identifikaci prvního vybraného objektu, který se stane nadřazeným, bílý objekt wireframe. Ostatní objekty ve výběru mají modrý objekt wireframe. Ve výchozím nastavení nejsou uzly zástupných symbolů zobrazeny. K zobrazení uzlů zástupného symbolu, na **modelu Editor** nástrojů vyberte **skripty**, **scény správu**, **zobrazit zástupný symbol uzly**. S uzly zástupných symbolů můžete pracovat stejně jako při práci s objekty bez zástupných symbolů.  
  
 Odebrat přidružení nadřazený podřízený mezi dvěma objekty, vyberte podřízený objekt a poté na **modelu Editor** nástrojů vyberte **skripty**, **scény správy**, **Odpojení od nadřazeného**. Pokud odpojíte od podřízeného objektu nadřazený, podřízený objekt se stane kořenovým objektem scény.  
  
## <a name="keyboard-shortcuts"></a>Klávesové zkratky  
  
|Příkaz|Klávesové zkratky|  
|-------------|------------------------|  
|Přepnout na **vyberte** režimu|Ctrl+G, Gtrl+Q<br /><br /> S|  
|Přepnout na **zvětšení** režimu|Ctrl+G, Ctrl+Z<br /><br /> Z|  
|Přepnout na **Panoramování** režimu|Ctrl+G, Ctrl+P<br /><br /> K|  
|Vybrat vše|Ctrl+A|  
|Odstranit aktuální výběr|Odstranit|  
|Zrušit aktuální výběr|Escape|  
|Přiblížit|Kolečko myši dopředu<br /><br /> Ctrl + kolečko myši dopředu<br /><br /> Shift + kolečko myši dopředu<br /><br /> Ctrl+PageUp<br /><br /> Znaménko plus (+)|  
|Oddálit|Kolečko myši dozadu<br /><br /> Ctrl + kolečko myši dozadu<br /><br /> Shift + kolečko myši dozadu<br /><br /> Ctrl+PageDown<br /><br /> Znaménko minus (-)|  
|Posunout kameru nahoru|PageDown|  
|Posunout kameru dolů|PageUp|  
|Posunout kameru vlevo|Kolečko myši doleva<br /><br /> Ctrl+PageDown|  
|Posunout kameru vpravo|Kolečko myši doprava<br /><br /> Ctrl+PageDown|  
|Zobrazit horní stranu modelu|Ctrl+L, Ctrl+T<br /><br /> T|  
|Zobrazit spodní stranu modelu|Ctrl+L, Ctrl+U|  
|Zobrazit levou stranu modelu|Ctrl+L, Ctrl+L|  
|Zobrazit pravou stranu modelu|Ctrl+L, Ctrl+R|  
|Zobrazit čelní stranu modelu|Ctrl+L, Ctrl+F|  
|Zobrazit zadní stranu modelu|Ctrl+L, Ctrl+B|  
|Orámovat objekt v okně|F|  
|Přepnout režim wireframe|Ctrl+L, Ctrl+W|  
|Přepnout přichycení k mřížce|Ctrl+G, Ctrl+N|  
|Přepnout režim pivotu|Ctrl+G, Ctrl+V|  
|Přepnout omezení osy x|Ctrl+L, Ctrl+X|  
|Přepnout omezení osy y|Ctrl+L, Ctrl+Y|  
|Přepnout omezení osy z|Ctrl+L, Ctrl+Z|  
|Přepnout do režimu posunutí|Ctrl+G, Ctrl+W<br /><br /> W|  
|Přepnout do režimu měřítka|Ctrl+G, Ctrl+E<br /><br /> E|  
|Přepnout do režimu otočení|Ctrl+G, Ctrl+R<br /><br /> R|  
|Přepnout do režimu výběru bodu|Ctrl+L, Ctrl+1|  
|Přepnout do režimu výběru okrajů|Ctrl+L, Ctrl+2|  
|Přepnout do režimu výběru ploch|Ctrl+L, Ctrl+3|  
|Přepnout do režimu výběru objektů|Ctrl+L, Ctrl+4|  
|Přepnout do režimu (kamera) orbit|Ctrl+G, Ctrl+O|  
|Vybrat další objekt na scéně|Tabulátor|  
|Vybrat předchozí objekt na scéně|Shift+Tab|  
|Manipulovat s vybraným objektem na základě aktuálního nástroje|Klávesy se šipkami|  
|Deaktivovat aktuální manipulátor|Q|  
|Otočit kameru|Alt + přetažení levým tlačítkem myši|  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Práce s 3D prostředky pro hry a aplikace](../designers/working-with-3-d-assets-for-games-and-apps.md)|Obsahuje přehled [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástroje, které můžete použít pro práci s prostředky grafiky například textury a bitové kopie, 3D modely a shaderu účinky.|  
|[Editor obrázků](../designers/image-editor.md)|Popisuje postup použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Editor obrázků pro práci s textury a bitové kopie.|  
|[Návrhář shaderu](../designers/shader-designer.md)|Popisuje postup použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] shaderu Designer pro práci s shadery.|