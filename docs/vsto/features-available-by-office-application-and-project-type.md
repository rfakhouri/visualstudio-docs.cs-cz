---
title: "Dostupné funkce podle aplikace Office a typu projektu | Microsoft Docs"
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
- application-level add-ins [Office development in Visual Studio]
- Office development in Visual Studio, features
- Ribbon [Office development in Visual Studio]
- Office applications [Office development in Visual Studio], features available
- document-level customizations [Office development in Visual Studio]
- Office projects [Office development in Visual Studio], features available
- add-ins [Office development in Visual Studio]
- form regions [Office development in Visual Studio], features available
ms.assetid: 3e9aa4d3-affb-4f76-bc67-49fe5f26a6a1
caps.latest.revision: "53"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 6a0f2e0b87e791618477ff6e11c9e180793d5495
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="features-available-by-office-application-and-project-type"></a>Dostupné funkce podle aplikací systému Office a typů projektu
  Visual Studio obsahuje několik typů šablon projektů, které podporují různé obchodní scénáře pro aplikace Microsoft Office, včetně následujících typů:  
  
-   Úpravy na úrovni dokumentů.  
  
-   Doplňků VSTO.  
  
 Ne všechny aplikace mohou používat každý typ projektu. Například projekty na úrovni dokumentu jsou k dispozici pouze pro aplikace Microsoft Office Word a Microsoft Office Excel. Podobně některé funkce jsou dostupné pouze pro určité typy projektů nebo aplikace. Například v podokně Akce je dostupná jenom v projektech na úrovni dokumentu a jsou dostupná jenom pro některé aplikace pásu karet rozšíření. Další informace o typech jiný projekt, najdete v části [přehled vývoje řešení pro systém Office &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md).  
  
> [!NOTE]  
>  Šablony projektů Office jsou k dispozici pouze v některých edicích [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Další informace najdete v tématu [Konfigurace počítače pro vývoj řešení pro Office](../vsto/configuring-a-computer-to-develop-office-solutions.md).  
  
## <a name="project-types-available-for-different-microsoft-office-applications"></a>K dispozici pro aplikace Microsoft Office různé typy projektů  
 V následující tabulce jsou aplikace, které může používat pro každý typ projektu.  
  
|Typy projektů|Aplikace Microsoft Office|  
|-------------------|----------------------------------|  
|Přizpůsobení na úrovni dokumentu|Excel<br /><br /> Word|  
|Doplňků VSTO|Excel<br /><br /> InfoPath (InfoPath 2013 a InfoPath 2010 pouze)<br /><br /> Outlook<br /><br /> PowerPoint<br /><br /> Projekt<br /><br /> Visio<br /><br /> Word<br /><br /> Excel|  
  
## <a name="features-available-in-different-project-types"></a>Funkce, které jsou k dispozici v různých typech projektů  
 Následující tabulka uvádí, které typy projektů zadejte každou funkci.  
  
|Funkce|Typy projektů, které poskytují funkce|Další čtení|  
|-------------|--------------------------------------------|---------------------|  
|Podokna akcí.|Projekty na úrovni dokumentu.|[Přehled podokna akcí](../vsto/actions-pane-overview.md)|  
|ClickOnce – nasazení.|Projekty na úrovni dokumentu a VS.|[Nasazení řešení Office](../vsto/deploying-an-office-solution.md)|  
|Vlastní podokna úloh.|Add-in projekty doplňku VSTO v následujících aplikacích:<br /><br /> -Aplikace Excel<br />-InfoPath (InfoPath 2013 a InfoPath 2010 pouze)<br />-Outlook<br />-PowerPoint<br />-Word|[Vlastní podokona úloh](../vsto/custom-task-panes.md)|  
|Vlastní části XML.|Projekty na úrovni dokumentu.<br /><br /> Aplikace úrovně projekty pro následující aplikace:<br /><br /> -Aplikace Excel<br />-PowerPoint<br />-Word|[Přehled vlastních částí XML](../vsto/custom-xml-parts-overview.md)|  
|Datové mezipaměti.|Projekty na úrovni dokumentu.|[Data uložená v mezipaměti v přizpůsobeních na úrovni dokumentu](../vsto/cached-data-in-document-level-customizations.md)|  
|Vystavení objektu v doplňku VSTO pro jiné řešení pro Microsoft Office.|Add-in projekty VSTO.|[Volání kódu v doplňcích VSTO z jiných řešení pro Office](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md)|  
|Následující hostitelské ovládací prvky:<br /><br /> -Grafu<br />-ListObject<br />-NamedRange<br />-Ovládací prvky obsahu<br />– Záložka|Projekty na úrovni dokumentu.<br /><br /> Add-in projekty VSTO pro Word a Excel.|[Přehled hostitelských položek a hostitelských ovládacích prvků](../vsto/host-items-and-host-controls-overview.md)|  
|Následující hostitelské ovládací prvky:<br /><br /> – Xmlmappedrange –<br />– XmlNode –<br />– XmlNodes –|Projekty na úrovni dokumentu.|[Přehled hostitelských položek a hostitelských ovládacích prvků](../vsto/host-items-and-host-controls-overview.md)|  
|Vícenásobného projektu nasazení.|Projekty na úrovni dokumentu.<br /><br /> Add-in projekty VSTO.|[Návod: Nasazení více řešení pro systém Office v jedné instalaci ClickOnce](http://msdn.microsoft.com/en-us/051223c0-4082-4799-b78b-a4763a9def55)|  
|Oblastí formulářů aplikace Outlook.|Add-in projekty VSTO pro Outlook.|[Vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md)|  
|Akce po nasazení.|Projekty na úrovni dokumentu.<br /><br /> Add-in projekty VSTO.|[Návod: Kopírování dokumentu do počítače koncového uživatele po instalaci ClickOnce](http://msdn.microsoft.com/en-us/100090f7-bc63-4152-b3e1-19b48bc27466)|  
|Přizpůsobení pásu karet.|Projekty na úrovni dokumentu.<br /><br /> Add-in projekty doplňku VSTO v následujících aplikacích:<br /><br /> -Aplikace Excel<br />-InfoPath (InfoPath 2013 a InfoPath 2010 pouze)<br />-Outlook<br />-PowerPoint<br />-Projektu<br />-Aplikace Visio<br />-Word|[Přehled pásu karet](../vsto/ribbon-overview.md)|  
|Návrhář Visual dokumentu.|Projekty na úrovni dokumentu.|[Projekty pro systém Office v prostředí Visual Studio](../vsto/office-projects-in-the-visual-studio-environment.md)|  
  
## <a name="see-also"></a>Viz také  
 [Začínáme &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/getting-started-office-development-in-visual-studio.md)   
 [Přehled vývoje řešení pro systém Office &#40; VSTO &#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [Přehled podokna akcí](../vsto/actions-pane-overview.md)   
 [Přehled pásu karet](../vsto/ribbon-overview.md)   
 [Vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Data uložená v mezipaměti v přizpůsobeních na úrovni dokumentu](../vsto/cached-data-in-document-level-customizations.md)   
 [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)  
  
  