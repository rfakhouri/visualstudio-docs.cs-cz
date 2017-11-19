---
title: "Stránka Možnosti návrháře XAML | Microsoft Docs"
ms.custom: 
ms.date: 03/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.ToolsOptionsPages.XAMLDesigner
ms.assetid: ad3820b2-0d95-4807-a75c-c3467ed973a3
caps.latest.revision: "1"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3058e19d4ac6211c741efd973344a1af14238d10
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="xaml-designer-options-page"></a>Stránka Možnosti Návrhář XAML
Použití **návrháře XAML** stránku možností určíte způsob elementů a atributů formátování v dokumentech XAML. Otevřete tuto stránku, vyberte **nástroje** nabídce a potom zvolte **možnosti**. Pro přístup k **návrháře XAML** vlastnost vyberte **návrháře XAML** uzlu. Nastavení pro Návrhář XAML se použijí při otevření dokumentu. Ano Pokud změníte nastavení, budete muset zavřete a znovu otevřete Visual Studio, aby se změny projevily.

> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md).  

## <a name="enable-xaml-designer"></a>Povolit Návrhář XAML
Pokud vybraná, toto nastavení umožňuje návrháře XAML. Návrhář XAML poskytuje vizuální pracovní oblast pro k úpravě XAML dokumenty. Některé dílčí funkce v sadě Visual Studio, jako je například technologie IntelliSense pro zdroje a datové vazby, vyžadují návrháře XAML, aby byl povolen.

Následující nastavení se vztahuje pouze v případě, že je povolená návrháře XAML. Pokud změníte tuto možnost, musíte restartovat Visual Studio pro nastavení vstoupila v platnost.

## <a name="default-document-view"></a>Výchozí dokument zobrazení
Pomocí tohoto nastavení pro ovládací prvek, zda zobrazení návrhu se zobrazí, když jsou načtena XAML dokumenty.

|||  
|-|-|  
|**Zobrazení zdroje**|Určuje, zda se zobrazí pouze XAML zdroje v zobrazení jazyka XAML. To je užitečné při načítání velkých dokumentů.|  
|**Návrhové zobrazení**|Určuje, zda pouze visual návrháře XAML zobrazí v zobrazení jazyka XAML.|  
|**Split – zobrazení**|Určuje, zda vizuálního návrháře XAML a zdroji XAML zobrazit vedle sebe navzájem v zobrazení jazyka XAML (na základě umístění **rozdělení orientaci** nastavení).|  

## <a name="split-orientation"></a>Orientace rozdělení
Pomocí tohoto nastavení můžete řídit, kdy a jak návrháře XAML se zobrazí v případě úpravy dokumentu XAML. Toto nastavení platí pouze tehdy, když **výchozí dokument zobrazení** je nastaven na **rozděleným zobrazením**.

|||  
|-|-|  
|**Svislý**|Zdroj XAML, zobrazí se na levé straně zobrazení XAML a návrháře XAML, zobrazí se na druhé straně.|  
|**Vodorovné**|Horní XAML zobrazení se zobrazí návrháře XAML a zdroji XAML, zobrazí se pod ním.|  
|**Výchozí**|Dokument XAML používá rozdělení orientaci doporučeno pro platformu cílem projektu dokumentu. Pro většinu platforem jde o ekvivalent **vodorovné**.|  

## <a name="zoom-by-using"></a>Pomocí zvětšení
Toto nastavení použijte k určení, jak funguje přiblížení při úpravě dokumentu XAML.

|||  
|-|-|  
|**Kolečka myši**|Zvětšit v Návrháři XAML posouvání kolečko myši.|  
|**CTRL + kolečka myši**|Zvětšení v Návrháři XAML po stisknutí klávesy CTRL při posouvání kolečko myši.|  
|**ALT + myši wheel**|Zvětšení v Návrháři XAML stisknutím klávesy ALT při posouvání kolečko myši.|  

Při úpravě dokumentu XAML, určuje toto nastavení chování návrháře.

|||  
|-|-|  
|**Interaktivní prvky při vytváření automaticky názvu**|Určuje, zda je výchozí název pro nový interaktivní element poskytnut při přidávání jednoho do návrháře.|  
|**Automaticky vložit vlastnosti rozložení v elementu vytvoření**|Určuje, zda vlastnosti rozložení jsou k dispozici pro nového elementu při přidávání jednoho do návrháře.|  
|**Použití kvadrantu na základě rozložení**|Určuje, jestli aktuálně vybraný ovládací prvek zarovná na nejbližší okraje nadřazeného kontejneru. Pokud toto políčko není zaškrtnuté, zarovnání ovládacího prvku nemění během přesunu a operace vytvoření.|  
|**Automaticky vyplnit položek sady nástrojů**|Určuje, zda uživatelských a vlastních ovládacích prvků v aktuálním řešení se zobrazují v panelu nástrojů automaticky.|  

## <a name="settings-blend-only"></a>Nastavení (pouze Blend)
Určení nastavení při úpravě souborů XAML pomocí Blend pomocí těchto možností.

|||  
|-|-|  
|**Pomocí zvětšení**|Zvětšení v Návrháři XAML posouvání kolečko myši, nebo stiskněte klávesu CTRL nebo ALT při posouvání kolečko myši.|  
|**Typ jednotky**|Určuje, zda měření v designeru jsou založeny na body nebo pixelů. Protože univerzálních aplikací pro Windows nepodporuje body, budou automaticky převedeny na jednotky pixelů Pokud **body** je vybrána.|  

## <a name="artboard-blend-only"></a>Návrhové plochy (pouze Blend)
Tato nastavení použijte k určení chování Návrháře XAML při úpravě dokumenty XAML v programu Blend.

### <a name="snapping"></a>Uchycení

|||  
|-|-|  
|**Zobrazit mřížky snap**|Pokud je vybraná tato možnost, zobrazí se mřížky v Návrháři můžete zarovnat ovládací prvky. Ovládací prvky přidané do návrháře snap do těchto mřížky při **Přichytit k mřížky** je vybraná možnost.|  
|**Přichytit k mřížky**|Při přidávání nebo přesunout kolem návrháře ovládací prvky, jejich Přichytit k mřížky.|  
|**Mezery mřížky**|Určuje mezery mezi mřížek v pixelech nebo body (počítáno od **zadejte jednotky** nastavení).|  
|**Přichytit k zarovnávací čáry**|Určuje, zda se ovládací prvky přichytí k zarovnávací čáry.|  
|**Výchozí rozpětí**|Když **Přichytit k zarovnávací čáry** je povoleno, určuje mezery mezi ovládacího prvku a zarovnávací čáry v pixelech nebo body (počítáno od **zadejte jednotky** nastavení).|  
|**Výchozí odsazení**|Když **Přichytit k zarovnávací čáry** je povoleno, určuje mezera navíc mezi ovládacího prvku a zarovnávací čáry v pixelech nebo body (počítáno od **zadejte jednotky** nastavení).|  

### <a name="animation"></a>Animace
Toto nastavení použijte k určení, jestli upozornění se zobrazí, když závislé (bez accelerated) animací jsou povolené v programu Blend.

### <a name="effects"></a>Účinek
Tato nastavení použijte k určení, zda důsledky jsou vykreslen při úpravě XAML souborů v Návrháři XAML pomocí Blend.

|||  
|-|-|  
|**Vykreslení efekty**|Určuje, zda důsledky vykreslit při úpravě souborů XAML v Návrháři XAML pomocí Blend.|  
|**Prahová hodnota přiblížení**|Určuje procento přiblížení či oddálení v které efekty při vykreslení **vykreslení důsledky** je zaškrtnuto políčko. Pokud jste zvětšení nad rámec tohoto nastavení, důsledky už nebudou zobrazovat v Návrháři XAML.|  

## <a name="see-also"></a>Viz také  
 [XAML v grafickém subsystému WPF](/dotnet/framework/wpf/advanced/xaml-in-wpf)   
 [Postupy: Změna nastavení zobrazení XAML](http://msdn.microsoft.com/en-us/aee87c79-ca01-4f84-8fb7-a9e47048ee47)   
 [XAML a návody kódu](http://msdn.microsoft.com/en-us/b3ff41a0-a2a3-4f61-b698-ac88ec8f799c)
