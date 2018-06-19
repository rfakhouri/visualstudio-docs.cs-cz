---
title: Vložení ovládacích prvků a změna jejich chování v Návrháři XAML
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: a80fff74-bf01-41c9-ab85-ada7a873c3a9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: e2ec53e78bc88e18d9ba8e77aa888ffa855b64ea
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31924152"
---
# <a name="insert-controls-and-modify-their-behavior-in-xaml-designer"></a>Vložení ovládacích prvků a změna jejich chování v Návrháři XAML

Ovládací prvky povolit uživatelům interakci s vaší aplikací. Můžete je použít ke shromažďování informací a provádět akce, jako například animace objekt nebo dotaz na zdroj dat.

## <a name="add-controls-to-the-artboard"></a>Přidání ovládacích prvků do kreslicí plochy

Můžete přetáhnout ovládacích prvků z **prostředky** panelu na **návrhové plochy**a následně je v upravit **vlastnosti** okno.

![Inovativně prostředky ovládací prvky karet](../designers/media/blend_assetsflipview_xaml.png)

### <a name="make-a-control-out-of-an-image-shape-or-path"></a>Vytvoření ovládacího prvku mimo obrázek, tvar nebo cesta

Můžete použít libovolný objekt do ovládacího prvku.

![Dialogové okno Blend zkontrolujte do ovládacího prvku](../designers/media/blend_makeintocontrol_xaml.png)

Představte si například přehled o televize v centru stránky. Můžete dokonce vytvářet ovládací prvky mimo malé bitové kopie, které vypadají tlačítka televize. Pak mohou uživatelé kliknout na těchto tlačítek, chcete-li změnit kanál.

To je možné, protože tlačítka jsou nyní ovládací prvky. Pomocí ovládacích prvků reagovat na akce uživatelů; v takovém případě, když uživatel klikne na tlačítko.

Chcete-li ovládacího prvku, vyberte objekt. Potom na **nástroje** nabídky, klikněte na tlačítko **zkontrolujte řízení**.

## <a name="make-controls-do-things"></a>Ujistěte se, provádět akce – ovládací prvky

Ovládací prvky můžete provádět akce, když uživatelé komunikovat s nimi. Například se může spustit animace, aktualizace zdroje dat nebo přehrávání videa.

Použití *aktivační události*, *chování*, a *události* aby ovládací prvky provádět akce.

### <a name="triggers"></a>Aktivační procedury

A *aktivační událost* změny vlastnosti nebo provede úlohu v reakci na událost nebo změny v jiné vlastnosti. Můžete například změnit barvu tlačítka při přechodu přes ho.

![Panel "Aktivační události"](../designers/media/custom_button_blend_propertytriggerinfo.png)

### <a name="behaviors"></a>Chování

A *chování* je opakovaně použitelné balíček kódu. Ho můžete provést trochu více než změnit vlastnosti. Může provádět akce, jako je například dotaz datové služby. Blend se dodává s malá skupina je, ale můžete přidat další. Přetáhněte chování na všech objektů v vaší návrhové plochy a pak přizpůsobit chování nastavením vlastnosti.

![FluidMoveBehavior v panelu Vlastnosti](../designers/media/b4_fluidmovebehaviorproperties_sample.png)

**Podívejte se na video:** ![Play ikonu](../designers/media/bldadminconsoleinitialconfigicon.PNG) [přizpůsobte tipy: Úvod do používání chování část 1](http://www.bing.com/videos/search?q=Expression%20blend%20behaviors&qs=n&form=QBVR&pq=expression%20blend%20behavior&sc=4-25&sp=-1&sk=#view=detail&mid=CF0DD797ED84DE740904CF0DD797ED84DE740904).

### <a name="events"></a>Události

Ultimate flexibilitu zpracování *událostí*. Budete muset napsat kód.