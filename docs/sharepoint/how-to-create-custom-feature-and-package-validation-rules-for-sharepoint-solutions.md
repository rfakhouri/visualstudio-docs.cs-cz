---
title: "Postupy: vytvoření vlastní funkce a pravidel ověřování balíčku pro řešení služby SharePoint | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, extending deployment
- SharePoint development in Visual Studio, validation rules
ms.assetid: 17e818f8-0f3a-4a96-a6fc-1634ddb4825d
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 20a56a2f6582a08270292cd86cf62a9344d8565f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
  
  