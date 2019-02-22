---
title: Rozšíření systému projektu služby SharePoint | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, extending projects
- SharePoint development in Visual Studio, extending project items
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 5b02d831093173b28cfd6c004e16c4514977a044
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56617402"
---
# <a name="extend-the-sharepoint-project-system"></a>Rozšíření systému projektu služby SharePoint
  Řešení služby SharePoint můžete vytvořit pomocí sady šablon projektů a šablon položek v sadě Visual Studio. Tyto šablony požadavkům mnoho vývojové scénáře, ale můžete narazit na některých případech, kde není poskytují funkce, které potřebujete. V těchto případech můžete rozšířit systém projektu služby SharePoint.

## <a name="overview-of-the-sharepoint-project-system"></a>Přehled systému Sharepointových projektů
 Systém projektu služby SharePoint je založen na základní součástí služby *položky Sharepointového projektu*. Položky Sharepointového projektu představuje jediné přizpůsobení SharePoint, jako je například definice seznamu, webové části nebo typu obsahu.

 Projekt SharePoint je projekt sady Visual Studio, který obsahuje jeden nebo více položek projektu služby SharePoint. Projekty SharePoint obsahovat také další součásti, které definují způsob seskupení položek projektu do funkcí a balíčků pro nasazení.

 Další informace o obsahu projektů SharePoint a položky projektu služby SharePoint, naleznete v tématu [položky vytvářet šablony a šablony projektů pro položky Sharepointového projektu](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md).

## <a name="how-to-extend-the-sharepoint-project-system"></a>Rozšíření systému projektu služby SharePoint
 Systém projektu služby SharePoint můžete rozšířit následujícími způsoby:

-   Definování vlastních typů položek projektu služby SharePoint a přidružit je k nové šablony položky nebo šablony projektů v sadě Visual Studio. Například můžete definovat typ položky projektu SharePoint pro vytvoření vlastní akce nebo pole. Další informace najdete v tématu [definování vlastních typů položek projektu služby SharePoint](../sharepoint/defining-custom-sharepoint-project-item-types.md).

-   Rozšíření typů položek projektu služby SharePoint, které jsou již nainstalovány v sadě Visual Studio. Například můžete přidat položky místní nabídky do položky projektu v **Průzkumníka řešení** a přizpůsobit položku projektu, když vývojář klikne na položku nabídky. Další informace najdete v tématu [položek projektu služby SharePoint rozšiřte](../sharepoint/extending-sharepoint-project-items.md).

-   Rozšíření projektů SharePoint. Můžete například přidat obslužné rutiny událostí k provádění konkrétních úkolů při položky jsou přidány nebo odebrány ze projektů služby SharePoint. Další informace najdete v tématu [rozšíření SharePoint projekty](../sharepoint/extending-sharepoint-projects.md).

-   Rozšíření balení a nasazení chování projektů SharePoint a položky Sharepointového projektu. Například můžete vytvořit vlastní kroky nasazení má provést, když nasazujete nebo odvolání projekt nebo můžete provádět další vlastní úlohy, když Visual Studio provede určité kroky nasazení. Další informace najdete v tématu [balení a nasazení rozšíření SharePoint](../sharepoint/extending-sharepoint-packaging-and-deployment.md).

## <a name="common-development-tasks"></a>Běžné úkoly vývoje
 Do rozšíření systému projektu služby SharePoint můžete provádět následující běžné úlohy:

-   Ukládání dat vlastní řetězec s položkami projektu a v několika různých typech souborů projektu. Další informace najdete v tématu [ukládání dat do rozšíření systému projektu služby SharePoint](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md).

-   Převést objekt v systému projektu služby SharePoint do odpovídajícího objektu v modelu objektu automatizace sady Visual Studio nebo integrace objektový model, nebo naopak. Další informace najdete v tématu [převést mezi systémovými typy projektů SharePoint a jinými typy projektů Visual Studio](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md).

## <a name="see-also"></a>Viz také:
- [Definování vlastních typů položek projektu služby SharePoint](../sharepoint/defining-custom-sharepoint-project-item-types.md)
- [Rozšíření položek projektu služby SharePoint](../sharepoint/extending-sharepoint-project-items.md)
- [Rozšíření projektů SharePoint](../sharepoint/extending-sharepoint-projects.md)
- [Rozšíření balení a nasazení SharePoint](../sharepoint/extending-sharepoint-packaging-and-deployment.md)
- [Ukládání dat do rozšíření systému projektu služby SharePoint](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md)
- [Převod mezi systémovými typy projektů SharePoint a jinými typy projektů Visual Studio](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md)
- [Rozšíření nástrojů SharePoint v sadě Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)
- [Programování konceptů a funkcí pro rozšíření nástrojů SharePoint](../sharepoint/programming-concepts-and-features-for-sharepoint-tools-extensions.md)
