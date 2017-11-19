---
title: "Přehled nástrojů návrhu modelu služby BDC | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.SharePointTools.BDC.Method_Details
- VS.SharePointTools.BDC.Explorer
- VS.SharePointTools.BDC.Diagram
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], visual tools
- Business Data Connectivity service [SharePoint development in Visual Studio], visual tools
- Business Data Connectivity service [SharePoint development in Visual Studio], BDC Explorer
- BDC [SharePoint development in Visual Studio], method details
- Business Data Connectivity service [SharePoint development in Visual Studio], designer
- Business Data Connectivity service [SharePoint development in Visual Studio], method details
- BDC [SharePoint development in Visual Studio], BDC Explorer
- BDC [SharePoint development in Visual Studio], designer
ms.assetid: dbd7b746-9e93-4ed4-a546-4a6f17a4725f
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: eaf6871f7ad9316ba2dbdaa8fa29b4810b1d6a3d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="bdc-model-design-tools-overview"></a>Přehled nástrojů pro navrhování modelů služby BDC
  Business Data Connectivity (BDC) modelu můžete navrhnout pomocí návrháře BDC **podrobnosti o metodě BDC** okně a **Průzkumník modelu BDC**.  
  
 **Průzkumník modelu BDC** umožňuje procházet modelu, hledání modelu a definovat typ popisovače.  
  
## <a name="bdc-designer"></a>Návrhář BDC  
 Návrhář BDC umožňuje definovat entity v modelu a vizuálně uspořádat jejich vztahů s jednu na druhou. Použijte Návrháře BDC k provádění následujících úloh:  
  
-   Přidání entity do modelu.  
  
-   Odeberte entit z modelu.  
  
-   Definujte vztahy mezi entitami.  
  
 Otevřete návrháře BDC, poklikejte na soubor modelu ve vašem projektu nebo otevřete místní nabídky souboru modelu a potom zvolte **otevřete**. Přidání entity do modelu přetažením nebo kopírování **Entity** z **sada nástrojů** do návrháře. K vytvoření přidružení mezi dvěma entitami, vyberte **přidružení** řídit ve **sada nástrojů**, zvolte první entity a potom vyberte druhý entity.  
  
## <a name="bdc-method-details-window"></a>Okno podrobností BDC – metoda  
 Použití **podrobnosti o metodě BDC** okno Definovat parametry, instance, a filtrovat popisovačů metody.  
  
 Můžete rychle vytvořit metody vyhledávací, specifická metoda Finder, Creator, aktualizační a metoda odstranění v **podrobnosti o metodě BDC** okno. Při generování těchto metod, Visual Studio přidá metadata, například parametry, instancí a typ popisovače metodě. Tato metadata pro uspokojení konkrétní scénář, můžete upravit.  
  
 Chcete-li otevřít **podrobnosti o metodě BDC** okně na řádku nabídek zvolte **zobrazení**, **ostatní okna**, **podrobnosti o metodě BDC**.  
  
 Chcete-li zobrazit metody v **podrobnosti o metodě BDC** okně zvolte entity v Návrháři BDC. Metody vybrané entity se zobrazí v **podrobnosti o metodě BDC** okno. Pokud jste nezvolili entity v Návrháři BDC **podrobnosti o metodě BDC** zobrazují žádné informace.  
  
 Rozbalit nebo sbalit uzly v **podrobnosti o metodě BDC** okno Definovat parametry, instance, a filtrovat popisovače. Použití **Průzkumník modelu BDC** zadat typ popisovače.  
  
## <a name="bdc-explorer"></a>Průzkumník modelu BDC  
 **Průzkumník modelu BDC** zobrazí prvky, které tvoří modelu. Chcete-li otevřít **Průzkumník modelu BDC**, na řádku nabídek zvolte **zobrazení**, **ostatní okna**, **Průzkumník modelu BDC**. Chcete-li procházet modelu, rozbalte uzly v **Průzkumník modelu BDC**. Každý uzel reprezentuje element v souboru XML souboru modelu.  
  
 Jako zvolte uzly v **Průzkumník modelu BDC**, vlastnosti každého uzlu, který zvolíte, se zobrazí v **vlastnosti** okno. Mnoho z těchto vlastností odpovídají atributy v souboru modelu. Pomocí vyhledávacího pole v horní části lze vyhledat modelu **Průzkumník modelu BDC**.  
  
> [!NOTE]  
>  **Průzkumník modelu BDC** není zobrazit identifikátory, vlastní vlastnosti, lokalizované řetězce, přidružení skupiny, akce, deskriptory filtrů, seznamy řízení akce a výchozí hodnoty parametrů.  
  
### <a name="defining-type-descriptors"></a>Definování popisovače typu  
 Použití **Průzkumník modelu BDC** zadat typ popisovače. Průzkumník modelu BDC umožňuje definovat popisovač typu jednou a potom budou používat tento popisovač typu jinde v modelu. K tomu, popisovač typu zkopírujte a vložte jej do druhý parametr nebo zadejte popisovač.  
  
> [!NOTE]  
>  Změny popisovač původní typ neovlivňují kopie tento popisovač typu.  
  
 Další informace najdete v tématu [postupy: definování deskriptoru typu pro parametr](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytvoření modelu služby BDC](../sharepoint/how-to-create-a-bdc-model.md)   
 [Postupy: Přidání Entity do modelu](../sharepoint/how-to-add-an-entity-to-a-model.md)   
 [Postupy: přidání vyhledávací metody](../sharepoint/how-to-add-a-finder-method.md)   
 [Postupy: Přidání specifické vyhledávací metody](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [Postupy: přidání metody vytvoření](../sharepoint/how-to-add-a-creator-method.md)   
 [Postupy: přidání metody odstranění](../sharepoint/how-to-add-a-deleter-method.md)   
 [Postupy: Přidání aktualizační metody](../sharepoint/how-to-add-an-updater-method.md)   
 [Vytvoření přidružení mezi entitami](../sharepoint/creating-an-association-between-entities.md)   
 [Návod: Vytvoření externího seznamu ve službě SharePoint s použitím obchodních dat](../sharepoint/walkthrough-creating-an-external-list-in-sharepoint-by-using-business-data.md)   
 [Integrace obchodních dat do služby SharePoint](../sharepoint/integrating-business-data-into-sharepoint.md)   
 [Vytvoření modelu připojení obchodních dat](../sharepoint/creating-a-business-data-connectivity-model.md)   
 [Navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md)  
  
  