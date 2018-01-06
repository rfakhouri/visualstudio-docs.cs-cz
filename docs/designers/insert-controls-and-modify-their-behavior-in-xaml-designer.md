---
title: "Vložení ovládacích prvků a změna jejich chování v Návrháři XAML | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a80fff74-bf01-41c9-ab85-ada7a873c3a9
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: 09eb82bede66b839b7b3facdb61d8fc5d3ed2bd0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="insert-controls-and-modify-their-behavior-in-xaml-designer"></a>Vložení ovládacích prvků a změna jejich chování v Návrháři XAML
Ovládací prvky povolit uživatelům interakci s vaší aplikací. Můžete je použít ke shromažďování informací a provádět akce, jako například animace objekt nebo dotaz na zdroj dat.  
  
 **V tomto tématu:**  
  
-   [Přidání ovládacích prvků do kreslicí plochy](#Insert)  
  
-   [Ujistěte se, provádět akce – ovládací prvky](#Modify)  
  
##  <a name="Insert"></a>Přidání ovládacích prvků do kreslicí plochy  
 Můžete přetáhnout ovládacích prvků z **prostředky** panelu na **návrhové plochy**a následně je v upravit **vlastnosti** okno.  
  
 ![Blend & č. 45; Prostředky & č. 45; FlipView](../designers/media/blend_assetsflipview_xaml.png "blend_AssetsFlipView_XAML")  
  
 Tyto videa ukazují, jak používat některé z běžných ovládacích prvků.  
  
|Ovládací prvek|Podívejte se na krátké video|  
|-------------|-------------------------|  
|`Menu`![ ] (../designers/media/015a263c-0b2b-4253-ac57-b86fcb8c9591.png "015a263c-0b2b-4253-ac57-b86fcb8c9591")|![Konfigurace nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [přidání ovládacích prvků](https://www.youtube.com/watch?v=ra4AHfgD4Ys&list=PLBDF977B2F1DAB358&index=45)|  
|`Button`![ ] (../designers/media/05df1779-a68f-436b-b834-a91b7995a3ec.png "05df1779-a68f-436b-b834-a91b7995a3ec")|![Konfigurace nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [návrh tlačítka](http://www.popscreen.com/v/6A4gb/Microsoft-Expression-Blend-Designing-a-Button)|  
|`Textblock`![ ] (../designers/media/42165963-00f7-4a33-abcd-b0849edebada.png "42165963-00f7-4a33-abcd-b0849edebada")|![Konfigurace nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [Přidání bitové kopie do textblock](http://www.popscreen.com/v/6A4du/Microsoft-Expression-Blend-Adding-Images-to-a-TextBlock)|  
|`Slider`![ ] (../designers/media/bf689d92-3c74-4218-815c-e98c930ac189.png "bf689d92-3c74-4218-815c-e98c930ac189")|![Konfigurace nainstalované součásti](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [sestavení Slider s popisek](http://www.bing.com/videos/search?q=slider%20expression%20blend&qs=n&form=QBVR&pq=slider%20expression%20blend&sc=1-23&sp=-1&sk=#view=detail&mid=F1BB7DB91B2772A8CA2AF1BB7DB91B2772A8CA2A)|  
|`GridSplitter`![ ] (../designers/media/d08d529f-a27e-4a8f-95aa-8a4e8b4ee7be.png "d08d529f-a27e-4a8f-95aa-8a4e8b4ee7be")|![Konfigurace nainstalované součásti](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [pracovat GridSplitter](http://msdn.microsoft.com/expression/cc188687.aspx)|  
  
### <a name="make-a-control-out-of-an-image-shape-or-path"></a>Vytvoření ovládacího prvku mimo obrázek, tvar nebo cesta  
 Můžete použít libovolný objekt do ovládacího prvku.  
  
 ![Dialogové okno zkontrolujte do ovládacího prvku Blend](../designers/media/blend_makeintocontrol_xaml.png "blend_MakeIntoControl_XAML")  
  
 Představte si například přehled o televize v centru stránky. Můžete dokonce vytvářet ovládací prvky mimo malé bitové kopie, které vypadají tlačítka televize. Pak mohou uživatelé kliknout na těchto tlačítek, chcete-li změnit kanál.  
  
 To je možné, protože tlačítka jsou nyní ovládací prvky. Pomocí ovládacích prvků reagovat na akce uživatelů; v takovém případě, když uživatel klikne na tlačítko.  
  
 Chcete-li ovládacího prvku, vyberte objekt. Potom na **nástroje** nabídky, klikněte na tlačítko **zkontrolujte řízení**.  
  
##  <a name="Modify"></a>Ujistěte se, provádět akce – ovládací prvky  
 Ovládací prvky můžete provádět akce, když uživatelé komunikovat s nimi. Například se může spustit animace, aktualizace zdroje dat nebo přehrávání videa.  
  
 Použití *aktivační události*, *chování*, a *události* aby ovládací prvky provádět akce.  
  
### <a name="triggers"></a>Aktivační procedury  
 A *aktivační událost* změny vlastnosti nebo provede úlohu v reakci na událost nebo změny v jiné vlastnosti. Můžete například změnit barvu tlačítka při přechodu přes ho.  
  
 ![Panel "Aktivační události"](../designers/media/custom_button_blend_propertytriggerinfo.png "custom_button_blend_PropertyTriggerInfo")  
  
 **Podívejte se na krátké video:** ![nakonfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [přidat vlastnost aktivační událost](http://www.popscreen.com/v/6A4gO/Microsoft-Expression-Blend-Adding-a-Property-Trigger).  
  
### <a name="behaviors"></a>Chování  
 A *chování* je opakovaně použitelné balíček kódu. Ho můžete provést trochu více než změnit vlastnosti. Může provádět akce, jako je například dotaz datové služby. Blend se dodává s malá skupina je, ale můžete přidat další. Přetáhněte chování na všech objektů v vaší návrhové plochy a pak přizpůsobit chování nastavením vlastnosti.  
  
 ![FluidMoveBehavior v panelu Vlastnosti](../designers/media/b4_fluidmovebehaviorproperties_sample.png "b4_FluidMoveBehaviorProperties_Sample")  
  
 **Podívejte se na krátké video:** ![nakonfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [přizpůsobte tipy: Úvod do používání chování část 1](http://www.bing.com/videos/search?q=Expression%20blend%20behaviors&qs=n&form=QBVR&pq=expression%20blend%20behavior&sc=4-25&sp=-1&sk=#view=detail&mid=CF0DD797ED84DE740904CF0DD797ED84DE740904).  
  
### <a name="events"></a>Události  
 Ultimate flexibilitu zpracování *událostí*. Budete muset napsat kód.  
  
 **Podívejte se na krátké video:** ![nakonfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [přidat událostí myši](https://www.youtube.com/watch?v=2PMxAlb-x_E).