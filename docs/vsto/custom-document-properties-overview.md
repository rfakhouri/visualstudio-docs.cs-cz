---
title: Přehled přizpůsobených vlastností dokumentu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], custom properties
- custom document properties
- document-level customizations [Office development in Visual Studio], custom properties
- Office documents [Office development in Visual Studio], custom properties
- _AssemblyLocation property
- _AssemblyName property
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 7b3f4038a05478d8e2d747efa700c7ece02e4827
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62951181"
---
# <a name="custom-document-properties-overview"></a>Přehled přizpůsobených vlastností dokumentu

Při vytváření projektu úrovni dokumentu, Visual Studio přidá do dokumentu v projektu dvě vlastní vlastnosti: \_AssemblyLocation a \_AssemblyName. Když uživatel otevře dokument, zkontroluje tyto přizpůsobených vlastností dokumentu aplikace Microsoft Office. Pokud existují v dokumentu, načtení aplikace [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], které spustí vlastní nastavení. Další informace najdete v tématu [řešení architektury systému Office v sadě Visual Studio](../vsto/architecture-of-office-solutions-in-visual-studio.md).

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

## <a name="assemblyname"></a>\_AssemblyName

Tato vlastnost obsahuje identifikátor CLSID rozhraní v součásti zavaděče řešení Office z [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]. Identifikátor CLSID hodnotu 4E3C66D5 58D 4-491E-A7D4-64AF99AF6E8B. Tato hodnota by měla nikdy nezmění.

## <a name="assemblylocation"></a>\_AssemblyLocation

Tato vlastnost obsahuje řetězec, který obsahuje podrobné informace o manifestu nasazení pro přizpůsobení. Další informace o manifestech najdete v tématu [aplikace a manifestů nasazení v řešeních pro systém Office](../vsto/application-and-deployment-manifests-in-office-solutions.md).

 \_Hodnota vlastnosti AssemblyLocation může mít různé formáty, v závislosti na tom, jak se řešení nasadí:

- Pokud toto řešení je publikována z webové stránky, cesta UNC nebo jednotka CD nebo USB, vlastnosti _AssemblyLocation má formát *DeploymentManifestPath*|*SolutionID*. Tento řetězec je příklad:

     file://deployserver/MyShare/ExcelWorkbook1.vsto|74744e4b-e4d6-41eb-84f7-ad20346fe2d9

- Při spuštění nebo ladění řešení v sadě Visual Studio, vlastnosti _AssemblyLocation má formát *DeploymentManifestName*|*SolutionID*| vstolocal. Tento řetězec je příklad:

     ExcelWorkbook1.vsto|74744e4b-e4d6-41eb-84f7-ad20346fe2d9|vstolocal

  *SolutionID* je identifikátor GUID, který [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] používá k identifikaci řešení. *SolutionID* se automaticky vygeneruje při sestavení projektu. **Vstolocal** označuje termín [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] , sestavení by měl být načteno ze stejné složky jako dokument.

## <a name="see-also"></a>Viz také:

- [Architektura řešení pro Office v sadě Visual Studio](../vsto/architecture-of-office-solutions-in-visual-studio.md)
- [Architektura přizpůsobení na úrovni dokumentu](../vsto/architecture-of-document-level-customizations.md)
- [Manifesty aplikace a nasazení v řešeních pro systém Office](../vsto/application-and-deployment-manifests-in-office-solutions.md)
- [Postupy: Publikování řešení Office s použitím technologie ClickOnce](https://msdn.microsoft.com/2b6c247e-bc04-4ce4-bb64-c4e79bb3d5b8)
- [Postupy: Vytvoření a změny přizpůsobených vlastností dokumentu](../vsto/how-to-create-and-modify-custom-document-properties.md)
