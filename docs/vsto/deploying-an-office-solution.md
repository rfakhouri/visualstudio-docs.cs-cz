---
title: Nasazení řešení Office | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ClickOnce deployment [Office development in Visual Studio], event viewer
- deploying applications [Office development in Visual Studio], event viewer
- Office applications [Office development in Visual Studio], deploying Office solutions
- Office development in Visual Studio, deploying Office solutions
- ClickOnce deployment [Office development in Visual Studio], troubleshooting
- deploying applications [Office development in Visual Studio], Office solutions (2007 system)
- Office development in Visual Studio, troubleshooting
- Office development in Visual Studio, event viewer
- ClickOnce deployment [Office development in Visual Studio], about ClickOnce solution deployments
- Office solutions [Office development in Visual Studio], deploying
- deploying applications [Office development in Visual Studio], troubleshooting
- solutions [Office development in Visual Studio], deploying Office solutions (2007 system)
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 1a397ef0986bd2a278f4b341dc772c71bc9b0a51
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="deploying-an-office-solution"></a>Nasazení řešení Office
  Řešení pro Office můžete nasadit pomocí technologie ClickOnce nebo Instalační služby systému Windows. Použití technologie ClickOnce umožňuje snížit počet kroků potřebných pro nasazení a aktualizaci vašeho řešení. Pokud použijete Instalační službu systému Windows, získáte kontrolu nad tím, jak bude řešení nainstalováno a jaké stránky instalační program zobrazí, až budou uživatelé vaše řešení instalovat.  
  
> [!NOTE]  
>  Máte zájem o vývoji řešení, které rozšiřují Office prostředí napříč [více platforem](https://dev.office.com/add-in-availability)? Podívejte se na [Office Add in modelu](https://dev.office.com/docs/add-ins/overview/office-add-ins). Doplňky Office mají malé nároky ve srovnání s doplňků VSTO a řešení a můžete je vytvořit pomocí téměř jakoukoli webové programování technologie, jako je například HTML5, JavaScript, CSS3 a XML.  
  
## <a name="deploying-a-solution-by-using-clickonce"></a>Nasazení řešení pomocí technologie ClickOnce  
 Když řešení nasadíte pomocí technologie ClickOnce, publikujete jej do centrálního umístění, z něhož jej mohou uživatelé nainstalovat a spustit. Řešení můžete aktualizovat bez nutnosti distribuovat nový instalační program uživatelům.  Tento způsob nasazení je jednodušší, ale neumožňuje zobrazit uživatelům při instalaci vlastní stránky. Řešení je také nutné nainstalovat vícekrát, pokud má počítač více než jednoho uživatele. V tématu [nasazení řešení Office s použitím technologie ClickOnce](../vsto/deploying-an-office-solution-by-using-clickonce.md).  
  
## <a name="deploying-a-solution-by-using-windows-installer"></a>Nasazení řešení pomocí Instalační služby systému Windows  
 Když řešení nasadíte pomocí Instalační služby systému Windows, musíte uživatelům distribuovat instalační program, pomocí něhož řešení nainstalují. Instalační program může nainstalovat řešení pro všechny uživatele počítače současně, na rozdíl od instalace pouze pro aktuálního uživatele. Máte také větší kontrolu nad možnostmi, které se uživatelům zobrazí při instalaci vašeho řešení. Můžete například zobrazit licenční smlouvu nebo uživatelům umožnit nainstalovat konkrétní součásti řešení. Pokud ale řešení aktualizujete, musíte distribuovat nový instalační program. V tématu [nasazení řešení Office s použitím Instalační služby systému Windows](../vsto/deploying-an-office-solution-by-using-windows-installer.md).  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)   
 [Nasazení řešení Office s použitím technologie ClickOnce](../vsto/deploying-an-office-solution-by-using-clickonce.md)   
 [Nasazení řešení Office s použitím Instalační služby systému Windows](../vsto/deploying-an-office-solution-by-using-windows-installer.md)   
 [Řešení potíží s nasazením řešení pro systém Office](../vsto/troubleshooting-office-solution-deployment.md)  
  
  