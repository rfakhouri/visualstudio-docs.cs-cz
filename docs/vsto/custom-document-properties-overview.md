---
title: "Přehled přizpůsobených vlastností dokumentu | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
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
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 672eaf3ed82a80983b919a37b2aeff4c99621f43
ms.sourcegitcommit: bfa26fd7426af0d065cb2eef3d6827b5d6f7986c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/20/2018
---
# <a name="custom-document-properties-overview"></a>Přehled přizpůsobených vlastností dokumentu

Při sestavování projektu úrovni dokumentu sady Visual Studio přidá dva vlastní vlastnosti dokumentu v projektu: \_AssemblyLocation a \_AssemblyName. Když uživatel otevře dokument, zkontroluje tyto vlastní vlastnosti dokumentu aplikace Microsoft Office. Pokud existují v dokumentu načte aplikaci [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], který spustí přizpůsobení. Další informace najdete v tématu [architektura z řešení pro systém Office v sadě Visual Studio](../vsto/architecture-of-office-solutions-in-visual-studio.md).

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

## <a name="assemblyname"></a>\_AssemblyName

Tato vlastnost obsahuje CLSID rozhraní v řešení Office zavaděč součást [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]. Hodnota CLSID je 4E3C66D5 - 58D 4-491E-A7D4-64AF99AF6E8B. Měli byste nikdy tuto hodnotu změnit.

## <a name="assemblylocation"></a>\_AssemblyLocation

Tato vlastnost obsahuje řetězec, který poskytuje podrobnosti o manifest nasazení pro přizpůsobení. Další informace o manifesty najdete v tématu [aplikace a manifesty nasazení v řešeních pro systém Office](../vsto/application-and-deployment-manifests-in-office-solutions.md).

 Hodnota vlastnosti The_AssemblyLocation může mít různých formátech, v závislosti na tom, jak je řešení nasazeno:

- Pokud řešení je publikována, které budou instalovány z webu, cesta UNC nebo jednotku CD nebo USB, vlastnost _AssemblyLocation má formát *DeploymentManifestPath*|*SolutionID*. Následující řetězec je příklad:

     file://deployserver/MyShare/ExcelWorkbook1.vsto|74744e4b-e4d6-41eb-84f7-ad20346fe2d9

- Pokud jsou spuštěna nebo ladění řešení ze sady Visual Studio, vlastnost _AssemblyLocation má formát *DeploymentManifestName*|*SolutionID*| vstolocal. Následující řetězec je příklad:

     ExcelWorkbook1.vsto|74744e4b-e4d6-41eb-84f7-ad20346fe2d9|vstolocal

 *SolutionID* je identifikátor GUID, [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] používá k identifikaci řešení. *SolutionID* se automaticky generuje při sestavování projektu. **Vstolocal** termín ukazuje [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] že ze stejné složky jako dokument by měl být načíst sestavení.

## <a name="see-also"></a>Viz také

[Architektura řešení pro systém Office v sadě Visual Studio](../vsto/architecture-of-office-solutions-in-visual-studio.md)
[architektura přizpůsobení na úrovni dokumentu](../vsto/architecture-of-document-level-customizations.md)
[aplikace a nasazení manifesty v řešeních pro systém Office ](../vsto/application-and-deployment-manifests-in-office-solutions.md) 
 [Postupy: publikování řešení Office s použitím technologie ClickOnce](http://msdn.microsoft.com/en-us/2b6c247e-bc04-4ce4-bb64-c4e79bb3d5b8)
[postupy: vytváření a změny přizpůsobených vlastností dokumentu](../vsto/how-to-create-and-modify-custom-document-properties.md)
