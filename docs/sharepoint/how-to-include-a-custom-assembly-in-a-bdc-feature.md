---
title: "Postupy: zahrnutí vlastního sestavení ve funkci BDC | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.SharePointTools.BDC.Add_Assemblies_Dialog
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], add reference
- Business Data Connectivity service [SharePoint development in Visual Studio], custom assembly
- BDC [SharePoint development in Visual Studio], custom assembly
- BDC [SharePoint development in Visual Studio], add reference
ms.assetid: 2ddf44b9-5f51-4bca-b8bb-94c4bbd1c5f3
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c5916da8b7aa5018824ffe8040e7184fe6d1bf31
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-include-a-custom-assembly-in-a-bdc-feature"></a>Postupy: Zahrnutí vlastního sestavení ve funkci BDC
  Projekt odkazovat z jiných projektů ve stejném řešení sestavení. Ale musíte přidat tyto sestavení do souboru funkce projektu pomocí **přiřazení odkazovaná sestavení do LobSystems** dialogové okno.  
  
### <a name="to-include-a-custom-assembly-in-a-business-data-connectivity-bdc-feature"></a>K zahrnutí vlastního sestavení ve funkci Business Data Connectivity (BDC)  
  
1.  V **Průzkumníku**, vyberte složku, která obsahuje modelu služby BDC.  
  
2.  Na **zobrazení** nabídky, klikněte na tlačítko **vlastnosti – okno**.  
  
3.  V **vlastnosti** okně zvolte **sestavení** vlastnost a potom tlačítko se třemi tečkami (![ASP.NET – Návrhář mobilních řešení elipsy](../sharepoint/media/mwellipsis.gif "ASP.NET Mobile Návrhář elipsy")).  
  
     **Přiřazení odkazovaná sestavení do LobSystems** zobrazí se dialogové okno.  
  
4.  V **vybrat sestavení** vyberte vlastní sestavení.  
  
    > [!NOTE]  
    >  Sestavení jsou zobrazeny pouze ve **přiřazení odkazovaná sestavení do LobSystems** dialogové okno Pokud jste přidali odkaz na projekt, který obsahuje sestavení. Další informace najdete v tématu [postupy: Přidání nebo odebrání odkazů pomocí dialogového okna Přidat odkaz na](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9).  
  
5.  V **vlastnosti odkazu** skupiny, otevřete seznam, který se zobrazí pro **LobSystem oboru** vlastnost, zvolte systém LOB metod, které používají vlastní sestavení a potom vyberte **OK**  tlačítko.  
  
    > [!NOTE]  
    >  Pokud chcete ladit kód v vlastní sestavení, je nutné přidat sestavení balíčku řešení. Další informace najdete v tématu [postupy: Přidání a odebrání dalších sestavení](../sharepoint/how-to-add-and-remove-additional-assemblies.md).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: určení lokalizovaných názvů, vlastností a oprávnění pomocí zdrojového souboru](../sharepoint/how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions.md)   
 [Postupy: Přidání stávajícího souboru modelu služby BDC do projektu služby SharePoint](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md)   
 [Vytvoření modelu připojení obchodních dat](../sharepoint/creating-a-business-data-connectivity-model.md)   
 [Postupy: vytvoření modelu služby BDC](../sharepoint/how-to-create-a-bdc-model.md)   
 [Integrace obchodních dat do služby SharePoint](../sharepoint/integrating-business-data-into-sharepoint.md)  
  
  