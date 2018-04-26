---
title: 'Návod: Vytvoření realistické 3D kulečníkové míč'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: af8eb0f3-bf6a-4d1c-ab47-dcd88ab04efa
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4ced3059b516c7285d525666a69d2c63a654a83a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-create-a-realistic-3d-billiard-ball"></a>Návod: Vytvoření realistické 3D kulečníkové míč

Tento návod ukazuje, jak vytvořit realistické 3D kulečníkové míč pomocí návrháře shaderu a Editor obrázků v sadě Visual Studio. 3D vzhled míč kulečníkové je dosáhnout kombinací několik technik shaderu s prostředky vhodné struktury.

## <a name="prerequisites"></a>Požadavky

Potřebujete následující součásti a dovednosti pro dokončení tohoto názorného postupu:

-   Nástroj pro ty textury do datové krychle mapy, jako je například nástroj Texture DirectX, který je součástí 2010 června DirectX SDK.

-   Znalosti s Editor obrázků v sadě Visual Studio.

-   Znalost návrháře shaderu v sadě Visual Studio.

## <a name="create-the-basic-appearance-with-shape-and-texture"></a>Vytvořte základní vzhled s tvar a textury

V počítači grafiky většinu – základní prvky vzhled jsou tvar a barvy. V počítači simulaci je běžné využívá 3D model, který představuje tvar reálného objektu. Barva podrobností se potom použije na povrch modelu pomocí mapy textury.

Obvykle možná budete muset požádat umělcem pro vytvoření 3D modelu, který můžete použít, ale protože kulečníkové míč je běžné tvar (oblasti), návrháře shaderu již vhodný model součástí.

Oblasti je výchozí tvar preview v Návrháři shaderu; Pokud aktuálně používáte jiný obrazce zobrazte náhled vašeho shaderu, přepněte zpět do oblasti.

### <a name="to-preview-the-shader-by-using-a-sphere"></a>Zobrazte náhled shaderu pomocí oblasti

-   Na panelu nástrojů návrháře shaderu zvolte **Preview s oblasti.**

 V dalším kroku vytvoříte program shaderu, který se týká texturou modelu, ale nejdřív je nutné vytvořit texture, který můžete použít. Tento návod ukazuje, jak vytvořit textury pomocí editoru bitovou kopii, která je součástí sady Visual Studio, ale můžete použít všechny bitové kopie editor, který můžete uložit textury vhodné formát.

 Ujistěte se, že **vlastnosti** okno a **sada nástrojů** jsou zobrazeny.

### <a name="to-create-a-billiard-ball-texture-by-using-the-image-editor"></a>K vytvoření texturou míč kulečníkové pomocí editoru obrázků

1.  Vytvořte texture pro práci s. Informace o tom, jak do projektu přidejte texturou, najdete v části Začínáme v [Editor obrázků](../designers/image-editor.md).

2.  Nastavit velikost obrázku tak, aby jeho šířka dvakrát výšku; To je nutné kvůli způsobem, že texturou mapována na kulovým prostor míč kulečníkové. Ke změně velikosti obrázku se v **vlastnosti** okno, zadejte nové hodnoty pro **šířka** a **výška** vlastnosti. Například nastavte šířku a výšku na 256 512.

3.  Zakreslit texture pro míč kulečníkové, přičemž mějte na tom, jak je texturou mapovány na oblasti.

     Textury by měl vypadat podobně jako tento:

     ![Texture pro míč kulečníkové](../designers/media/gfx_shader_demo_billiard_art_ball_texture.png "gfx_shader_demo_billiard_art_ball_texture")

4.  Volitelně můžete chtít snížit požadavky na úložiště z této texture. Můžete to udělat snížením šířku texture tak, aby odpovídala jeho výšku. To komprimaci texture podél šířku, ale vzhledem ke způsobu, že textury je mapována na oblast, bude rozšířena, při vykreslení míč kulečníkové. Po změně velikosti, textury by měl vypadat podobně jako tento:

     ![Texture kulečníkové komprimované do čtverce](../designers/media/gfx_shader_demo_billiard_art_ball_texture_square.png "gfx_shader_demo_billiard_art_ball_texture_square")

 Nyní můžete vytvořit shaderu, který se týká tato texture modelu.

### <a name="to-create-a-basic-texture-shader"></a>Chcete-li vytvořit základní texture shaderu

1.  Vytvořte DGSL shaderu pro práci s. Informace o tom, jak do projektu přidejte shaderu DGSL, najdete v části Začínáme v [shaderu Návrhář](../designers/shader-designer.md).

     Ve výchozím nastavení graf shaderu vypadat třeba takto:

     ![Graf shaderu výchozí](../designers/media/gfx_shader_demo_billiard_step_0.png "gfx_shader_demo_billiard_step_0")

2.  Upravte výchozí shaderu tak, aby hodnota vzorku texture se vztahuje na aktuální pixelů. Graf shaderu by měl vypadat takto:

     ![Shaderu grafu, který se vztahuje k objektu texture](../designers/media/gfx_shader_demo_billiard_step_1.png "gfx_shader_demo_billiard_step_1")

3.  Použití textury, kterou jste vytvořili v předchozím postupu pomocí konfigurace vlastností texture. Nastavte hodnotu **Texture** vlastnost **ukázka Texture** uzlu **Texture1**a pak zadejte soubor textury pomocí **Filename**vlastnost **Texture1** skupina vlastností v okně Vlastnosti.

 Další informace o tom, jak používat textury ve vašem shaderu najdete v tématu [postupy: vytvoření základní shaderu Texture](../designers/how-to-create-a-basic-texture-shader.md).

 Vaše kulečníkové míč by teď měl vypadat podobně jako tento:

 ![Closeup míč texturou kulečníkové](../designers/media/gfx_shader_demo_.png "gfx_shader_demo_")

## <a name="create-depth-with-the-lambert-lighting-model"></a>Vytvoření hloubka s modelem osvětlení společnost Lambert

Zatím jste vytvořili snadno rozpoznatelný kulečníkové míč. Zobrazí se však ploché nebo nezajímavé – více jako obrázek Kreslený vtip kulečníkové míč než přesvědčivé repliky. Plochý vzhled výsledkem shaderu zneužívající vlastností prohlížeče, který se chová, jako by každý pixelů na povrch míč kulečníkové obdrží stejné množství světla.

 V praxi zobrazí se lehký nejjasnější na plochy, které přímo čelí zdroje světla a zobrazuje se méně jasně na plochy, které jsou v úhlu Kosý ke zdroji světla. To je proto energie v světla paprsky je distribuován do oblasti nejmenší prostor, jestliže plocha směřuje přímo ke zdroji světla. Jak se změní na povrchu směřující od zdroje světla, stejnou úroveň energie je distribuován do stále větší prostor oblast. Prostor, který otočená od zdroje světla obdrží žádné světla energie, výsledkem je zcela tmavý vzhled. Tato odchylky také průraznost na povrchu objektu je důležité vizuální upozornění, která pomáhá znamenat tvaru objektu; bez, zobrazí se ploché objektu.

 V počítači grafiky *osvětlení modely*– zjednodušená aproximace komplexní, skutečné osvětlení interakce – replikují vzhled reálného osvětlení. Model osvětlení společnost Lambert se množství diffusely reflektované světla liší na povrchu objektu jak je popsáno v předchozím odstavci. Model osvětlení společnost Lambert můžete přidat do vaší shaderu umožnit míč kulečníkové více přesvědčivé 3D vzhled.

### <a name="to-add-lambert-lighting-to-your-shader"></a>Přidání společnost Lambert osvětlení do vaší shaderu

-   Upravte vaše shaderu provádět úpravy hodnota vzorku texture společnost Lambert osvětlení hodnotou. Graf shaderu by měl vypadat takto:

     ![Graf shaderu s společnost Lambert osvětlení přidat](../designers/media/gfx_shader_demo_billiard_step_2.png "gfx_shader_demo_billiard_step_2")

-   Volitelně můžete upravit chování osvětlení nakonfigurováním **MaterialDiffuse** vlastnost shaderu grafu. Přístup k vlastnostem shaderu grafu, vyberte na prázdnou oblast na návrhovou plochu a vyhledejte vlastnost, která chcete pro přístup **vlastnosti** okno.

 Další informace o tom, jak používat společnost Lambert osvětlení ve vašem shaderu najdete v tématu [postupy: vytvoření základní shaderu společnost Lambert](../designers/how-to-create-a-basic-lambert-shader.md).

 S společnost Lambert osvětlení použít, vaše kulečníkové míč by měl vypadat podobně jako tento:

 ![Closeup míč texturou a po kulečníkové](../designers/media/gfx_shader_demo_billiard_ball_2.png "gfx_shader_demo_billiard_ball_2")

## <a name="enhance-the-basic-appearance-with-specular-highlights"></a>Vylepšení základní vzhled s zrcadlová světla

Model osvětlení společnost Lambert poskytuje smysl tvar a dimenze, která byla chybí v shaderu jen texture. Ale míč kulečníkové má stále poněkud obyčejný vzhled.

 Skutečné kulečníkové míč má obvykle lesklý dokončit, která odráží část světlý, která spadá na něm. Některé tohoto projeví světla má za následek zrcadlová světla, které simulovat odrážející vlastnosti prostor. V závislosti na vlastnosti dokončit může být označuje lokalizované nebo široký, velký nebo jemně. Tyto zrcadlová odrazů jsou modelovány pomocí vztah mezi zdroji světla, orientaci na povrch a pozice fotoaparát – zvýraznění je koncentrace při orientaci na povrch odráží ke zdroji světla přímo do fotoaparátu, a je méně intenzivní když je odraz méně SMB direct.

 Model osvětlení Phong založený na modelu osvětlení společnost Lambert zahrnout zrcadlová světla, jak je popsáno v předchozím odstavci. Model osvětlení Phong můžete přidat do vaší shaderu umožnit míč kulečníkové simulované dokončit, jejímž výsledkem zajímavějšího vzhled.

### <a name="to-add-specular-highlights-to-your-shader"></a>Přidání zrcadlová světla do vaší shaderu

1.  Upravte vaše shaderu zahrnout zrcadlová příspěvek pomocí sčítání prolnutí. Graf shaderu by měl vypadat takto:

     ![Graf shaderu s zrcadlová osvětlení přidat](../designers/media/gfx_shader_demo_billiard_step_3.png "gfx_shader_demo_billiard_step_3")

2.  Volitelně můžete upravit způsob, jakým zrcadlová zvýraznění chová nakonfigurováním vlastností zrcadlení (**MaterialSpecular** a **MaterialSpecularPower**) shaderu grafu. Přístup k vlastnosti shaderu grafu, zvolte na prázdnou oblast na návrhovou plochu a potom v **vlastnosti** okně najít vlastnost, která chcete získat přístup.

 Další informace o tom, jak používat zrcadlová světla ve vašem shaderu najdete v tématu [postupy: vytvoření základní shaderu Phong](../designers/how-to-create-a-basic-phong-shader.md).

 Zrcadlová zvýrazněné, použít, vaše kulečníkové míč by měl vypadat podobně jako tento:

 ![Přidat closeup míč kulečníkové s zrcadlová](../designers/media/gfx_shader_demo_billiard_ball_3.png "gfx_shader_demo_billiard_ball_3")

## <a name="create-a-sense-of-space-by-reflecting-the-environment"></a>Vytvořte si smysl místa odrážející prostředí

S zrcadlová světla použít vypadá poměrně přesvědčivé vaší kulečníkové míč. Je tu, správného tvaru, úlohy správné Malování a pravém dokončit. Je však stále jeden další technika, který bude vaše kulečníkové míč vypadat spíše jako součást své prostředí.

 Pokud si projdete skutečné kulečníkové míč úzce, uvidíte, že prostor lesklý není právě vykazovat zrcadlová světla, ale také faintly odráží bitové kopie na světě kolem něj. Tato reflexe můžete simulovat pomocí bitové kopie prostředí jako texturou a že ho propojíte s texture modelu vlastní určit konečné barva každý pixelů. V závislosti na druhu dokončit, které chcete, můžete kombinovat více nebo méně odraz texture společně s rest shaderu. Například shaderu, která simuluje vysoce odrážející prostor jako zrcadlení může použít pouze texture reflexe, ale shaderu, která simuluje více jemně reflexe, jako byl nalezen na míč kulečníkové může kombinovat jenom malou část odraz Hodnota Texture na spolupráci s ostatními shaderu výpočtu.

 Samozřejmě jenom u nelze použít bitovou kopii reflektované modelu stejným způsobem, že použijete mapy textury modelu. Pokud jste to udělali, by s míč kulečníkové přesunout odraz na světě, jako kdyby byly odraz připevněná k němu. Protože odraz mohou pocházet z libovolným směrem, budete potřebovat způsob, jak zadat hodnotu reflexe mapování pro všechny úhel a způsob, jak udržovat mapy reflexe zaměřené na konkrétní podle na světě. Splňovat tyto požadavky můžete použít zvláštní druh mapy textury – názvem *datové krychle mapy*– šesti textury uspořádané na formuláři postranní datové krychle, která poskytuje. Z uvnitř této datové krychle, můžete zadat odkaz vede libovolným směrem najít texture hodnotu. Pokud textury na každé straně datové krychle obsahovat bitových kopií prostředí, můžete simulovat žádné reflexe vzorkování správném umístění na povrchu datové krychle. Tím, zachovat datové krychle zarovnán na světě, získáte přesný odraz prostředí. Pokud chcete zjistit, kde se datové krychle odeberou, právě vypočítat odraz fotoaparát vector mimo prostor objektu a použít jej jako 3D texture souřadnice. Pomocí datové krychle map tímto způsobem je běžný postup, který se označuje jako *prostředí mapování*.

 Mapování prostředí poskytuje efektivní sblížení skutečné odrazů, jak je popsáno v předchozích odstavcích. Do vaší shaderu umožnit míč kulečníkové, které simulované dokončit, která vytváří míč kulečníkové zdá se, že další založena scény můžete přizpůsobte odrazů mapované prostředí.

 Prvním krokem je vytvoření mapy texturou datové krychle. V mnoha typy aplikací nemusí být ideální být efektivní, zejména v případě, že je jemně odraz nebo není zabírat viditelného prostor na obrazovce obsah mapy datové krychle. Mnoho hry například použít pro mapování prostředí a jenom používání ten nejblíže každý objekt odrážející mapy předvypočítaných datové krychle, i když to znamená, že odraz není správný. I hrubý aproximace je často dostatečně vhodné pro přesvědčivé vliv.

### <a name="to-create-textures-for-an-environment-map-by-using-the-image-editor"></a>K vytvoření textury pro mapování prostředí pomocí editoru obrázků

1.  Vytvořte texture pro práci s. Informace o tom, jak do projektu přidejte texturou, najdete v části Začínáme v [Editor obrázků](../designers/image-editor.md).

2.  Nastavit velikost obrázku tak, že jeho šířka rovná výšku a je druhou mocninou dva velikost; To je nutné kvůli způsobem, že je indexovaný mapu datové krychle. Ke změně velikosti obrázku se v **vlastnosti** okno, zadejte nové hodnoty pro **šířka** a **výška** vlastnosti. Například nastavit hodnotu **šířka** a **výška** vlastnosti na 256.

3.  Použijte výplň texturou plnou barvou. Tato texture bude dolní mapy datové krychle, která odpovídá na povrch kulečníkové tabulky. Barva, které jste použili mějte na paměti pro další texture.

4.  Vytvořte druhý texture, který má stejnou velikost jako první. Tato texture se bude opakovat na čtyři strany mapy datové krychle odpovídajících prostor a stranách kulečníkové tabulky a oblasti kolem kulečníkové tabulky. Zajistěte, aby k vykreslení prostor kulečníkové tabulky v této texture pomocí stejné barvy jako texture dolní. Textury by měl vypadat podobně jako tento:

     ![Texture pro postranní cubemap](../designers/media/gfx_shader_demo_billiard_art_env_texture_side.png "gfx_shader_demo_billiard_art_env_texture_side")

     Mějte na paměti, že mapu reflexe nemusí být fotorealistické účinná; například datové krychle mapy použít k vytvoření bitové kopie v tomto článku obsahuje pouze čtyři kapsami místo šest.

5.  Vytvořte třetí texture, který má stejnou velikost jako ostatní. Tato texture bude horní mapy datové krychle, která odpovídá mezní hodnoty nad tabulkou kulečníkové. Chcete-li tuto část odraz zajímavějšího, můžete nakreslit režijní najevo, že posílit zrcadlová světla, které jste přidali do shaderu v předchozím postupu. Textury by měl vypadat podobně jako tento:

     ![Texture pro horní části cubemap](../designers/media/gfx_shader_demo_billiard_art_env_texture_top2.png "gfx_shader_demo_billiard_art_env_texture_top2")

 Teď, když jste vytvořili jednotlivých textury pro postranní mapy datové krychle, můžete je spojit do datové krychle mapu, která mohou být uloženy v jednom .dds texture nástroj. Můžete použít libovolné aplikaci, kterou chcete vytvořit datové krychle mapy, dokud ho můžete uložit ve formátu texture .dds mapy datové krychle. Tento návod ukazuje, jak vytvořit textury s použitím rozhraní DirectX Texture nástroj, který je součástí 2010 června DirectX SDK.

### <a name="to-assemble-a-cube-map-by-using-the-directx-texture-tool"></a>Ke kompilaci mapu datové krychle pomocí nástroje Texture DirectX

1.  V nástroji Texture rozhraní DirectX v hlavní nabídce zvolte **soubor**, **nové Texture**. **Nové Texture** zobrazí se dialogové okno.

2.  V **typu textury** skupiny, vyberte **Cubemap Texture**.

3.  V **dimenze** skupině, zadejte správné hodnoty pro **šířka** a **výška**a potom zvolte **OK**. Zobrazí se nové texture dokument. Ve výchozím nastavení, texture nejprve zobrazí v dokumentu texture odpovídá **kladné X** datové krychle řez.

4.  Načtení textury, kterou jste vytvořili pro stranu texture datové krychle do datové krychle písmo. V hlavní nabídce zvolte **soubor**, **otevřete na tento Cubemap čelní strany**, vyberte texture, kterou jste vytvořili pro stranu datové krychle a potom zvolte **otevřete**.

5.  Opakováním kroků 4 pro **záporné X**, **kladné Z**, a **záporné Z** datové krychle řezy. To pokud chcete udělat, musíte zobrazit řez, který chcete načíst. Zobrazíte řez mapy jiné datové krychle, v hlavní nabídce zvolte **zobrazení**, **datové krychle mapy vzhled**a potom vyberte řez, který chcete zobrazit.

6.  Pro **kladné Y** datové krychle řez, načtení textury, kterou jste vytvořili pro horní texture datové krychle.

7.  Pro **záporné Y** datové krychle řez, načtení textury, kterou jste vytvořili pro dolní texture datové krychle.

8.  Uložte textury.

 Si lze představit rozložení mapy datové krychle takto:

 ![Rozložení mapy datové krychle prostředí](../designers/media/gfx_shader_demo_billiard_art_env_texture_top.png "gfx_shader_demo_billiard_art_env_texture_top")

 Bitová kopie v horní části je kladné tučné datové krychle Y (+ Y); uprostřed zleva doprava je -X, + Z + X a -Z datové krychle řezy; v dolní části je řez datové krychle -Y.

 Nyní můžete upravit shaderu a přizpůsobte ukázka mapy datové krychle do zbytku shaderu.

### <a name="to-add-environment-mapping-to-your-shader"></a>Přidání mapování prostředí do vašeho shaderu

1.  Upravte vaše shaderu zahrnout příspěvek mapování prostředí pomocí sčítání prolnutí. Graf shaderu by měl vypadat takto:

     ![Closeup obě typu uzlů odrážející shaderu](../designers/media/gfx_shader_demo_billiard_step_4b.png "gfx_shader_demo_billiard_step_4b")

     Všimněte si, že můžete použít **násobení přidat** uzlu zjednodušit shaderu grafu.

     Tady je podrobnější pohled na shaderu uzlů, které implementují mapování prostředí:

     ![Graf shaderu pomocí prostředí mapování přidat](../designers/media/gfx_shader_demo_billiard_step_4a.png "gfx_shader_demo_billiard_step_4a")

2.  Použití textury, kterou jste vytvořili v předchozím postupu pomocí konfigurace vlastností texture mapy datové krychle. Nastavte hodnotu **Texture** vlastnost **Cubemap ukázka** uzlu **Texture2**a pak zadejte soubor textury pomocí **Filename**vlastnost **Texture2** skupina vlastností.

3.  Volitelně můžete upravit odrazovost míč kulečníkové nakonfigurováním **výstup** vlastnost **konstantní** uzlu. Přístup k vlastnosti uzlu, vyberte ho a potom v **vlastnosti** okně najít vlastnost, která chcete získat přístup.

 S použitím mapování prostředí, vaše kulečníkové míč by měl vypadat podobně jako tento:

 ![Closeup prostředí namapované kulečníkové míč](../designers/media/gfx_shader_demo_billiard_ball_4.png "gfx_shader_demo_billiard_ball_4")

 Na tomto posledním obrázku Všimněte si, jak použít účinky, které jste přidali současně vytvořit velmi přesvědčivé míč kulečníkové. Obrazec, texture a osvětlení vytvoření základní vzhled 3D objektu a zrcadlová světla a odrazů zkontrolujte míč kulečníkové zajímavějšího a vypadat podobně jako součást své prostředí.

## <a name="see-also"></a>Viz také

- [Postupy: Exportování shaderu](../designers/how-to-export-a-shader.md)
- [Postupy: použití shaderu 3D modelu](../designers/how-to-apply-a-shader-to-a-3-d-model.md)
- [Návrhář shaderů](../designers/shader-designer.md)
- [Editor obrázků](../designers/image-editor.md)
- [Uzly návrháře shaderů](../designers/shader-designer-nodes.md)