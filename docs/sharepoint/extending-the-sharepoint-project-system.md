---
title: "Rozšíření systému projektu služby SharePoint | Microsoft Docs"
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
- SharePoint development in Visual Studio, extending projects
- SharePoint development in Visual Studio, extending project items
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: e79808ef9d5d4712d67426b202046615c8ab14b2
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="extending-the-sharepoint-project-system"></a>Rozšíření systému projektu služby SharePoint
  Řešení služby SharePoint můžete vytvořit pomocí sadu šablony projektů a šablon položek v sadě Visual Studio. Tyto šablony požadavkům mnoho vývojové scénáře, ale může v některých případech, kde není poskytují funkce, které budete potřebovat zjistíte. V těchto případech můžete rozšíření systému projektu služby SharePoint.  
  
## <a name="overview-of-the-sharepoint-project-system"></a>Přehled systému projektu služby SharePoint  
 Systém projektu služby SharePoint je založen na základní součásti *SharePoint – položky projektu*. Položky projektu služby SharePoint představuje jediné přizpůsobení SharePoint, například definice seznamu, webové části nebo typ obsahu.  
  
 Projektu služby SharePoint je projekt sady Visual Studio, která zahrnuje jednu nebo více položek projektu služby SharePoint. Projekty SharePoint obsahovat také další součásti, které definují způsob seskupení položek projektu do funkce a balíčky pro nasazení.  
  
 Další informace o obsahu SharePoint – položky projektu a projektů služby SharePoint, naleznete v části [vytváření šablon položek a šablony projektů pro položky projektu služby SharePoint](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md).  
  
## <a name="how-to-extend-the-sharepoint-project-system"></a>Postup rozšíření systému projektu služby SharePoint  
 Systému projektu služby SharePoint můžete rozšířit následujícími způsoby:  
  
-   Definování vlastních typů položek projektu služby SharePoint a přidružit je k nové položky šablony nebo šablony projektů v sadě Visual Studio. Můžete například definovat typu položky projektu služby SharePoint pro vytvoření vlastní akce ani pole. Další informace najdete v tématu [definování vlastní SharePoint typů položek projektu](../sharepoint/defining-custom-sharepoint-project-item-types.md).  
  
-   Rozšíření typů položek projektu služby SharePoint, které již jsou nainstalovány v sadě Visual Studio. Například můžete přidat položky místní nabídky do položky projektu v **Průzkumníku řešení** a přizpůsobit položku projekt, když vývojář vybere položku nabídky. Další informace najdete v tématu [rozšíření položky projektu služby SharePoint](../sharepoint/extending-sharepoint-project-items.md).  
  
-   Rozšíření projektů služby SharePoint. Například můžete přidat obslužné rutiny událostí k provádění specifických úloh, když položky jsou přidány nebo odebrány z projektů služby SharePoint. Další informace najdete v tématu [rozšíření projektů SharePoint](../sharepoint/extending-sharepoint-projects.md).  
  
-   Rozšíření balení a nasazení chování položky projektu služby SharePoint a projektů služby SharePoint. Například můžete vytvořit vlastní postup nasazení provést při nasazení nebo odvolávání projektu, nebo když Visual Studio provede určité kroky nasazení můžete provádět další vlastní úlohy. Další informace najdete v tématu [rozšíření balení a nasazení SharePoint](../sharepoint/extending-sharepoint-packaging-and-deployment.md).  
  
## <a name="common-development-tasks"></a>Běžné úlohy vývoj  
 Můžete provádět následující běžné úlohy v rozšíření systému projektu služby SharePoint:  
  
-   Uložení dat vlastní řetězec s položky projektu a v několika různých typů souborů projektu. Další informace najdete v tématu [ukládání dat do rozšíření systému projektu služby SharePoint](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md).  
  
-   Převést objekt v systému projektu služby SharePoint na odpovídající objekt v sadě Visual Studio automatizace objektový model nebo integrace objektový model, nebo naopak. Další informace najdete v tématu [převádění mezi SharePoint systémovými typy projektů a ostatní typy projektů Visual Studio](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md).  
  
## <a name="see-also"></a>Viz také  
 [Definování typů položek projektu služby SharePoint vlastní](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [Rozšíření položek projektu služby SharePoint](../sharepoint/extending-sharepoint-project-items.md)   
 [Rozšíření projektů SharePoint](../sharepoint/extending-sharepoint-projects.md)   
 [Rozšíření balení a nasazení SharePoint](../sharepoint/extending-sharepoint-packaging-and-deployment.md)   
 [Ukládání dat do rozšíření systému projektu služby SharePoint](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md)   
 [Převod mezi systémovými typy projektů SharePoint a jinými typy projektů Visual Studio](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md)   
 [Rozšíření nástrojů SharePoint v sadě Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)   
 [Programování konceptů a funkcí pro rozšíření nástrojů SharePoint](../sharepoint/programming-concepts-and-features-for-sharepoint-tools-extensions.md)  
  
  