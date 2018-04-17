---
title: 'Postupy: Model 3D geologické struktury | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-designers
ms.topic: conceptual
ms.assetid: f779b1fd-82a9-4a11-8ab7-c1c9caabc883
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ec1cf2d86ddb052b1f12310fb80d192aee080596
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-model-3-d-terrain"></a>Postupy: Modelování 3D terénu
Tento dokument ukazuje, jak použití editoru Model pro vytvoření modelu 3D geologické struktury.  
  
 Tento dokument ukazuje tyto aktivity:  
  
-   Přidání objektů do scény  
  
-   Výběr řezy a body  
  
-   Výběr překladu  
  
-   Pomocí **Rozdělit vzhled** nástroj  
  
-   Počet rámců objekt v návrhové plochy  
  
## <a name="creating-a-3-d-terrain-model"></a>Vytvoření modelu 3D geologické struktury  
 3D geologické struktury můžete vytvořit tak, že roviny zajistit další řezy rozdělení sítě SAN a pak manipulace s jejich vrcholy vytvořit zajímavé funkce geologické struktury.  
  
 Jakmile budete hotovi, modelu by měl vypadat přibližně takto:  
  
 ![3&#45;scény D, který znázorňuje model geologické struktury](../designers/media/digit-terrain-model.png "číslice. geologické struktury modelu")  
  
 Než začnete, ujistěte se, že **vlastnosti** okno a **sada nástrojů** jsou zobrazeny.  
  
#### <a name="to-create-a-3-d-terrain-model"></a>Pro vytvoření modelu 3D geologické struktury  
  
1.  Vytvořte 3D model pro práci s. Informace o tom, jak přidat model do projektu, najdete v části Začínáme v [modelu Editor](../designers/model-editor.md).  
  
2.  Přidejte do roviny scény. V **sada nástrojů**v části **tvarů**, vyberte **roviny** a přesunout ho na plochu návrháře.  
  
    > [!TIP]
    >  Usnadnění roviny objekt pro práci s může být rámce v návrhové ploše. V **vyberte** režimu, vyberte objekt roviny a potom na panelu nástrojů editoru modelu, vyberte **rámce objekt** tlačítko.  
  
3.  Zadejte režim vzhled výběru. Na panelu nástrojů editoru modelu zvolte **vyberte vzhled**.  
  
4.  Rozdělit plochy. V režimu výběru řez zvolte roviny jednou aktivace pro výběr a potom zvolte jej znovu a vyberte jeho pouze vzhled. Na panelu nástrojů editoru modelu zvolte **Rozdělit vzhled**. Tento postup přidá novou vrcholy do roviny, která rozdělená do čtyř oddílů stejně velké.  
  
5.  Vytvořte více dílčích dělení. S novou řezy stále vybrán, zvolte **Rozdělit vzhled** dvakrát. Tím se vytvoří celkem 64 řezy. Vytvořením více dílčích dělení můžete udělit geologické struktury více podrobností.  
  
6.  Zadejte režim výběru bodu. Na panelu nástrojů editoru modelu zvolte **vyberte bod**.  
  
7.  Změňte bod pro vytvoření funkce geologické struktury. V režimu výběru bod, vyberte jeden z bodů a potom na panelu nástrojů editoru modelu, vyberte **přeložit** nástroj. Pole, která představuje bod se zobrazí na návrhovou plochu. Použijte na zelenou šipku přesunout pole a tím změnit výška bodu. Opakujte tento krok pro různé body k vytvoření zajímavé funkce geologické struktury.  
  
    > [!TIP]
    >  Můžete vybrat několik bodů najednou o jejich úpravu jednotným způsobem.  
  
 Model geologické struktury je dokončena. Tady je poslední model znovu s Phong stínování použít:  
  
 ![3&#45;scény D, který znázorňuje model geologické struktury](../designers/media/digit-terrain-model.png "číslice. geologické struktury modelu")  
  
 Tento model geologické struktury můžete použít k předvedení efektu barevného přechodu shaderu, která je popsána v [postupy: vytvoření přechodu shaderu na základě geometrie](../designers/how-to-create-a-geometry-based-gradient-shader.md).  
  
## <a name="see-also"></a>Viz také  
 [Editor modelů](../designers/model-editor.md)