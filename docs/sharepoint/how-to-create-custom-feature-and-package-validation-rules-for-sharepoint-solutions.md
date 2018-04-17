---
title: 'Postupy: vytvoření vlastní funkce a pravidel ověřování balíčku pro řešení služby SharePoint | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, extending deployment
- SharePoint development in Visual Studio, validation rules
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0c68df756e24fc45603d34dd6982a09889bd5203
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions"></a>Postupy: Vytvoření vlastní funkce a pravidel ověřování balíčku pro řešení služby SharePoint
  Můžete vytvořit vlastní pravidla ověřování k ověření balíčku řešení vytvořen sadou Visual Studio. Můžete provést úplné ověřování na celou funkci nebo balíčku výběrem **ověřením** v místní nabídce balíček nebo funkce v **PackagingExplorer**. Částečné ověřování se provádí při přidání nového projektu SharePonit nebo funkce projektu k určení, pokud na balíček nebo funkce bude v platném stavu.  
  
### <a name="to-create-a-custom-package-validation-rule"></a>Chcete-li vytvořit vlastní balíček ověřovacího pravidla  
  
1.  Vytvoření projektu knihovny tříd.  
  
2.  Přidejte odkazy na následující sestavení:  
  
    -   Microsoft.VisualStudio.SharePoint  
  
    -   System.ComponentModel.Composition  
  
3.  Vytvořte třídu, která provádí jednu z následujících rozhraní:  
  
    -   Chcete-li vytvořit balíček ověřovacího pravidla, implementujte <xref:Microsoft.VisualStudio.SharePoint.Validation.IPackageValidationRule> rozhraní.  
  
    -   Pokud chcete vytvořit funkci pravidla ověřování, implementovat <xref:Microsoft.VisualStudio.SharePoint.Validation.IFeatureValidationRule> rozhraní.  
  
4.  Přidat <xref:System.ComponentModel.Composition.ExportAttribute> k třídě. Tento atribut umožňuje sadě Visual Studio pro zjišťování a načtení ověřovacího pravidla. Předat <xref:Microsoft.VisualStudio.SharePoint.Validation.IPackageValidationRule> nebo <xref:Microsoft.VisualStudio.SharePoint.Validation.IFeatureValidationRule> typ do konstruktoru atributu.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak vytvořit vlastní funkci pravidla ověřování.  
  
 [!code-vb[SPExtensibility.FeatureValidation#1](../sharepoint/codesnippet/VisualBasic/featurevalidation/extension/customvalidationrule.vb#1)]
 [!code-csharp[SPExtensibility.FeatureValidation#1](../sharepoint/codesnippet/CSharp/featurevalidation/extension/customfeaturevalidationrule.cs#1)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje odkazy na následující:  
  
-   Microsoft.VisualStudio.SharePoint.  
  
-   System.ComponentModel.Composition.  
  
## <a name="deploying-the-extension"></a>Nasazení rozšíření  
 Chcete-li nasadit rozšíření, vytvořte [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] balíček rozšíření (VSIX) pro sestavení a všechny další soubory, které chcete distribuovat s rozšířením. Další informace najdete v tématu [nasazení rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření balení a nasazení SharePoint](../sharepoint/extending-sharepoint-packaging-and-deployment.md)  
  
  