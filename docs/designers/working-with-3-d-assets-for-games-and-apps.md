---
title: Práce s 3D prostředky pro hry a aplikace
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
f1_keywords:
- vs.graphics
ms.assetid: 910d673b-c884-4eeb-9928-0e89f3d38cb6
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5865597f9833ab04fbd5ca287ba0bc61217d7088
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="work-with-3d-assets-for-games-and-apps"></a>Práce s 3D prostředky pro hry a aplikace

Tento dokument popisuje nástroje sady Visual Studio, které můžete použít k vytvoření nebo úpravě 3D modely, textury a shadery pro založené na rozhraní DirectX hry a aplikace.

## <a name="directx-app-development-in-visual-studio"></a>Vývoj aplikací rozhraní DirectX v sadě Visual Studio
 Aplikace rozhraní DirectX obvykle kombinuje programovací logiku, rozhraní API DirectX a programy vysokou úroveň stínování jazyk (HLSL), společně s audia a 3D visual prostředky k dispozici bohatý a interaktivní multimediální využití. Visual Studio obsahuje nástroje, které můžete použít pro práci s obrázky a textury, 3D modely a shadery aniž byste museli opustit IDE používat jiný nástroj. Nástroje sady Visual Studio jsou obzvláště vhodný pro vytváření *zástupný symbol* prostředky, které můžete použít k testování kódu nebo sestavení prototypy před Komise prostředky produkční prostředí a pro kontroly a úprava produkční prostředí prostředky při ladění aplikace.

 Zde jsou další informace o typech prostředků, které můžete pracovat v sadě Visual Studio.

### <a name="images-and-textures"></a>Bitové kopie a textury
 Bitové kopie a textury poskytují barvy a visual podrobně hry a aplikace. V 3D grafický textury pocházejí v různých formátech, typy a geometrie pro podporu různých používá. Například normální mapy zajišťují normály za pixelů pro další podrobné osvětlení 3D modelů a datové krychle mapy zajišťují texture ve všech pokynů pro použití jako sky zabalení, odrazů a kulovým texture mapování. Textury může poskytnout mapy mip pro podporu efektivní vykreslování na různých úrovních podrobností a může podporovat kanály různých barev a barvu pořadí. Textury mohou být uloženy v různých komprimované formáty, které zabírají vyhrazený grafické paměti a pomáhají grafickými procesory přístup textury efektivněji.

 Editor obrázků Visual Studio můžete pracovat s obrázky a textury v mnoha běžné typy a formáty.

### <a name="3d-models"></a>3D modely
 3D modely vytvořit místa a tvar v hry a aplikace. Minimálně modely kódování pozici body v 3D prostoru – což se označuje jako *vrcholy*– společně s indexování dat k definování čáry nebo trojúhelníky, které představují tvaru modelu. Další data mohou být přidruženy tyto vrcholy – například barev informace, normální vektory nebo atributy specifické pro aplikaci. Každý model můžete také definovat atributy objektu celou – například které shaderu slouží k výpočtu vzhled objektu prostor, nebo které texture se použije na ni.

 Můžete pracovat s 3D modely v různých formátech běžné editoru Visual Studio modelu.

### <a name="shaders"></a>Shadery
 Shadery jsou malé, specifické pro doménu programy, které běží na grafický procesor (GPU). Shadery určit, jak 3D modely se převede na obrazovce tvarů a jak je barevný každý pixelů v těchto tvarů. Vytvořením shaderu a jeho použití na objekt v hry nebo aplikace, můžete poskytnout objekt jedinečný vzhled.

 Shaderu návrháři sady Visual Studio, což je nástroj na základě grafu shaderu návrhu, můžete použít k vytváření vizuálních efektů vlastní bez znalosti programování HLSL.

> [!NOTE]
> Další informace o tom, jak začít s programováním DirectX najdete v tématu [DirectX](http://go.microsoft.com/fwlink/p/?LinkId=224633). Další informace o tom, jak ladění aplikace založené na rozhraní DirectX najdete v tématu [Diagnostika grafiky (ladění grafiky DirectX)](../debugger/visual-studio-graphics-diagnostics.md).

## <a name="directx-version-compatibility"></a>Kompatibilita verzí DirectX
 Visual Studio použije DirectX k vykreslení 2D a 3D prostředky. Můžete vybrat zobrazovací jednotky DirectX 11 nebo vykreslovací software Windows Advanced Rasterizační platformy (Osnova). Zobrazovací jednotky DirectX 11 poskytuje vysoce výkonné, accelerated hardwaru vykreslování na DirectX 11 a grafickými procesory DirectX 10. Zobrazovací jednotky OSNOVĚ pomáhá, ujistěte se, že vaše prostředky fungovat s širokou škálu počítače – to zahrnuje počítače, které nemají moderní grafiky hardwaru a počítače, které mají integrované grafiky hardwaru. Další informace o OSNOVĚ najdete v tématu [Windows Advanced Rasterizační platformy (Osnova) průvodce](http://go.microsoft.com/fwlink/p/?LinkId=224634).

## <a name="related-topics"></a>Související témata

|Název|Popis|
|-----------|-----------------|
|[Práce s texturami a obrázky](../designers/working-with-textures-and-images.md)|Popisuje, jak pracovat s obrázky a textury pomocí sady Visual Studio.|
|[Práce s 3D modely](../designers/working-with-3-d-models.md)|Popisuje, jak pomocí sady Visual Studio pro práci s 3D modelů.|
|[Práce se shadery](../designers/working-with-shaders.md)|Popisuje způsob použití návrháři shaderu sady Visual Studio vytvářet a upravovat vlastní shaderu účinky.|
|[Pomocí 3D prostředky v hry nebo aplikace](../designers/using-3-d-assets-in-your-game-or-app.md)|Popisuje postup používání prostředků, které jste vytvořili pomocí Editor obrázků, Editor modelu nebo shaderu Návrhář v hry nebo aplikace.|