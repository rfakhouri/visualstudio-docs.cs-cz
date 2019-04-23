---
title: 'Postupy: Vytvoření základní textury shaderu | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 5af113fb-6415-4be0-8b23-10fddb10e80a
caps.latest.revision: 25
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 9dda948921c702367859afe32ad75a7998460587
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60048564"
---
# <a name="how-to-create-a-basic-texture-shader"></a>Postupy: Vytvoření shaderu základní textury
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tento dokument popisuje způsob použití návrháře shaderu a orientovaného grafu shaderu jazyka (DGSL) k vytvoření shaderu textury jedním. Tento shader nastaví konečnou barvu přímo na RGB a alfa hodnot, které jsou odebírána data z textury.  
  
 Tento dokument vysvětluje tyto činnosti:  
  
- Odebrání uzlů z grafu shaderu  
  
- Přidání uzlů do grafu  
  
- Nastavení parametrů shaderu  
  
- Nastavení viditelnost parametru  
  
- Spojující uzly  
  
## <a name="creating-a-basic-texture-shader"></a>Vytvoření shaderu základní textury  
 Basic, jeden textury shaderu můžete implementovat pomocí zápisu hodnoty barev a alfa vzorek textury přímo do konečné výstupní barva.  
  
 Než začnete, ujistěte se, že **vlastnosti** okno a **nástrojů** jsou zobrazeny.  
  
#### <a name="to-create-a-basic-texture-shader"></a>K vytvoření shaderu základní textury  
  
1. Vytvořte shader DGSL pracovat. Informace o tom, jak přidat do projektu DGSL shader naleznete v části Začínáme v [návrháře shaderu](../designers/shader-designer.md).  
  
2. Odstranit **barva bodu** uzlu. V **vyberte** režimu, vyberte **barva bodu** uzel a pak na panelu nabídek zvolte **upravit**, **odstranit**. Díky tomu místo pro uzel, který je přidán v dalším kroku.  
  
3. Přidat **vzorek textury** uzel do grafu. V **nástrojů**v části **textury**vyberte **vzorek textury** a přesuňte jej na návrhovou plochu.  
  
4. Přidat **textury koordinovat** uzel do grafu. V **nástrojů**v části **textury**vyberte **textury koordinovat** a přesuňte jej na návrhovou plochu.  
  
5. Zvolte textury, který chcete použít. V **vyberte** režimu, vyberte **vzorek textury** uzel a pak v **vlastnosti** okno, určete texturu, kterou chcete použít s použitím **název souboru**  vlastnost.  
  
6. Ujistěte se, textury veřejně přístupná. Vyberte **vzorek textury** uzel a pak v **vlastnosti** okno, nastavte **přístup** vlastnost **veřejné**. Nyní textury můžete nastavit od jiného nástroje, jako **editoru modelů**.  
  
7. Souřadnice textury se připojte k vzorek textury. V **vyberte** režimu, přesunout **výstup** z terminálu **koordinovat textury** uzlu **UV** z terminálu **textury Ukázka** uzlu. Toto připojení navzorkuje texturu na zadaných souřadnicích.  
  
8. Vzorek textury se připojte k konečnou barvu. Přesunout **RGB** z terminálu **vzorek textury** uzlu **RGB** z terminálu **konečnou barvu** uzel a potom ho přesuňte **Alfa** z terminálu **vzorek textury** uzlu **alfa** z terminálu **konečnou barvu** uzlu.  
  
   Následující obrázek znázorňuje dokončené shader graf a náhled shaderu použitý pro datovou krychli.  
  
> [!NOTE]
>  Na tomto obrázku rovině slouží jako tvar náhled a byl zadán lépe demonstruje účinek shader textury.  
  
 ![Graf shaderu a náhled vlivu](../designers/media/digit-texture-effect.png "číslice textury efekt")  
  
 Určité tvary můžou poskytovat lepší verze Preview pro některé shadery. Další informace o tom, jak shadery v Návrháři shaderu ve verzi preview, najdete v části [návrháře shaderu](../designers/shader-designer.md)  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Použití shaderu na 3D Model](../designers/how-to-apply-a-shader-to-a-3-d-model.md)   
 [Editor obrázků](../designers/image-editor.md)   
 [Návrhář shaderů](../designers/shader-designer.md)   
 [Uzly návrháře shaderů](../designers/shader-designer-nodes.md)
