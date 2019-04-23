---
title: Pokyny pro import opakovaně použitelných pracovních postupů | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, importing items
- SharePoint development in Visual Studio, reusable workflows
- importing items [SharePoint development in Visual Studio]
- reusable workflows [SharePoint development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: bb386a2d80931ece415b0b3939f2947678808261
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60041218"
---
# <a name="guidelines-for-importing-reusable-workflows"></a>Pokyny pro import opakovaně použitelných pracovních postupů
  Pro import opakovaně použitelných pracovních postupů, které jsou vytvořeny v aplikaci SharePoint Designer, použijte šablonu projektu Import opakovaně použitelného Sharepointu 2010 pracovního postupu v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Importuje šabloně *deklarativní* *pracovního postupu* ([!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)]– pouze) a převede ho na *kód pracovního postupu*, což je pracovní postup, který můžete zvýšit s oběma [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] nebo [!INCLUDE[csprcs](../sharepoint/includes/csprcs-md.md)] kódu. [!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)] [Návod: Import opakovaně použitelného pracovního postupu návrháře služby SharePoint do sady Visual Studio](../sharepoint/walkthrough-import-a-sharepoint-designer-reusable-workflow-into-visual-studio.md).

 Import opakovaně použitelného 2010 pracovního postupu služby SharePoint šablony však můžete importovat pouze řešení farmy. Pokud chcete nasadit jako řešení v izolovaném prostoru pracovního postupu, ji naimportujte pomocí šablony importovat balíček řešení služby SharePoint 2010. Tímto způsobem, ale nedá se převést na kód pracovního postupu a nebudete moct změnit v důsledku.

## <a name="import-reusable-workflows-by-using-the-import-reusable-workflow-template"></a>Import opakovaně použitelných pracovních postupů s použitím šablony Import opakovaně použitelného pracovního postupu
 Pokud importujete opakovaně použitelného pracovního postupu pomocí šablony Import opakovaně použitelných 2010 pracovního postupu služby SharePoint, můžete spustit nebo změnit řešení stejně jako jakýkoli jiný [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] řešení služby SharePoint, ale budete možná muset ručně vyřešit některé položky.

### <a name="import-task-forms"></a>Importovat formuláře úkolu
 Šablona projektu pracovního postupu Import opakovaně použitelného služby SharePoint 2010 importuje všechny formuláře zahájení a přidružení, ale importuje formuláře pouze jeden úkol, protože schéma pracovního postupu kód povoluje jen jeden úkol formulář. Žádné další úlohy formuláře z původního řešení pracovního postupu jsou vloženy do **ostatní soubory importovat** složky **Průzkumníka řešení**.

## <a name="import-reusable-workflows-by-using-the-import-sharepoint-2010-solution-package-template"></a>Import opakovaně použitelných pracovních postupů s použitím šablony importovat balíček řešení služby SharePoint 2010
 Pokud importujete opakovaně použitelného pracovního postupu pomocí šablony importovat balíček řešení služby SharePoint 2010, je potřeba zvážit následující problémy:

- Po importu pracovního postupu, můžete okamžitě nasadit a spustit ho v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] výběrem **F5** klíč. Ale pokud něco v pracovním postupu v importované řešení změnit, budete muset ručně vyřešit prvky v projektu bylo možné nasadit a spustit pracovní postup.

- Protože pracovní postup je deklarativní, kód nelze přidat k němu. Převést pracovní postup do kódu pracovního postupu, je nutné naimportovat ho do [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] pomocí šablony Import opakovaně použitelného 2010 pracovního postupu služby SharePoint.

- Když upravíte soubor návrháře (XOML) pracovního postupu v návrhovém zobrazení, se doporučuje upravit v zobrazení zdroje, protože návrháře postupu provádění zobrazí falešné chyby.

- Ladění pracovního postupu pro deklarativní obsah nefunguje. Zarážky nastavené v [!INCLUDE[wfd2](../sharepoint/includes/wfd2-md.md)] nejsou přístupů.

## <a name="import-globally-reusable-workflow-solutions"></a>Import řešení globálně opakovaně použitelného pracovního postupu
 Nelze importovat globálně opakovaně použitelných pracovních postupů s použitím šablony Import opakovaně použitelného pracovního postupu 2010 SharePoint. Chcete-li importovat globální opakovaně použitelného pracovního postupu, budete muset převést globálně opakovaně použitelného pracovního postupu nebo je nutné použít šablonu importovat balíček řešení služby SharePoint 2010.

 Chcete-li převést pracovní postup, vytvořte kopii globálně opakovaně použitelného pracovního postupu v aplikaci SharePoint Designer (tak, že otevřete místní nabídku pro pracovní postup a následným výběrem možnosti **uložit jako kopii**). Importujte nový opakovaně použitelného pracovního postupu pomocí šablony Import opakovaně použitelného Sharepointu 2010 pracovního postupu [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].

 Chcete-li importovat globální opakovaně použitelného pracovního postupu bez její změny, použijte šablonu importovat balíček řešení služby SharePoint 2010. Pokud použijete tuto metodu, pracovní postup není převedena na kód pracovního postupu a zůstane deklarativní pracovního postupu.

## <a name="see-also"></a>Viz také:
- [Import položek z existující stránky SharePoint](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)
- [Návod: Import opakovaně použitelného pracovního postupu návrháře služby SharePoint do sady Visual Studio](../sharepoint/walkthrough-import-a-sharepoint-designer-reusable-workflow-into-visual-studio.md)
