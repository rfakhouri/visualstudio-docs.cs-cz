---
title: Práce s texturami a obrázky | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: b9fbc8fa-66d1-4055-8460-24d8b8fbe43e
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 89c8fd489c29fc9b352c34011349ff447e48adb4
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65690081"
---
# <a name="working-with-textures-and-images"></a>Práce s texturami a obrázky
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete použít Editor obrázků v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] k vytvoření a úprava textury a obrázky. Editor obrázků podporuje bohaté textury a obrazu formátech, jako jsou ty, které se používají při vývoji aplikace rozhraní DirectX.  
  
> [!NOTE]
> Editor obrázků nepodporuje barvy s nízkou Image jako ikony a kurzory. Chcete-li vytvořit nebo upravit tyto druhy imagí, použijte [Editor obrázků pro ikony](https://msdn.microsoft.com/library/586d2b8b-0348-4883-a85d-1ff0ddbf14dd).  
  
## <a name="textures-and-images"></a>Texturami a obrázky  
 Texturami a obrázky se na základní úrovni, pouze tabulky dat, které se používají k zajištění podrobností v grafické aplikace. Druh podrobností, které poskytuje textury nebo image závisí na způsobu jejich použití, ale vzorky barev, hodnoty alfa (průhlednost), normály a výška hodnoty jsou běžné příklady. Hlavní rozdíl mezi textury a obrazu je, že textury smyslem je lze používat společně s reprezentací tvar – obvykle na 3D model – vyjádřit kompletního objektu nebo scény, ale image je obvykle samostatné reprezentace objektu nebo scény .  
  
 Běžné typy textury patří:  
  
 Map textur  
 Map textur obsahovat hodnot barev, které jsou uspořádané jako jeden –, dvou nebo třírozměrných matice. Slouží k poskytnutí detailu barvy na ovlivněného objektu. Barvy jsou běžně kódovaný pomocí kanálů barva RGB (červená, zelená, modrá) a může jich obsahovat čtvrtý kanálu alfa, představující průhlednost. Ne tak často, barvy může být zakódován do jiné barevné schéma nebo čtvrtý kanálu by mohla obsahovat data než alfa – například výška.  
  
 Běžné mapy  
 Map normál obsahovat normály. Používají se k poskytování osvětlení podrobností na ovlivněného objektu. Normály pro každou plochu běžně kódované pomocí komponenty červené, zelené a modré barvu pro ukládání x, y a z dimenzí vektoru. Nicméně existují jiné kódování – například kódování, které jsou založeny na polární souřadnice.  
  
 Výška mapy  
 Výška maps obsahují data výška pole. Se používají k zajištění určitou formu geometrických detailů na ovlivněného objektu – s použitím kódu shaderu pro výpočet požadovaného efektu – nebo k poskytování datových bodů pro použití stejně jako generace terénu. Výška hodnoty jsou běžně kódované pomocí jeden kanál v textuře.  
  
 Mapy krychle  
 Mapy krychle může obsahovat různé typy dat – například barvy nebo normály pro každou plochu, ale jsou uspořádána jako šest textur na plošky krychle. Z tohoto důvodu nejsou zadáním souřadnice textury vzorkovány krychlové mapy, ale zadáním vektor jehož původ center datové krychle; vzorek je v místě, kde vektoru protíná datové krychle. Datová krychle maps se používají k zajištění aproximaci prostředí, které slouží k výpočtu odrazů – to se označuje jako *mapování prostředí*– nebo k poskytování textur na kulovité objekty s méně deformacemi než basic můžete zadat dvojrozměrné textury.  
  
 Všechny textury můžete kódování a komprimovaná řadu způsobů, který je ortogonální k typu dat, který obsahuje textury, nebo dimenzionalitě nebo "tvar" textury. Ale jiné kódování a komprese metody přinést lepší výsledky pro různé druhy dat.  
  
 Můžete použít Editor obrázků pro vytvoření a úprava textury a obrázky takovým způsobem, který vypadat podobně jako ostatní editory obrázků. Editor obrázků také poskytuje mipmapping a další funkce pro použití s 3D grafika a podporuje řadu formátů textur vysoce komprimovaný, hardwarově urychlené, které podporuje rozhraní DirectX.  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Editor obrázků](../designers/image-editor.md)|Popisuje, jak použít Editor obrázků pro práci s texturami a obrázky.|  
|[Příklady editoru obrázků](../designers/image-editor-examples.md)|Obsahuje odkazy na témata, která ukazují, jak provádět běžné úlohy pro zpracování obrázků pomocí editoru obrázků.|
