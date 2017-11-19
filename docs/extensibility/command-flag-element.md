---
title: "Příkaz příznak Element | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CommandFlag element (VSCT XML schema)
- VSCT XML schema elements, CommandFlag
ms.assetid: 5ef63399-d2db-4dc1-97ce-be1bd4ef4e39
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cc69edbe0865953d242967490a0852c9da4942b3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="command-flag-element"></a>Element Command příznak
Upravuje svého nadřízeného elementu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<CommandFlag>DynamicVisibility</CommandFlag>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující část popisuje platný element hodnoty.  
  
### <a name="attributes"></a>Atributy  
 Žádné  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|AllowParams|Určuje, zda mohou uživatelé zadat parametry příkazu v **příkaz** okno při jejich zadejte kanonický název příkazu.<br /><br /> Platné pro:`Button`|  
|AlwaysCreate|I když nemá žádné skupiny nebo tlačítek, vytvoří se nabídky.<br /><br /> Platné pro:`Menu`|  
|CaseSensitive|Uživatelské záznamy rozlišují velká a malá písmena.<br /><br /> Platné pro:`Combo`|  
|CommandWellOnly|Použít tento příznak, pokud příkaz nezobrazí v nabídce nejvyšší úrovně a chcete, aby byl k dispozici pro další vlastního nastavení prostředí, například pro vytvoření vazby klávesové zkratky. Po instalaci VSPackage tyto příkazy můžete přizpůsobit tak, že otevřete **možnosti** dialogové okno a potom úpravy příkaz umístění v rámci **klávesnice prostředí** kategorie. Tento příznak nemá vliv na umístění v místní nabídky, panely nástrojů, nabídky řadiče nebo dílčích.<br /><br /> Platná pro: `Button`,`Combo`|  
|DefaultDisabled|Ve výchozím nastavení, příkaz vypnutá, pokud není načtený VSPackage, která je implementuje nebo `QueryStatus` nebyla zavolána metoda.<br /><br /> Platná pro: `Button`,`Combo`|  
|DefaultDocked|Ukotveno ve výchozím nastavení. Toto nastavení už se vztahuje na panely nástrojů, protože jsou vždy ukotven.|  
|DefaultInvisible|Ve výchozím nastavení, příkaz je neviditelná, pokud není načtený VSPackage, která je implementuje nebo `QueryStatus` nebyla zavolána metoda.<br /><br /> Doporučujeme, abyste o zkombinujete `DynamicVisibility` příznak.<br /><br /> Platná pro: `Button`, `Combo`,`Menu`|  
|DontCache|Vývojové prostředí neukládá do mezipaměti `QueryStatus` výsledky metody pro tento příkaz.<br /><br /> Nabídky tato hodnota informuje řadič nabídky není pro ukládání do mezipaměti text jeho položky nabídky. Pomocí tohoto příznaku, když v nabídce obsahuje dynamické položky nebo položky, které mají dynamický text.<br /><br /> Platná pro: `Button`,`Menu`|  
|DynamicItemStart|Označuje začátek dynamické seznamu. To umožňuje prostředí k vytvoření seznamu postupně voláním `QueryStatus` metodu položky seznamu, dokud se vrátí příznak OLECMDERR_E_UNSUPPORTED. To funguje dobře pro položky, jako je naposledy použité okno seznamy a seznamy (naposledy použitých).<br /><br /> Platné pro:`Button`|  
|DynamicVisibility|Viditelnost příkazu lze změnit pomocí `QueryStatus` metoda nebo prostřednictvím kontextu identifikátor GUID, který je součástí `VisibilityConstraints` části.<br /><br /> Platí pro příkazy, které se zobrazují na nabídek a panelů nástrojů okna nástroj, ale není na nejvyšší úrovni panely nástrojů, které se zobrazují v hlavním okně. Položky panelu nástrojů nejvyšší úrovně můžete zakázat, ale není skrytý, pokud je příznak OLECMDF_INVISIBLE vrácené z `QueryStatus` metoda. Příkazy nástrojů, které se zobrazují na panely nástrojů nástroje může být skryté.<br /><br /> V nabídce tento příznak také určuje, měl by být automaticky skrytý skryté všichni její členové. Tento příznak je přiřazen dílčích obvykle, protože už máte toto chování nabídek nejvyšší úrovně.<br /><br /> Tento příznak by měl nelze kombinovat s `DefaultInvisible` příznak.<br /><br /> Platná pro: `Button`, `Combo`,`Menu`|  
|Funkce Filtrování kláves|Podívejte se na téma filtrování klíče v části [Element pole se seznamem](../extensibility/combo-element.md).<br /><br /> Platné pro:`Combo`|  
|FixMenuController|Pokud tento příkaz je umístěn na řadiči nabídky, příkaz je vždy výchozí; To znamená příkaz je vybrána vždy, když výběru tlačítka nabídky řadiče sám sebe. Pokud má řadič nabídky `TextIsAnchorCommand` příznak nastaven, pak řadič nabídky také provede jeho text z příkazu, který má `FixMenuController` příznak.<br /><br /> By měl mít jenom jeden příkaz v nabídce řadiči `FixMenuController` příznak. Pokud je označeno tak víc než jednoho příkazu, poslední příkaz v nabídce se změní na výchozí.<br /><br /> Platné pro:`Button`|  
|IconAndText|Zobrazte ikonu a text na nabídek a panelů nástrojů.<br /><br /> Platná pro: `Button`, `Combo`,`Menu`|  
|NoAutoComplete|Funkce automatického dokončování je zakázána.<br /><br /> Platné pro:`Combo`|  
|NoButtonCustomize|Nenechte uživatele přizpůsobit toto tlačítko.<br /><br /> Platná pro: `Button`,`Combo`|  
|NoKeyCustomize|Nepovolujte přizpůsobení klávesnice.<br /><br /> Platná pro: `Button`,`Combo`|  
|NoShowOnMenuController|Pokud tento příkaz je umístěn na řadiči nabídky, příkaz se v rozevíracím seznamu nezobrazí.<br /><br /> Platné pro:`Button`|  
|NotInTBList|V seznamu dostupných panelů nástrojů nezobrazí. Toto je platná pouze pro typy nabídky panelu nástrojů.<br /><br /> Platné pro:`Menu`|  
|NoToolbarClose|Uživatel nemůže zavřít panelu nástrojů. Toto je platná pouze pro typy nabídky panelu nástrojů.<br /><br /> Platné pro:`Menu`|  
|PICT|Zobrazit pouze ikonu na panelu nástrojů, ale pouze text v nabídce. Pokud není určena žádná ikona, zobrazuje prokliknutelný prázdného místa na panelu nástrojů.<br /><br /> Platné pro:`Button`|  
|PostExec|Díky, na příkaz neblokující. Vývojové prostředí odkládat údaje spuštění, dokud nejsou dokončeny všechny předběžné zpracování dotazů.<br /><br /> Platné pro:`Button`|  
|RouteToDocs|Příkaz se směruje na aktivní dokument.<br /><br /> Platné pro:`Button`|  
|StretchHorizontally|Když je nastavený tento příznak, stane se šířka minimální šířku pro pole se seznamem a pokud je na panelu nástrojů místnosti, pole se seznamem roztahovány k vyplnění dostupné místo. K tomu dojde pouze v případě vodorovně ukotveno panelu nástrojů a příznaku (na všech kromě prvního pole se seznamem je ignorována příznak) můžete pouze jeden pole se seznamem na panelu nástrojů.<br /><br /> Platné pro:`Combo`|  
|TextMenuUseButton|Použití `ButtonText` pole pro nabídky. V poli výchozí `MenuText` Pokud není zadán.<br /><br /> Platné pro:`Button`|  
|TextChanges|Text příkazu nebo nabídky lze změnit v době běhu, obvykle prostřednictvím `QueryStatus` metoda.<br /><br /> Platná pro: `Button`,`Menu`|  
|TextChangesButton|Platné pro:`Button`|  
|TextIsAnchorCommand|Pro řadič nabídky a text v nabídce jsou převzaty z příkaz výchozí (ukotvení). Příkaz ukotvení je poslední příkaz vybrali nebo zajištěné. Pokud není nastavený tento příznak, používá řadič nabídky vlastní `MenuText` pole. Ale kliknutím na nabídku řadiče umožňuje stále poslední vybraný příkaz z tohoto řadiče.<br /><br /> Doporučujeme vám, že zkombinujete tento příznak se `TextChanges` příznak.<br /><br /> Tento příznak se vztahuje pouze na nabídky typu MenuController nebo MenuControllerLatched.<br /><br /> Platné pro:`Menu`|  
|TextMenuCtrlUseMenu|Použití `MenuText` pole na řadičích nabídky. V poli výchozí `ButtonText`.<br /><br /> Platné pro:`Button`|  
|TextMenuUseButton|Použití `ButtonText` pole pro nabídky. V poli výchozí `MenuText` Pokud není zadán.<br /><br /> Platné pro:`Button`|  
|Typu TextOnly|Zobrazit pouze textu na panelu nástrojů nebo nabídky, ale žádná ikona i v případě, že je zadán ikonu.<br /><br /> Platné pro:`Button`|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Element tlačítka](../extensibility/buttons-element.md)|Obsahuje skupinu pro [Button Element](../extensibility/button-element.md) elementy.|  
|[Element nabídky](../extensibility/menus-element.md)|Definuje všechny nabídky, které implementuje VSPackage.|  
  
## <a name="see-also"></a>Viz také  
 [Visual Studio příkaz tabulky (. Soubory Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)