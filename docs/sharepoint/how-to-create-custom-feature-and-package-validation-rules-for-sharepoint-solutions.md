---
title: 'Postupy: Vytvoření vlastní funkce a pravidel ověřování balíčku pro řešení služby SharePoint | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, extending deployment
- SharePoint development in Visual Studio, validation rules
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 061a86ee301378bc8b456d370eddd19d2f91bbb6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62966741"
---
# <a name="how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions"></a>Postupy: Vytvoření vlastní funkce a balíku ověřovacích pravidel pro řešení služby SharePoint
  Můžete vytvořit vlastní ověřovací pravidla pro ověření balíčku řešení vygenerované sadou Visual Studio. Na všechny položky této součásti nebo balíčku můžete provést úplné ověření tak, že vyberete **ověřit** v místní nabídce balíčku nebo funkce **PackagingExplorer**. Částečné ověřování se provádí při přidání nového projektu SharePonit nebo funkce na projekt tak, aby určí, jestli balíček nebo funkce by být v platném stavu.

### <a name="to-create-a-custom-package-validation-rule"></a>Chcete-li vytvořit balíček vlastní ověřovací pravidlo

1. Vytvořte projekt knihovny tříd.

2. Přidejte odkazy na následující sestavení:

    - Microsoft.VisualStudio.SharePoint

    - System.ComponentModel.Composition

3. Vytvořte třídu, která implementuje jednu z následujících rozhraní:

    - Chcete-li vytvořit balíček ověřovacího pravidla, implementovat <xref:Microsoft.VisualStudio.SharePoint.Validation.IPackageValidationRule> rozhraní.

    - Chcete-li vytvořit funkci pravidla ověřování, implementovat <xref:Microsoft.VisualStudio.SharePoint.Validation.IFeatureValidationRule> rozhraní.

4. Přidat <xref:System.ComponentModel.Composition.ExportAttribute> do třídy. Tento atribut umožňuje zjišťovat a načíst ověřovací pravidlo Visual Studio. Předání <xref:Microsoft.VisualStudio.SharePoint.Validation.IPackageValidationRule> nebo <xref:Microsoft.VisualStudio.SharePoint.Validation.IFeatureValidationRule> typ konstruktoru atributu.

## <a name="example"></a>Příklad
 Následující příklad kódu ukazuje, jak vytvořit vlastní ověřovací pravidlo funkce.

 [!code-vb[SPExtensibility.FeatureValidation#1](../sharepoint/codesnippet/VisualBasic/featurevalidation/extension/customvalidationrule.vb#1)]
 [!code-csharp[SPExtensibility.FeatureValidation#1](../sharepoint/codesnippet/CSharp/featurevalidation/extension/customfeaturevalidationrule.cs#1)]

## <a name="compile-the-code"></a>Kompilace kódu
 Tento příklad vyžaduje odkazy na následující sestavení:

- Microsoft.VisualStudio.SharePoint.

- System.ComponentModel.Composition.

## <a name="deploy-the-extension"></a>Nasazení rozšíření
 Chcete-li nasadit rozšíření, vytvořte [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)] extension (VSIX) balíčku pro sestavení a všechny další soubory, které chcete distribuovat s příponou. Další informace najdete v tématu [nástroje nasazení rozšíření pro SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).

## <a name="see-also"></a>Viz také:
- [Rozšíření balení a nasazení SharePoint](../sharepoint/extending-sharepoint-packaging-and-deployment.md)
