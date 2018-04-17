---
title: Práce s textury a obrázků | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-designers
ms.topic: conceptual
ms.assetid: b9fbc8fa-66d1-4055-8460-24d8b8fbe43e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 148732e45dc839a30e60586de594d6b62fda16a8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="working-with-textures-and-images"></a>Práce s texturami a obrázky
Můžete použít Editor obrázků v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] k vytvoření a úpravám textury a bitové kopie. Editor obrázků podporuje bohaté texture a obrázkových formátů, jako jsou ty, které se používají v DirectX vývoj aplikací.  
  
> [!NOTE]
>  Editor obrázků nepodporuje nízká color bitové kopie jako ikony nebo kurzory. Chcete-li vytvořit nebo upravit tyto druhy bitové kopie, použijte [Editor obrázků pro ikony](/cpp/windows/image-editor-for-icons).  
  
## <a name="textures-and-images"></a>Textury a obrázků  
 Textury a bitové kopie jsou na základní úrovni, jenom tabulek dat, která slouží k poskytování visual podrobně grafiky aplikace. Druh podrobností, která poskytuje texture nebo bitové kopie, závisí na tom, jak se používá, ale barva ukázky, hodnoty alfa (průhlednost), normály a výška hodnoty jsou běžných příkladů. Hlavní rozdíl mezi texturou a bitovou kopii je, že texturou je určen pro použití spolu s znázornění tvaru – obvykle 3D modelu – vyjádřit kompletní objekt nebo scény, ale bitovou kopii je obvykle samostatné reprezentace objektu nebo scény .  
  
 Běžné typy textury patří:  
  
 Texture mapy  
 Texture mapy obsahovat hodnoty barev, která jsou uspořádána jako jeden –, dva- nebo trojrozměrné matice. Používají se k jsou uvedeny podrobnosti barev v ovlivněných objektu. Barvy běžně kódované pomocí kanály barva RGB (červená, zelená, modrá) a může zahrnovat čtvrtý kanál, alfa, který představuje průhlednost. Ne tak často, může být zakódován barvy v jiné barevné schéma nebo čtvrtý kanál může obsahovat data než alpha – například výšku.  
  
 Normální mapy  
 Normální maps obsahují normály. Používají se k jsou uvedeny podrobnosti osvětlení ovlivněných objektu. Normály běžně kódované pomocí součásti červenou, zelenou a modrou barvu pro uložení x, y a z dimenze vektoru. Ale existují další kódování – například kódování, které jsou založeny na polární souřadnice.  
  
 Výška mapy  
 Výška mapy obsahovat výška pole data. Používají se k poskytování formuláře geometrickou podrobností ovlivněného objektu – pomocí kódu shaderu k výpočtu požadovaný účinek – nebo poskytovat datových bodů pro použití jako generování geologické struktury. Výška hodnoty jsou běžně kódovaný pomocí jeden kanál v texturou.  
  
 Mapuje datové krychle  
 Mapy datové krychle může obsahovat různé typy dat – například barvy nebo normály –, ale jsou uspořádána jako šesti textury na řezy datovou krychlí. Z toho důvodu nejsou datové krychle mapy vzorkovat zadáním texture souřadnice, ale zadáním vektor jehož původ je center datové krychle; odebrání vzorku v okamžiku, kdy vektoru protíná datové krychle. Datové krychle mapování slouží k poskytování sblížení prostředí, které lze použít k výpočtu odrazů – to se označuje jako *prostředí mapování*– nebo poskytovat texture kulovým objektů s menší narušení než basic Dvourozměrná textury může poskytnout.  
  
 Všechny texture můžete kódování a komprimované v několika způsoby, které jsou ortogonální typu dat, která obsahuje texturou nebo dimenzionalitě nebo "tvar" textury. Lepší výsledky pro různé druhy dat. yield však jiný kódování a metody komprese.  
  
 Editor obrázků můžete vytvářet a upravovat textury a bitové kopie způsoby, které vypadat podobně jako ostatní editory bitové kopie. Editor obrázků také poskytuje mipmapping a další funkce pro použití s 3D grafiky a podporuje mnoho vysoce komprimované, accelerated hardwaru texture formátů, které podporuje rozhraní DirectX.  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Editor obrázků](../designers/image-editor.md)|Popisuje, jak použít Editor obrázků pro práci s textury a bitové kopie.|  
|[Příklady editoru obrázků](../designers/image-editor-examples.md)|Obsahuje odkazy na témata, která ukazují, jak provádět běžné image zpracování úloh pomocí editoru bitové kopie.|