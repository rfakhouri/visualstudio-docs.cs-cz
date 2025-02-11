---
title: 'Postupy: Vytvoření základního Lambertova shaderu | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: ec5c10fb-9600-4240-8280-d59451ea1d68
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 227c9c84022e3c3340b4821df9dbd2dbe9465a03
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63414690"
---
# <a name="how-to-create-a-basic-lambert-shader"></a>Postupy: Vytvoření základního Lambertova shaderu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tento dokument popisuje způsob použití návrháře shaderu a orientovaného grafu shaderu jazyka (DGSL) k vytvoření, který implementuje klasického modelu osvětlení Lambert osvětlení shaderu.  
  
 Tento dokument vysvětluje tyto činnosti:  
  
- Přidání uzlů do grafu shaderu  
  
- Odpojuje se uzly  
  
- Spojující uzly  
  
## <a name="the-lambert-lighting-model"></a>Lambertova modelu osvětlení  
 Model osvětlení Lambert zahrnuje okolí a směrové světlo na odstín objekty ve 3D scéně. Ambientní komponenty poskytují základní úroveň osvětlení ve 3D scéně. Směrové komponenty nabízejí další osvětlení z směrové zdroje (vzdálené) světla. Ambientní osvětlení má vliv na všechny plochy ve scéně stejně, bez ohledu na jejich orientace. Pro daný plochu je produkt okolní barvy na povrchu a barvy a intenzitu zrcadlových osvětlením okolí ve scéně. Směrové světlo ovlivňuje všechny oblasti ve scéně odlišně, na základě orientace povrchu s ohledem na směru světla. Je produkt barvy rozptýlení a orientaci ovládacího prvku na plochu a barvu, intenzity a směr světla zdrojů. Zařízení Surface směřujících přímo ke zdroji světla získat maximální příspěvek a povrchy směřujících přímo okamžitě obdržet žádná příspěvek. V části Lambertova modelu osvětlení okolí komponenty a jednu nebo více komponent směrové kombinovat určit příspěvek celkový rozptýlení barvy pro každý bod na objekt.  
  
 Než začnete, ujistěte se, že **vlastnosti** okno a **nástrojů** jsou zobrazeny.  
  
#### <a name="to-create-a-lambert-shader"></a>Chcete-li vytvořit Lambertova shaderu  
  
1. Vytvořte shader DGSL pracovat. Informace o tom, jak přidat do projektu DGSL shader naleznete v části Začínáme v [návrháře shaderu](../designers/shader-designer.md).  
  
2. Odpojte **barva bodu** uzlu z **konečnou barvu** uzlu. Zvolte **RGB** z terminálu **barva bodu** uzel a klikněte na tlačítko **přerušit odkazy**. Nechte **alfa** terminálu připojen.  
  
3. Přidat **Lambertova** uzel do grafu. V **nástrojů**v části **nástroj**vyberte **Lambertova** a přesuňte jej na návrhovou plochu. Uzel lambertova vypočítá podíl celkové rozptýlení barvy pixelu na základě parametrů osvětlením okolí a difúzním.  
  
4. Připojení **barva bodu** uzlu **Lambertova** uzlu. V **vyberte** režimu, přesunout **RGB** z terminálu **barva bodu** uzlu **rozptýlit barvu** z terminálu **Lambertova**  uzlu. Toto připojení obsahuje uzel lambertova s interpolovanými barvy rozptýlení pixelu.  
  
5. Hodnota počítaného barvy se připojte k konečnou barvu. Přesunout **výstup** z terminálu **Lambertova** uzlu **RGB** z terminálu **konečnou barvu** uzlu.  
  
   Následující obrázek znázorňuje dokončené shader graf a náhled shaderu použité pro model čajové konvice.  
  
> [!NOTE]
> K předvedení lépe efekt shaderu na tomto obrázku, byl zadán oranžové barvy s použitím **MaterialDiffuse** parametr shaderu. Hry nebo aplikace můžete použít tento parametr slouží k poskytování hodnotu barvy jedinečný pro každý objekt. Informace o parametrech materiálu, naleznete v části Náhled shadery v [návrháře shaderu](../designers/shader-designer.md).  
  
 ![Graf shaderu a jeho účinkem ve verzi preview. ](../designers/media/digit-lambert-effect-graph.png "Číslice Lambertova efekt grafu")  
  
 Určité tvary můžou poskytovat lepší verze Preview pro některé shadery. Další informace o tom, jak shadery v Návrháři shaderu ve verzi preview, najdete v části Náhled shadery v [návrháře shaderu](../designers/shader-designer.md).  
  
 Následující obrázek znázorňuje shaderu, který je popsaný v tomto dokumentu se použijí na 3D model.  
  
 ![Osvětlení Lambert k modelu. ](../designers/media/digit-lambert-effect-result.png "Číslice Lambertova efekt výsledků")  
  
 Další informace o tom, jak použití shaderu na 3D model, najdete v části [jak: Použití shaderu na 3D Model](../designers/how-to-apply-a-shader-to-a-3-d-model.md).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Použití shaderu na 3D Model](../designers/how-to-apply-a-shader-to-a-3-d-model.md)   
 [Postupy: Exportování shaderu](../designers/how-to-export-a-shader.md)   
 [Postupy: Vytvoření základního Phongova shaderu](../designers/how-to-create-a-basic-phong-shader.md)   
 [Návrhář shaderů](../designers/shader-designer.md)   
 [Uzly návrháře shaderů](../designers/shader-designer-nodes.md)
