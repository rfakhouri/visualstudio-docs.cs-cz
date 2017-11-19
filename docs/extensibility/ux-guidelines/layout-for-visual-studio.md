---
title: "Rozložení pro sadu Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c19e3022-047c-43b6-a046-a82717efed4f
caps.latest.revision: "2"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0ebb82c49820bdd664324984bd7d3bb88a5bb5fd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="layout-for-visual-studio"></a>Rozložení pro sadu Visual Studio
Většina dialogová okna v sadě Visual Studio je [rozložení dialogové okno nástroj](../../extensibility/ux-guidelines/layout-for-visual-studio.md#BKMK_UtilityDialogLayout), které jsou unthemed tento standard postupujte podle kroků v dialogových oknech [Windows Desktop dialogové okno rozložení Principy](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742499\(v=vs.85\).aspx). Při přesunu Visual Studio k aktualizaci jeho uživatelském rozhraní, některé výraznější dialogová okna mají nový návrh, který stanoví je jako produktu definování prostředí. Tyto [motivu dialogové okno rozložení](../../extensibility/ux-guidelines/layout-for-visual-studio.md#BKMK_ThemedDialogLayout) vzhled motivu.  
  
##  <a name="BKMK_UtilityDialogLayout"></a>Dialogové okno nástroj rozložení  
  
-   Všechny ovládací prvky v dialogovém okně Nástroj začínat v horní části levého a toku dolů.  
  
-   Nikdy center ovládacích prvků v dialogovém okně k vyplnění velké oblasti.  
  
-   Použijte prostředí písmo veškerého textu v dialogovém okně. Při zápisu visual specifikace, zadejte místo výběru konkrétní písma a velikost písma prostředí. V tématu [písmo prostředí](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TheEnvironmentFont).  
  
-   Použít konzistentní řízení mezery a umístění pro podporu cílem kvality v řemeslné ruční práce.  
  
-   Dialogová okna se může stát složitější z větší počet ovládací prvky, jedinečné srovnáním ovládacích prvků nebo obojí. Pro tyto situace komplexní povolte dostatečným místem mezi řízení seskupení a přidělit uživateli logický tok analyzovat.  
  
### <a name="utility-dialog-layout-examples"></a>Příklady rozložení nástroj dialogové okno  
 Všechny dimenze jsou vyjádřené jako pixelů.  
  
 ![Dialogové okno mezery pro popisky výše ovládací prvky](../../extensibility/ux-guidelines/media/0801-a_utilityspacingabove.png "0801 a_UtilitySpacingAbove")  
  
 **Obrázek 08.01-a: Mezery pokyny pro dialogová okna nástroje s popisky nad ovládací prvky**  
  
 ![Dialogové okno mezery pro popisky nalevo od ovládací prvky](../../extensibility/ux-guidelines/media/0801-b_utilityspacingleft.png "0801 b_UtilitySpacingLeft")  
  
 **Obrázek 08.01-b: Mezery pokyny pro dialogová okna nástroje s popisky vlevo ovládacích prvků**  
  
### <a name="layout-details"></a>Podrobnosti o rozložení  
  
#### <a name="margins"></a>Okraje  
  
-   Všechna dialogová okna by měl mít 12 pixelů ohraničení okrajů všechny.  
  
-   Okraje v rámci skupiny musí mít 9 pixelů od okraje rámečku.  
  
-   Okraje v rámci ovládacího prvku karta by měl být 6 pixelů od okraje ovládacího prvku karta.  
  
#### <a name="command-buttons"></a>Příkazová tlačítka  
  
-   Příkazová tlačítka pracovat v dialogovém okně rámečku, nikoli na obsah. Tyto musí být umístěny v dolní části správné a musí mít dostatek proměnné místa výše a nastavit odlišné samostatné tlačítka.  
  
-   Pokud existují vodorovné tlačítka, která pracovat v dialogovém okně, konfigurace tlačítko alternativní příkaz je nad sebou v pravém horním rohu. V tématu [vnitřních příkazová tlačítka](../../extensibility/ux-guidelines/layout-for-visual-studio.md#BKMK_InteriorCommandButtons) níže.  
  
-   Místo na levé straně příkazová tlačítka (nižší nalevo od středu dialogového okna) se považuje za součást "vzdálené" ovládací prvky dialogového okna operaci. Jediné, co by měl pronikat na toto místo je odkaz nápovědy, které se týkají celkové úloh nebo dialogové okno.  
  
-   Příkazová tlačítka by měl být 75 x 23 pixelů.  
  
-   Příkazová tlačítka by měla být 6 pixelů od sebe.  
  
 ![Základní tlačítko zarovnání](../../extensibility/ux-guidelines/media/0801-c_buttonalign.png "0801 c_ButtonAlign")  
  
 **Obrázku 08.01 – c: Základní tlačítko zarovnání**  
  
#### <a name="labels"></a>Popisky  
  
-   Zarovnání doleva všechny popisky.  
  
-   Pro popisky, které se nacházejí výše ovládacího prvku, se musí doleva align přesněji s ovládacím prvkem pod ním a dolní části popisek by měl být 5 pixelů nad horní části Další ovládací prvek (například pole se seznamem).  
  
-   Pro popisky, které se nacházejí na levé straně ovládacích prvků je minimální šířka až vstupního ovládacího prvku popisek 10 pixelů. Předpokládané druhý sloupec by se mělo vytvořit pro zarovnání textová pole, pole se seznamem nebo jiných ovládacích prvků.  
  
-   Popisky jsou věty a jsou následovaným dvojtečkou. V tématu [styl textu](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TextStyle).  
  
#### <a name="distance-between-controls"></a>Vzdálenost mezi ovládacími prvky  
 Ovládací prvky zásobníku přiměřeně. Neexistuje žádné absolutní platí pro mezery mezi skládaný ovládací prvky. Těsnost mezi ovládacími prvky mohou mírně lišit dialogová okna. Doporučené mezery je 20 pixelů pro dvojice svislé nebo popisek ovládacího prvku a 9 pixelů pro dvojice vodorovné nebo popisek ovládacího prvku. Mezery minimální ovládací prvek pro vodorovné dvojice je 6 pixelů.  
  
 ![Doporučená vzdálenost mezi ovládacími prvky](../../extensibility/ux-guidelines/media/0801-d_controldistance.png "0801 d_ControlDistance")  
  
 **Obrázek 08.01 – d: Doporučení pro vzdálenost mezi ovládacími prvky**  
  
#### <a name="control-indentation"></a>Ovládací prvek odsazení  
 Když jsou vnořené ovládací prvky, Zarovnat vnitřní ovládací prvky vodorovně s levým okrajem ovládací prvek nahoře, obvykle popisku.  
  
 ![Vnořené zarovnání ovládacího prvku](../../extensibility/ux-guidelines/media/0801-e_controlalign.png "0801 e_ControlAlign")  
  
 **Obrázek 08.01 – e: Zarovnání ovládacího prvku vnořené**  
  
#### <a name="control-width"></a>Šířka ovládacího prvku  
 Šířka textového pole nebo jiné podobné ovládací prvky musí být delší než průměrná vstup pro pole. Průměrná anglické slovo je pět znaků. Textové pole, které vyžaduje dlouhého názvu cesty by měl být například, pokud umožňuje vodorovném rozložení, při rozevírací seznam pro platformu názvy by měly být pouze délku, která umožňuje nejdelší položku.  
  
#### <a name="helper-text"></a>Textu Pomocník  
  
-   Zobrazí se dialogové okno můžete zobrazit text pomocné rutiny, který poskytuje další informace o účelu dialogového okna. To většinou nachází v horní části a může být 1 – 2 věty.  
  
-   Délka řádku by měla být možnost šířku pro uživatele, pro analýzu a číst. Střední dialogové okno by měl být delší než 550 pixelů.  
  
####  <a name="BKMK_InteriorCommandButtons"></a>Vnitřní příkazová tlačítka  
 V dialogových oknech složitější pravděpodobně ovládacího prvku interní vlastní související tlačítka, které by mohly ovlivnit, kde se nachází dialogové okno potvrzení tlačítka.  
  
-   Svislé zarovnání (sloupec) interior tlačítka při použití **OK**/**zrušit** jsou orientovány vodorovně v pravém dolním rohu.  
  
-   Vodorovné zarovnání (řádek) interior tlačítka při použití **OK**/**zrušit** jsou orientovány svisle v pravém horním rohu. Tato situace je méně častých.  
  
-   Velikost vnitřních tlačítka cílem by měl velikost standardní tlačítko 75 x 23 pixelů, odpovídající velikost **OK**/**zrušit** tlačítka, pokud je to možné. Pokud popisků tlačítka provede tlačítko přesáhla velikost standardní tlačítko, by měl tlačítek v dané sadě přiblížili tato širší velikost.  
  
 ![Tlačítka OK vodorovné a zrušit](../../extensibility/ux-guidelines/media/0801-f_horizokcan.png "0801 f_HorizOKCan")  
  
 **Obrázek 08.01-f: Svislé Interior tlačítka s vodorovné OK nebo Storno**  
  
 ![Tlačítka OK svislé a zrušit](../../extensibility/ux-guidelines/media/0801-g_vertokcan.png "0801 g_VertOKCan")  
  
 **Obrázek 08.01-g: Vodorovné vnitřních tlačítka s svislé OK nebo Storno**  
  
#### <a name="browse-button"></a>[Procházet...] tlačítko  
 **[Procházet...]**  tlačítka, které budou následovat v textovém poli by se "Procházet..." pravopisu v úplné, včetně se třemi tečkami. Pokud je na úzkou místa nebo je více **[Procházet...]**  tlačítka v dialogovém okně tlačítko se může snížit na právě se třemi tečkami.  
  
##  <a name="BKMK_ThemedDialogLayout"></a>Rozložení motivu dialogové okno  
 Motivu dialogová okna v sadě Visual Studio světlejší vzhled a nabízí další prázdné znaky. Typografie poskytuje další zvýraznění a zájmu, nabízí více otevřete mezery mezi řádky a změnu velikosti písem a váhu. Kde je to možné, byly chrome a název řádky snížit nebo odebrat. Rozložení tyto dialogy postupujte podle tohoto vzoru základní:  
  
1.  Je bílé pozadí dialogového okna.  
  
2.  V šedá střední hodnota je 1 pixel pravidlo ohraničení.  
  
3.  Název dialogového okna již nachází v záhlaví okna, ale poskytuje visual a zvýraznit větší velikost bodu. (Najdete v části velikost písma v [styl textu](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TextStyle).)  
  
4.  Popisky spolu s další text, například popis, by měla být **prostředí písma + Bold**.  
  
5.  Vnitřní sloupce jsou odděleny pravidlo 1 pixel barvou.  
  
6.  Výchozí odkazy mít žádné podtržítka. Hover a při stisknutí tlačítka stavy mít změna barvy a podtržítka.  
  
7.  Potvrdit tlačítka (jako je **OK**/**zrušit**) nacházejí v pravém dolním rohu.  
  
### <a name="themed-dialog-layout-examples"></a>Příklady rozložení motivu dialogové okno  
 ![Dialogové okno motivu rozložení](../../extensibility/ux-guidelines/media/0801-h_themeddialog.png "0801 h_ThemedDialog")  
  
 **Obrázek 08.01v: Dialogové okno motivu**  
  
 ![Dialogové okno motivu dimenze](../../extensibility/ux-guidelines/media/0801-i_themeddialogdimensions.png "0801 i_ThemedDialogDimensions")  
  
 **Obrázek 08.01-i: Motivu dialogu - dimenze**  
  
 ![Motivu dialogové okno písem](../../extensibility/ux-guidelines/media/0801-j_themeddialogfonts.png "0801 j_ThemedDialogFonts")  
  
 **Obrázek 08.01-j: Motivu dialogu - písem**  
  
 ![Motivu dialogové okno barvy](../../extensibility/ux-guidelines/media/0801-k_themeddialogcolors.png "0801 k_ThemedDialogColors")  
  
 **Obrázek 08.01-k: Motivu dialogu - barvy**  
  
## <a name="see-also"></a>Viz také  
 [Aplikace vzory pro sadu Visual Studio](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md)   
 [Ovládací prvky (Windows)](https://msdn.microsoft.com/library/windows/desktop/dn742399.aspx)   
 [Dialogová okna (Windows)](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742499\(v=vs.85\).aspx)