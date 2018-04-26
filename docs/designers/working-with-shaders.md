---
title: Práce se shadery
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 6b2ea1ed-b995-4e75-af19-c68fd37a3bc5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b0c42b90998eef8314f37060b655185d1c68b53b
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="work-with-shaders"></a>Práce s shadery

Návrhář shaderu na základě grafu v sadě Visual Studio slouží k návrhu vlastní shaderu účinky. Můžete použít tyto shadery založené na rozhraní DirectX hry nebo aplikace.

## <a name="shaders"></a>Shadery

A *shaderu* je počítačový program, který provede výpočty grafiky – například vrchol transformace nebo barevné zvýrazňování pixelů – a obvykle běží na grafický procesor (GPU) namísto procesoru. Protože většina fázích kanálu tradiční, – funkce grafiky nyní provádí shaderu programy, můžete je používat k vytvoření kanálu, který je určený výhradně pro potřeby vaší aplikace.

Nejběžnější druhy shadery jsou *vrchol shadery*, který provádět výpočty na vrchol a nahraďte – funkce transformace a osvětlení obvody v hardwaru-programovatelný grafiky a *pixelů shadery*, který provádět výpočty za pixelů, které určit barev pixelů a nahraďte zapojení – funkce barva kombinační programovatelný grafiky hardwaru. Moderní grafiky hardwaru je umožněno i další typy shadery –*trupu shadery*, *domény shadery*, a *geometrie shadery* pro výpočty grafiky a *výpočetní shadery* pro jiný grafiky výpočty. Žádná z těchto fází jsou i v jiných programovatelný grafiky hardwaru k dispozici. Shadery byly původně vytvořeny pomocí sestavení jako jazyk, který poskytuje data paralelní (SIMD) a pokynů zaměřené na grafiky (tečka produktu). Nyní shadery jsou obvykle vytvoří pomocí jazyků vysoké úrovně, jako C jako HLSL (vysokou úroveň shaderu Language).

Návrhář shaderu slouží k vytvoření pixelů shadery interaktivně místo z zadáním a kompilování kódu. V Návrháři shaderu shaderu definované počet uzlů, které představují data a operace a připojení mezi uzly, které představují tok hodnoty data a mezilehlých výsledků prostřednictvím shaderu. Pomocí tohoto přístupu a v reálném čase preview v Návrháři shaderu můžete vizualizovat provádění shaderu snadněji a "objevit" zajímavé variace shaderu prostřednictvím experimenty.

## <a name="dgsl-documents"></a>DGSL dokumenty

Návrhář shaderu uloží shadery ve formátu směrované grafu shaderu jazyk (DGSL), který je formátu XML, který je založen na směrované grafů Markup Language (DGML). Můžete provést DGSL shadery přímo u 3D modely v editoru modelu. Ale předtím, než budete moct použít shaderu DGSL ve vaší aplikaci, je nutné ho exportovat do formátu, který funguje s technologií DirectX – například HLSL.

Protože DGSL je kompatibilní s DGML, můžete použít nástroje, které slouží k analýze DGML dokumenty k analýze vaší shadery DGSL. Informace o DGML najdete v tématu [Principy směrované značení grafů jazyk (DGML)](http://msdn.microsoft.com/library/ee842619.aspx).

## <a name="related-topics"></a>Související témata

|Název|Popis|
|-----------|-----------------|
|[Návrhář shaderů](../designers/shader-designer.md)|Popisuje, jak používat návrháře shaderu Visual Studio pro práci s shadery.|
|[Uzly návrháře shaderů](../designers/shader-designer-nodes.md)|Popisuje druhy shaderu Návrhář uzlů, které můžete použít k dosažení grafiky účinky.|
|[Příklady návrháře shaderů](../designers/shader-designer-examples.md)|Obsahuje odkazy na témata, která ukazují, jak používat návrháře shaderu k dosažení běžné grafiky účinky.|