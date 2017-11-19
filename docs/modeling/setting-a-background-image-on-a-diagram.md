---
title: "Nastavení obrázek na pozadí v diagramu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e334a24c-8521-4072-b50f-e59158dde145
caps.latest.revision: "2"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 13e52e30ebeda4d881474bcf990068d1a92bb7f4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="setting-a-background-image-on-a-diagram"></a>Nastavení obrázku pozadí v diagramu
V [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] vizualizace a modelování SDK, můžete nastavit obrázek pozadí pro generovaný Návrhář pomocí vlastní kód.  
  
## <a name="setting-the-background-image"></a>Nastavení obrázku pozadí  
  
#### <a name="to-set-a-background-image-for-a-generated-designer"></a>Nastavit obrázek pozadí pro generovaný návrháře  
  
1.  Zkopírujte soubor bitové kopie, kterou chcete použít jako na obrázku pozadí do adresáře Dsl\Resources aktuálního projektu.  
  
2.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na složku Dsl\Resources, přejděte na **přidat**a potom klikněte na **existující položka**.  
  
3.  V **přidat existující položku** dialogové okno, přejděte do složky Dsl\Resources.  
  
4.  V **soubory typu** seznamu, klikněte na tlačítko **soubory obrázků**.  
  
5.  Klikněte na soubor obrázku, který jste zkopírovali do adresáře a potom klikněte na **přidat**.  
  
6.  Klikněte pravým tlačítkem na Dsl a klikněte na tlačítko **vlastnosti** otevřete vlastnosti projektu Dsl.  
  
7.  Na **prostředky** , klikněte na **tohoto projektu neobsahuje výchozí soubor prostředků. Chcete-li vytvořit, klikněte sem.**  
  
8.  Přidání souboru bitové kopie do souboru prostředků tak, že přetáhnete na obrázku z **Průzkumníku řešení** do okna prostředků.  
  
9. Otevřete nabídku souborů a klikněte na možnost Uložit vlastnosti projektu.  
  
10. Ověřte, zda je soubor Dsl\Properties\Resources.resx existuje a má soubor Resources.Designer.cs v něm.  
  
11. Pokud chybí Resources.Designer.cs, klikněte na soubor Resources.resx v **Průzkumníku řešení**.  
  
12. V **vlastnosti** nastavte `Custom Tool` vlastnost `ResXFileCodeGenerator`.  
  
13. V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt Dsl, přejděte na **přidat**a klikněte na tlačítko **novou složku**.  
  
14. Název složky **vlastní**.  
  
15. Klikněte pravým tlačítkem na vlastní složku, přejděte na **přidat**a klikněte na tlačítko **novou položku**.  
  
16. V **přidat novou položku** dialogu **šablony** seznamu, klikněte na tlačítko **souboru kódu**.  
  
17. V **název** zadejte `BackgroundImage.cs`a klikněte na tlačítko **přidat**.  
  
18. Zkopírujte následující kód do souboru BackgroundImage.cs, nastavení oboru názvů, název třídy diagram a název zdrojové bitové kopie souboru.  
  
     Nahraďte název třídy částečné diagram, který je definován v Dsl\GeneratedCode\Diagrams.cs "MyDiagramClass". Můžete také načíst správný obor názvů ze souboru Dsl\GeneratedCode\Diagrams.cs.  
  
    ```  
    using System;  
    using Microsoft.VisualStudio.Modeling.Diagrams;  
  
    // Fix the namespace:  
    namespace Fabrikam.MyLanguage  
    {  
      // Fix the Diagram Class name - get it from GeneratedCode\Diagram.cs  
  
      public partial class Language29Diagram  
      {  
        protected override void InitializeInstanceResources()  
        {  
          // Fix the Resources namespace and the Image resource name:  
          ImageField backgroundField = new ImageField("background",  
              Fabrikam.MyLanguage.Properties.Resources.MyPicture);  
  
          backgroundField.DefaultFocusable = false;  
          backgroundField.DefaultSelectable = false;  
          backgroundField.DefaultVisibility = true;  
          backgroundField.DefaultUnscaled = false;  
  
          shapeFields.Add(backgroundField);  
  
          backgroundField.AnchoringBehavior  
            .SetTopAnchor(AnchoringBehavior.Edge.Top, 0.01);  
          backgroundField.AnchoringBehavior  
            .SetLeftAnchor(AnchoringBehavior.Edge.Left, 0.01);  
          backgroundField.AnchoringBehavior  
            .SetRightAnchor(AnchoringBehavior.Edge.Right, 0.01);  
          backgroundField.AnchoringBehavior  
            .SetBottomAnchor(AnchoringBehavior.Edge.Bottom, 0.01);  
  
          base.InitializeInstanceResources();  
        }  
      }  
    }  
    ```  
  
     Další informace o přizpůsobení modelu pomocí programu kódu najdete v tématu [navigace a aktualizace modelu v programovém kódu](../modeling/navigating-and-updating-a-model-in-program-code.md).  
  
## <a name="see-also"></a>Viz také  
 [Definování konektory a obrazců](../modeling/defining-shapes-and-connectors.md)   
 [Přizpůsobení bitové kopie pole a Text](../modeling/customizing-text-and-image-fields.md)   
 [Navigace a aktualizace modelu v programovém kódu](../modeling/navigating-and-updating-a-model-in-program-code.md)   
 [Psaní kódu sestavit si jazyka domény](../modeling/writing-code-to-customise-a-domain-specific-language.md)
 
[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
