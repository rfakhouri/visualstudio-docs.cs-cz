---
title: Úpravy stylu objektů v Blendu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fcdd5b98ce49dbf437e8071c5e2cd7d734c666c4
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55028566"
---
# <a name="modify-the-style-of-objects-in-blend"></a>Úpravy stylu objektů v Blendu

Nejjednodušší způsob, jak přizpůsobit objektu je můžete nastavit vlastnosti **vlastnosti** podokně.

Pokud chcete znovu použít nastavení nebo skupiny nastavení, vytvoření opakovaně použitelné prostředku. Může se jednat *styl*, *šablony*, nebo je příčina prostá, jako jsou vlastní barvy. Můžete provést také ovládací prvek zobrazí odlišně v závislosti na jeho stavu. Například tlačítko se změní na zelenou když na něj uživatel klikne.

## <a name="brushes-modify-the-appearance-of-an-object"></a>Štětce: Upravení vzhledu objektu

Použití štětce k objektu, pokud chcete změnit její vzhled.

### <a name="paint-a-repeating-image-or-pattern-on-an-object"></a>Malování s opakováním image nebo vzor pro objekt

Vykreslení s použitím image nebo vzor pro objekt s opakováním *dlaždicového štětce*.

K vytvoření dlaždicového štětce, začněte vytvořením *obrázku štětce*, *kreslicí štětec*, nebo *vizuální štětec* prostředků.

Vytvoření obrázkový štětec pomocí obrázku. Na následujících obrázcích obrázkový štětec, obrázkový štětec vedle sebe a obrázkový štětec obráceně.

![Obrázkový štětec](../designers/media/81f84f56-906d-456b-8288-d77da1e01e31.png) ![štětec Mage vedle sebe](../designers/media/d3782ca8-64da-47a4-a095-c6cdd0fa47a2.png) ![Obrázkový štětec překlopení](../designers/media/38ae3691-f3f1-4a1e-82ca-c7fa164bf56e.png)

Vytvořením kreslicího štětce vektorové kreslení například cestu nebo tvar. Na následujících obrázcích kreslicího štětce, kreslicího štětce vedle sebe a kreslicího štětce obráceně.

![Kreslicí štětec](../designers/media/197666ac-ef57-4c5c-9779-669e991a00a5.png) ![Kreslicí štětec vedle sebe](../designers/media/ba09cda3-4cee-40ba-b3d4-edc032158bdc.png) ![Kreslicí štětec překlopení](../designers/media/15bf6021-620c-4490-9eae-086153d3f14f.png)

Vytvoření vizuální štětec pomocí ovládacího prvku, jako je například tlačítko. Na následujících obrázcích je vizuální štětec a vizuální štětec vedle sebe.

![Vizuální štětec](../designers/media/fb6c90e0-153c-48fe-b563-e601beac6227.png) ![Vizuální štětec vedle sebe](../designers/media/e261b99f-7d8f-4d91-bc84-19c7beccc255.png)

## <a name="styles-and-templates-create-a-consistent-look-and-feel-across-controls"></a>Styly a šablony: Vytvoření konzistentního vzhledu a chování napříč ovládacích prvků

Můžete navrhnout vzhled a chování ovládacího prvku jednou a použití tohoto návrhu pro ostatní ovládací prvky, takže není nutné udržovat je jednotlivě.

**Byste měli použít styl?** : Pokud chcete nastavit výchozí vlastnosti (například barva tlačítka), použijte *styl*. Ovládací prvek můžete upravit, i když jste použili k němu stylu.

**Můžete použít šablonu?** : Pokud chcete změnit strukturu ovládacího prvku, použijte *šablony*. Představte si převod obrázek nebo logo na tlačítku. Ovládací prvek nelze změnit poté, co jste použili šablony do něj.

### <a name="create-a-template-or-style"></a>Vytvořit šablonu nebo styl

Existují dva způsoby, jak vytvořit šablonu. Libovolný objekt lze převést na kreslicí ploše do ovládacího prvku nebo vytváříte šablonu na existující ovládací prvek.

Libovolný objekt převést na šablonu ovládacího prvku, vyberte objekt a pak na **nástroje** nabídce zvolte **Ujistěte se, do ovládacího prvku**.

Pokud chcete založit šablony na existující ovládací prvek, vyberte objekt na návrhové ploše. Potom v horní části návrhové plochy, klikněte na tlačítko s popisem cesty, zvolte **upravit šablonu**a klikněte na tlačítko **upravit kopii** nebo **vytvořit prázdnou**.

![Úprava šablony nabídky](../designers/media/5ebdb33f-aad2-4c10-a328-5e8b04c56a36.png)

Chcete-li vytvořit styl, vyberte objekt a potom v **objekt** nabídce zvolte **upravit styl**a klikněte na tlačítko **upravit kopii** nebo **vytvořit prázdnou**.

- Zvolte **upravit kopii** začínat výchozí styl nebo šablonu ovládacího prvku.

- Zvolte **vytvořit prázdnou** od záčátku.

**Upravit aktuální** možnost bude nabídnuta jen v případě, že upravit styl nebo šablonu, kterou jste vytvořili. Nebude se zobrazovat pro ovládací prvek, který je stále používá výchozí šablonu systému.

V **vytvořit prostředek stylu** dialogové okno, můžete buď pojmenovat stylu nebo šablony tak, aby ji mohli použít později, nebo použít styl nebo šablonu pro všechny ovládací prvky tohoto typu.

![Vytvořit styl prostředek – dialogové okno](../designers/media/4818ee6a-ce60-4b79-91c8-3b1871829eea.png)

> [!NOTE]
> Nelze vytvořit styly a šablony pro každý typ ovládacího prvku. Pokud je nepodporuje ovládací prvek, tlačítko s popisem cesty nezobrazí výše na návrhovou plochu.
> Chcete-li vrátit do rozsahu úprav hlavního dokumentu, klikněte na tlačítko **vrátit rozsah do** ![obnovit obor na ikonu](../designers/media/55844eb3-ed98-4f20-aa66-a6f5b23eeb2b.png).

### <a name="apply-a-style-or-template-to-a-control"></a>Platí pro ovládací prvek stylu nebo šablony

Klikněte pravým tlačítkem na objekt [objekty a časová osa](../designers/creating-a-ui-by-using-blend-for-visual-studio.md#tour-of-the-objects-and-timeline-panel) panelu, vyberte **upravit šablonu**a klikněte na tlačítko **aplikovat zdroj**.

![Použít prostředek nabídky](../designers/media/dc12debc-7711-47d9-84ce-10322a384397.png)

### <a name="restore-the-default-style-or-template-of-a-control"></a>Obnovit výchozí styl nebo šablonu ovládacího prvku

Vyberte ovládací prvek a [vlastnosti](../designers/creating-a-ui-by-using-blend-for-visual-studio.md#tour-of-the-properties-panel) panelu, vyhledejte **styl** nebo **šablony** vlastnost. Zvolte **pokročilé možnosti**a potom klikněte na tlačítko **resetování** v místní nabídce.

## <a name="visual-states-change-the-appearance-of-a-control-based-on-its-state"></a>Vizuální stavy: Změna vzhledu ovládacího prvku na základě jeho stavu

Ovládací prvky mohou mít různé vizuální vzhled na základě interakcí uživatele. Například můžete provést tlačítka změní na zelenou když na něj uživatel klikne nebo ji můžete spustit animaci. Zkraťte nebo prodloužit doba mezi vizuálních stavů pomocí přechodů.

![Přesuňte ukazatel stavu](../designers/media/a95c671a-5639-40b9-83db-1e6b214330d5.png)

**Podívejte se na krátké video:** ![Tlačítko Přehrát](../designers/media/bldadminconsoleinitialconfigicon.PNG) [Správa stavu ovládacích prvků WPF](https://www.youtube.com/watch?v=m0PlkF5i6uw).

## <a name="resources-create-colors-styles-and-templates-and-reuse-them-later"></a>Prostředky: Vytvoření barvy, styly a šablony a pozdější použití

Můžete převést prakticky cokoliv ve vašem projektu a prostředek. Prostředek je právě objekt, který můžete ve své aplikaci využít v různých místech. Můžete například vytvořit jednou barvu, usnadňují prostředek a potom použít na několik objektů. Chcete-li změnit barvu všech těchto objektů, stačí změňte barvu prostředků.

![Převést barvu na prostředek](../designers/media/89203705-cf66-46e0-b153-52a23cd744f7.png) ![Vytvořit prostředek barev – dialogové okno](../designers/media/6bff8b19-3cd5-41a0-bbf9-ff65532d5aae.png)

## <a name="see-also"></a>Viz také:

- [Vytvoření uživatelského rozhraní pomocí nástroje Blend pro Visual Studio](../designers/creating-a-ui-by-using-blend-for-visual-studio.md)