---
title: Animace objektů v Návrháři XAML
titleSuffix: Blend for Visual Studio
ms.date: 07/31/2019
ms.topic: conceptual
ms.assetid: fb88fa26-e835-47f5-9771-2f279441c83c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 4b396c0428f9810fe41fa70aca7b52fba2dd4f5b
ms.sourcegitcommit: 90c3187d804ad7544367829d07ed4b47d3f8a72d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2019
ms.locfileid: "68822174"
---
# <a name="animate-objects-in-xaml-designer"></a>Animace objektů v Návrháři XAML

Blend pro Visual Studio umožňuje snadno vytvořit krátké animace, které přesunou objekty nebo je rozpínají, například.

K vytvoření animace potřebujete *scénář*. Scénář obsahuje jednu nebo více *časových os*. Nastavte *klíčové snímky* na časové ose, aby bylo možné označit změny vlastností. Po spuštění animace Blend pro Visual Studio interpoluje změny vlastností během stanoveného časového období. Výsledkem je hladký přechod. Můžete animovat jakoukoli vlastnost, která patří objektu, i nevizuální vlastnosti.

Na následujících obrázcích je znázorněn scénář nazvaný **Storyboard1**. Časová osa obsahuje klíčové snímky, které označují polohu X a Y obdélníku. Když se tato animace spustí, obdélník se přesune z jedné pozice do druhé plynule.

![Scénář pro animaci v Blend pro Visual Studio](../designers/media/storyboard-timeline.png)

## <a name="create-an-animation"></a>Vytvoření animace

1. Chcete-li vytvořit scénář, v okně **objekty a časová osa** vyberte tlačítko **Možnosti scénáře** a pak vyberte možnost **Nový**.

   ![Přidání scénáře do Blend pro Visual Studio](media/new-storyboard.png)

2. V dialogovém okně **vytvořit prostředek scénáře** zadejte název scénáře.

3. Na panelu **aktiva** v zobrazení Návrh přidejte obdélník na spodní levou stranu stránky.

   ![Obdélník v panelu aktiva Návrhář XAML](media/add-rectangle.PNG)

4. V okně **objekty a časová osa** přesuňte žlutý ukazatel času na **3** sekundy.

   ![Časový indikátor na časové ose](media/timeline-indicator.PNG)

5. V zobrazení Návrh pro stránku přetáhněte obdélník na pravou stranu stránky.

6. Stisknutím tlačítka **Přehrát** Sledujte pohyb obdélníku od levé strany až po pravou stranu stránky.

Hraní dalších změn v obdélníku v různých okamžicích v čase. Například můžete změnit barvu výplně nebo překlopit orientaci v okno Vlastnosti.

## <a name="see-also"></a>Viz také:

- [Vytvoření uživatelského rozhraní pomocí nástroje Blend pro Visual Studio](../designers/creating-a-ui-by-using-blend-for-visual-studio.md)