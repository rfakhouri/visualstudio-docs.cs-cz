---
title: "Tvoří podpory v pracovních postupech | Microsoft Docs"
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
- SharePoint development in Visual Studio, workflows
- workflows [SharePoint development in Visual Studio]
ms.assetid: 1706f6a2-ea84-4234-85ae-19feb8540507
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e2c63af83c6ca8249e87d60f23043c0639c7fd43
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="form-support-in-workflows"></a>Podpora formulářů v produktu Workflows
  V pracovním postupu možné použít čtyři typy tvarů: přidružení, spuštění, úloh a úpravy. Tyto typy formuláře může být založen na formuláře ASPX nebo formuláře aplikace InfoPath. Úroveň podpory, který [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] poskytuje pro příslušného formuláře závisí na několika faktorech, které jsou popsány v následujících tabulkách. Další informace o typech formuláře pracovního postupu najdete v tématu [přehled pracovního postupu Forms](http://go.microsoft.com/fwlink/?LinkId=185228) na webu MSDN.  
  
## <a name="xml-refactoring"></a>Refaktoring XML  
 Když přidáte ASPX přidružení nebo spuštění formuláře k [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] položka projektu pracovního postupu, [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] automaticky refactors kód XML v souboru pracovního postupu Elements.xml zachovat atribut, který odkazuje na přidružení nebo spuštění formulář synchronizované vždy, když se aktualizuje formuláře název nebo nasazení cestu nebo formulář je odstraněn. Pokud používáte jiné typy formuláře v pracovním postupu, jako je například formuláři úloh nebo změna není rozdělili souboru Elements.xml.  
  
## <a name="form-support-in-new-visual-studio-workflows"></a>Podpora formulářů v nových pracovních postupů sady Visual Studio  
 Následující tabulka uvádí [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] podporu různých typů ve formulářích ASPX nebo InfoPath v pracovních postupech, které jsou vytvořeny v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
|Typ formuláře|Pracovní postup vytvořený v sadě Visual Studio s formuláře ASPX|Pracovní postup vytvořený v sadě Visual Studio pomocí formuláře aplikace InfoPath|  
|---------------|---------------------------------------------------------|-----------------------------------------------------------------|  
|Přidružení|-ASPX přidružení formuláře lze přidat do pracovního postupu pomocí **formuláře přidružení pracovního postupu** šablony položky.<br />-Při přidávání, přejmenovat nebo odstranit formuláře, nebo když se změní cesta pro její nasazení, je teď vyčleněný souboru Elements.xml pracovního postupu.<br />-Další informace najdete v tématu [návod: vytvoření pracovního postupu pomocí formulářů přidružení a inicializace](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md).|-Neexistuje žádná šablona InfoPath přidružení formuláře v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].<br />-Neexistuje žádná integrace mezi [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] a návrháři InfoPath.<br />-Není rozdělili souboru Elements.xml pracovního postupu.|  
|Inicializace|-ASPX spuštění formuláře lze přidat do pracovního postupu pomocí **formuláře inicializace pracovního postupu** šablony položky.<br />-Při přidávání, přejmenovat nebo odstranit formuláře, nebo když se změní cesta pro její nasazení, je teď vyčleněný souboru Elements.xml pracovního postupu.<br />-Další informace najdete v tématu [návod: vytvoření pracovního postupu pomocí formulářů přidružení a inicializace](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md).|-Neexistuje žádná šablona InfoPath přidružení formuláře v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].<br />-Neexistuje žádná integrace mezi [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] a návrháři InfoPath.<br />-Není rozdělili souboru Elements.xml pracovního postupu.|  
|Úloha|-Žádná šablona formuláře ASPX úloh je k dispozici v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Musíte vytvořit stránku aplikace a přidejte do ní kód.<br />-Není rozdělili souboru Elements.xml pracovního postupu.<br />-Další informace najdete v tématu [formuláře úlohy pracovního postupu (SharePoint Foundation)](http://go.microsoft.com/fwlink/?LinkId=187674)|-Neexistuje žádná šablona InfoPath úloh formuláře v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].<br />-Neexistuje žádná integrace mezi [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] a návrháři InfoPath.<br />-Není rozdělili souboru Elements.xml pracovního postupu.|  
|Úpravy|-Je k dispozici v šabloně žádné úpravy ASPX [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Chcete-li přidat formulář Úpravy, musí vytvoření stránky aplikace a přidejte do ní kód.<br />-Není rozdělili souboru Elements.xml pracovního postupu. Je nutné ručně upravit podle potřeby.<br />-Další informace najdete v tématu [formuláře Změna pracovního postupu (SharePoint Foundation)](http://go.microsoft.com/fwlink/?LinkId=187675)|-Neexistuje žádná šablona InfoPath úpravy formuláře v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].<br />-Neexistuje žádná integrace mezi [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] a návrháři InfoPath.<br />-Není rozdělili souboru Elements.xml pracovního postupu.|  
  
## <a name="form-support-in-imported-sharepoint-reusable-workflows"></a>Podpora formulářů v pracovních postupech importované opakovaně použitelného služby SharePoint  
 Následující tabulka uvádí [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] podporu různých typů na ASPX nebo InfoPath formulářů v opakovaně použitelných pracovních postupů služby SharePoint, které jsou importovány do [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
|Typ formuláře|Opakovaně použitelného pracovního postupu, který má formuláře ASPX naimportované z Návrháře služby SharePoint|Opakovaně použitelného pracovního postupu, který má formuláře aplikace InfoPath naimportované z Návrháře služby SharePoint|  
|---------------|-------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|  
|Přidružení|-Formuláře se odkazuje v souboru Elements.xml pracovního postupu.<br />-Když formuláře je přejmenován nebo odstraněn, nebo když se změní cesta pro její nasazení, je teď vyčleněný souboru Elements.xml pracovního postupu.|-Formuláře je naimportovány, ale neodkazuje v Elements.xml pracovního postupu.<br />-Není rozdělili souboru Elements.xml pracovního postupu.|  
|Inicializace|-Formuláře je odkazován objektem pracovního postupu v souboru Elements.xml pracovního postupu.<br />-Když formuláře je přejmenován nebo odstraněn, nebo když se změní cesta pro její nasazení, je teď vyčleněný souboru Elements.xml pracovního postupu.|-Formuláře je naimportovány, ale neodkazuje v Elements.xml pracovního postupu.<br />-Není rozdělili souboru Elements.xml pracovního postupu. **Poznámka:** pravidla a vlastnosti musí být přidán a změnit pro tento scénář fungovat.|  
|Úloha|-Formuláře se odkazuje v souboru Elements.xml pracovního postupu.<br />-Není rozdělili souboru Elements.xml pracovního postupu.|-Formuláře je naimportovány, ale neodkazuje v Elements.xml pracovního postupu.<br />-Není rozdělili souboru Elements.xml pracovního postupu. **Poznámka:** pravidla a vlastnosti musí být přidán a změnit pro tento scénář fungovat.|  
|Úpravy|Nelze použít. V seznamu služby SharePoint nelze vytvořit ASPX úpravy formulářů.|Nelze použít. Úpravy formulářů aplikace InfoPath nelze vytvořit v Návrháři SharePoint, s výjimkou předdefinované SharePoint Server pracovního postupu, který není součástí souborů WSP při exportu pracovního postupu.|  
  
## <a name="see-also"></a>Viz také  
 [Návod: Vytvoření pracovního postupu pomocí formulářů přidružení a inicializace](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md)   
 [Vytváření řešení pracovního postupu služby SharePoint](../sharepoint/creating-sharepoint-workflow-solutions.md)   
 [Import položek z existující stránky SharePoint](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)  
  
  