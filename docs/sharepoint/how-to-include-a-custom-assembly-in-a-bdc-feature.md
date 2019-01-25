---
title: 'Postupy: Zahrnutí vlastního sestavení ve funkci BDC | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.BDC.Add_Assemblies_Dialog
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], add reference
- Business Data Connectivity service [SharePoint development in Visual Studio], custom assembly
- BDC [SharePoint development in Visual Studio], custom assembly
- BDC [SharePoint development in Visual Studio], add reference
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 4effb22f85ed7328a121340124f43b24b09e0ddc
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54870659"
---
# <a name="how-to-include-a-custom-assembly-in-a-bdc-feature"></a>Postupy: Zahrnutí vlastního sestavení ve funkci BDC
  Váš projekt může odkazovat na sestavení z jiných projektů ve stejném řešení. Ale musíte přidat tato sestavení do funkcí souboru projektu pomocí **přiřadit odkazovaná sestavení k objektům LobSystem** dialogové okno.  
  
### <a name="to-include-a-custom-assembly-in-a-business-data-connectivity-bdc-feature"></a>K zahrnutí vlastního sestavení ve funkci business data connectivity (BDC)
  
1.  V **Průzkumníka řešení**, vyberte složku, která obsahuje model služby BDC.  
  
2.  Na **zobrazení** nabídky, klikněte na tlačítko **okno vlastností**.  
  
3.  V **vlastnosti** okna, vyberte **sestavení** vlastnost a potom tlačítko se třemi tečkami (![elipsa ASP.NET – Návrhář mobilních řešení](../sharepoint/media/mwellipsis.gif "technologie ASP.NET Mobile Návrhář Elipsa")).  
  
     **Přiřadit odkazovaná sestavení k objektům LobSystem** zobrazí se dialogové okno.  
  
4.  V **vyberte sestavení** , zvolte vlastní sestavení.  
  
    > [!NOTE]  
    >  Sestavení se zobrazí pouze v **přiřadit odkazovaná sestavení k objektům LobSystem** dialogovému oknu, pokud jste přidali odkaz na projekt, který obsahuje sestavení. Další informace najdete v tématu [jak: Přidání nebo odebrání odkazů pomocí dialogového okna Přidat odkaz](https://msdn.microsoft.com/3bd75d61-f00c-47c0-86a2-dd1f20e231c9).  
  
5.  V **vlastnosti odkazu** seskupit, otevřete seznam, který se zobrazí pro **rozsah objektu LobSystem** vlastnost, zvolte systému LOB z metod, které používají vlastní sestavení a klikněte na tlačítko **OK**  tlačítko.  
  
    > [!NOTE]  
    >  Chcete-li ladit kód v vlastní sestavení, je nutné přidat sestavení do balíčku řešení. Další informace najdete v tématu [jak: Přidání a odebrání dalších sestavení](../sharepoint/how-to-add-and-remove-additional-assemblies.md).  
  
## <a name="see-also"></a>Viz také:
 [Postupy: Určení lokalizovaných názvů, vlastností a oprávnění pomocí zdrojového souboru](../sharepoint/how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions.md)   
 [Postupy: Přidání stávajícího souboru modelu služby BDC do projektu služby SharePoint](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md)   
 [Vytvoření modelu připojení obchodních dat](../sharepoint/creating-a-business-data-connectivity-model.md)   
 [Postupy: Vytvoření modelu služby BDC](../sharepoint/how-to-create-a-bdc-model.md)   
 [Integragte obchodních dat do služby SharePoint](../sharepoint/integrating-business-data-into-sharepoint.md)  
