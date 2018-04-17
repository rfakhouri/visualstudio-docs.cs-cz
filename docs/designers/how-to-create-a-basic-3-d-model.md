---
title: 'Postupy: vytvoření základního modelu 3D | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-designers
ms.topic: conceptual
ms.assetid: a0d97966-2df8-449b-a8cf-5a19684dc773
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5b61ebe27209b80873ba5e7f751c70c106f6aab0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-a-basic-3-d-model"></a>Postupy: Vytvoření základního 3D modelu
Tento dokument ukazuje, jak vytvořit základní 3D modelu pomocí editoru modelu.  
  
 Tento dokument ukazuje tyto aktivity:  
  
-   Přidání objektů do scény  
  
-   Výběr řezy a okraje  
  
-   Výběr překladu  
  
-   Pomocí **Rozdělit vzhled** a **tvarování vzhled** nástroje  
  
-   Pomocí **Triangulate** příkaz  
  
## <a name="creating-a-basic-3-d-model"></a>Vytvoření základního modelu 3D  
 Editor modelu můžete vytvářet a upravovat 3D modely a scény pro hry nebo aplikace. Následující kroky ukazují, jak vytvořit jednoduchý model 3D domu pomocí editoru modelu. Zjednodušený model slouží jako stand-in pro konečné obrázky prostředky, které jsou stále probíhá vytváření, jako mřížku pro detekce kolizí nebo nízké podrobností model má být použita, pokud objekt, který reprezentuje je příliš daleko abyste mohli využívat výhod vykreslování podrobnější.  
  
 Jakmile budete hotovi, modelu by měl vypadat přibližně takto:  
  
 ![Dokončené model zjednodušené úklidové](../designers/media/gfx_model_demo_house_final.png "gfx_model_demo_house_final")  
  
 Než začnete, ujistěte se, že **vlastnosti** okno a **sada nástrojů** jsou zobrazeny.  
  
#### <a name="to-create-a-simplified-3-d-model-of-a-house"></a>Pro vytvoření modelu zjednodušené 3D domu  
  
1.  Vytvořte 3D model pro práci s. Informace o tom, jak přidat model do projektu, najdete v části Začínáme v [modelu Editor](../designers/model-editor.md).  
  
2.  Přidejte do scény datovou krychli. V **sada nástrojů** okno, v části **tvarů**, vyberte **datové krychle** a poté ho přesuňte na plochu návrháře.  
  
3.  Umožňuje přepnout do vzhled výběru. Na panelu nástrojů editoru modelu zvolte **vyberte vzhled**.  
  
4.  Rozdělit horní části datové krychle. V režimu výběru řez zvolte datové krychle jednou aktivace pro výběr a zvolte horní části datové krychle vyberte nejvyšší písmo. Na panelu nástrojů editoru modelu zvolte **Rozdělit vzhled**. Tento postup přidá novou vrcholy do horní části datové krychle, která rozdělená do čtyř oddílů stejně velké.  
  
     ![Horní části datové krychle se dělí](../designers/media/gfx_model_demo_house_subdiv.png "gfx_model_demo_house_subdiv")  
  
5.  Tvarování sociálními přiléhající datové krychle – například přední a pravé straně datové krychle. V režimu výběru řez zvolte datové krychle jednou aktivovat pro výběr a potom vyberte jedné straně datové krychle. Stiskněte a přidržte klávesu ovládací prvek, zvolte jiné straně sousedícího na straně, které jste vybrali nejprve datové krychle a na panelu nástrojů editoru modelu zvolte **tvarování vzhled**.  
  
     ![Mít byla vyňaty postranní datové krychle](../designers/media/gfx_model_demo_house_extrude.png "gfx_model_demo_house_extrude")  
  
6.  Jeden z extrusions rozšiřte. Vyberte jednu z řezy, které jste právě vyňaty a potom na panelu nástrojů editoru modelu zvolte **přeložit** nástroje a přesunout manipulator překlad ve stejném směru jako vysunutí.  
  
     ![Další má byla vyňaty jedné straně datové krychle. ] (../designers/media/gfx_model_demo_house_extend.png "gfx_model_demo_house_extend")  
  
7.  Triangulovat modelu. Na panelu nástrojů editoru modelu zvolte **Upřesnit**, **nástroje**, **Triangulate**.  
  
8.  Vytvořte stropu budovy. Přepnout na režim výběru edge tak, že zvolíte **vyberte okraj** na panelu nástrojů editoru modelu a potom vyberte datovou krychli aktivovat. Stiskněte a přidržte klávesu ovládací prvek, při výběru okrajů, které jsou zobrazeny zde:  
  
     ![Okraje, které budou formovat ve špičce z stropu](../designers/media/gfx_model_demo_house_edges.png "gfx_model_demo_house_edges")  
  
     Když jsou vybrané okrajů, na panelu nástrojů editoru modelu, vyberte **přeložit** nástroje a poté přesuňte manipulator překlad směrem nahoru k vytvoření stropu budovy.  
  
 Zjednodušená úklidové modelu je dokončena. Tady je poslední model znovu s konstantní stínování použít:  
  
 ![Dokončené model zjednodušené úklidové](../designers/media/gfx_model_demo_house_final.png "gfx_model_demo_house_final")  
  
 Jako další krok můžete použít shaderu k tomuto 3D modelu. Informace najdete v tématu [postupy: použití shaderu 3D modelu](../designers/how-to-apply-a-shader-to-a-3-d-model.md).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Model 3D geologické struktury](../designers/how-to-model-3-d-terrain.md)   
 [Editor modelu](../designers/model-editor.md)   
 [Návrhář shaderů](../designers/shader-designer.md)