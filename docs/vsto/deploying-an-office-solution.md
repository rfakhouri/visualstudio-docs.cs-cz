---
title: Nasazení řešení Office
ms.date: 02/02/2017
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
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: d48d534d0f8783b803b9c5ade17a693a03ef37d9
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63441870"
---
# <a name="deploy-an-office-solution"></a>Nasazení řešení Office
  Řešení pro Office můžete nasadit pomocí technologie ClickOnce nebo Instalační služby systému Windows. Použití technologie ClickOnce umožňuje snížit počet kroků potřebných pro nasazení a aktualizaci vašeho řešení. Pokud použijete Instalační službu systému Windows, získáte kontrolu nad tím, jak bude řešení nainstalováno a jaké stránky instalační program zobrazí, až budou uživatelé vaše řešení instalovat.

> [!NOTE]
> Zajímá vás vývoj řešení, které rozšiřují Office prostředí napříč [více platforem](https://dev.office.com/add-in-availability)? Podívejte se na nové [Office Add-ins modelu](https://dev.office.com/docs/add-ins/overview/office-add-ins). Doplňky sady Office mají malé náklady v porovnání s doplňky VSTO a řešení a je můžete vytvořit s využitím téměř jakékoli webové programování technologie, jako je například HTML5, JavaScript, CSS3 a XML.

## <a name="deploy-a-solution-by-using-clickonce"></a>Nasazení řešení s použitím technologie ClickOnce
 Když řešení nasadíte pomocí technologie ClickOnce, publikujete jej do centrálního umístění, z něhož jej mohou uživatelé nainstalovat a spustit. Řešení můžete aktualizovat bez nutnosti distribuovat nový instalační program uživatelům.  Tento způsob nasazení je jednodušší, ale neumožňuje zobrazit uživatelům při instalaci vlastní stránky. Řešení je také nutné nainstalovat vícekrát, pokud má počítač více než jednoho uživatele. Zobrazit [nasazení řešení Office s použitím technologie ClickOnce](../vsto/deploying-an-office-solution-by-using-clickonce.md).

## <a name="deploy-a-solution-by-using-windows-installer"></a>Nasazení řešení pomocí Instalační služby systému Windows
 Když řešení nasadíte pomocí Instalační služby systému Windows, musíte uživatelům distribuovat instalační program, pomocí něhož řešení nainstalují. Instalační program může nainstalovat řešení pro všechny uživatele počítače současně, na rozdíl od instalace pouze pro aktuálního uživatele. Máte také větší kontrolu nad možnostmi, které se uživatelům zobrazí při instalaci vašeho řešení. Můžete například zobrazit licenční smlouvu nebo uživatelům umožnit nainstalovat konkrétní součásti řešení. Pokud ale řešení aktualizujete, musíte distribuovat nový instalační program. Zobrazit [nasazení řešení Office s použitím Instalační služby systému Windows](../vsto/deploying-an-office-solution-by-using-windows-installer.md).

## <a name="see-also"></a>Viz také:
- [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)
- [Nasazení řešení Office s použitím technologie ClickOnce](../vsto/deploying-an-office-solution-by-using-clickonce.md)
- [Nasazení řešení Office s použitím Instalační služby systému Windows](../vsto/deploying-an-office-solution-by-using-windows-installer.md)
- [Řešení potíží s nasazením řešení pro systém Office](../vsto/troubleshooting-office-solution-deployment.md)
