---
title: Integrace obchodních dat do služby SharePoint | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], business data
- BDC [SharePoint development in Visual Studio], aggregating data
- BDC [SharePoint development in Visual Studio], business data
- Business Data Connectivity service [SharePoint development in Visual Studio], aggregating data
- BDC [SharePoint development in Visual Studio], creating a model
- Business Data Connectivity service [SharePoint development in Visual Studio], creating a model
- Business Data Connectivity service [SharePoint development in Visual Studio], data
- BDC [SharePoint development in Visual Studio], data
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: d04a3fcfac93ffbb6a2a6c60363e4906898e0c7f
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54865473"
---
# <a name="integrate-business-data-into-sharepoint"></a>Integrace obchodních dat do služby SharePoint
  Integraci obchodních dat do služby SharePoint. Obchodní data můžou pocházet z back endové serverové aplikace, jako například [!INCLUDE[TLA#tla_sqlsvr](../sharepoint/includes/tlasharptla-sqlsvr-md.md)], Siebel a SAP, nebo webové službě. Uživatelé mohou zobrazit, přidat, aktualizovat nebo odstranit obchodních dat s použitím externí seznamy nebo obchodní Data webových částí služby SharePoint.  Uživatelé mohou také přístup k těmto datům v režimu offline v aplikaci Microsoft Office, jako je například Microsoft Outlook. Další informace najdete v tématu [kde lze je zobrazit externí Data](http://go.microsoft.com/fwlink/?LinkId=169295).  
  
 K integraci dat do služby SharePoint, vytvořte model služby obchodní Data připojení (BDC). Služba BDC je aplikace v Sharepointu, která uchovává informace o data v obchodních aplikacích. Další informace najdete v tématu [obchodní Data připojení (BDC) služby](http://go.microsoft.com/fwlink/?LinkID=169276).  
  
## <a name="models-in-visual-studio"></a>Modelů v sadě Visual Studio  
 Modelů v sadě Visual Studio umožňují napsat vlastní kód se načítají a aktualizují data ze zdrojů dat back-end. Můžete také agregovaná data z různých zdrojů dat. Například můžete zobrazit seznam zákazníků, které obsahují data z [!INCLUDE[ssNoVersion](../sharepoint/includes/ssnoversion-md.md)] databáze a webové služby.  
  
 Můžete také importovat modely, které jsou už nasazené do Sharepointu. Po importu modelu, můžete přidat vlastní kód nebo jenom pomocí sady Visual Studio balení a nasazení modelu do více Sharepointové serverové farmy. Další informace najdete v tématu [vytvoření modelu připojení obchodních dat](../sharepoint/creating-a-business-data-connectivity-model.md).  
  
## <a name="design-a-model-in-visual-studio"></a>Návrh modelu v sadě Visual Studio
 Model můžete navrhnout pomocí návrháře a několika okny nástrojů. Při návrhu modelu, sada Visual Studio generuje XML modelu. Další informace najdete v tématu [přehled nástrojů pro návrh modelu služby BDC](../sharepoint/bdc-model-design-tools-overview.md).  
  
 Model obsahuje entit a metody.  
  
### <a name="entities"></a>Entity  
 Entita popisuje kolekci polí. Entity mohou například představovat tabulky v databázi. Entity se zobrazí jako typ externího obsahu sharepointu. Další informace o externích typů obsahu, najdete v části [co jsou typy externího obsahu?](http://go.microsoft.com/fwlink/?LinkId=169293)  
  
### <a name="methods"></a>Metody  
 Metoda umožňuje příjemci typ externího obsahu k provedení akce na pole entity. Například může povolit uživatelům změnit adresu aktualizační metody a narození datum zákazníka kde `Address` a `BirthDate` jsou pole `Customer` entity.  
  
 Visual Studio generuje soubor kódu služby pro každou entitu v modelu. Když přidáte metodu pro váš model, Visual Studio vygeneruje odpovídající metody v souboru kódu služby. Přidejte kód pro každou metodu za účelem na příslušnou úlohu. Pokud chcete do modelu přidat metody vytvoření, sada Visual Studio generuje metody vytvoření v souboru kódu služby. Tato metoda je volána službou BDC, když uživatel klikne **nová položka** tlačítko v seznamu, který je založen na modelu. Proto přidejte kód do metody tvůrce, který přidává nová data do zdroje dat. Další informace najdete v tématu [navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
## <a name="related-topics"></a>Související témata
  
|Název|Popis|  
|-----------|-----------------|  
|[Vytvoření modelu připojení obchodních dat](../sharepoint/creating-a-business-data-connectivity-model.md)|Ukazuje, jak vytvořit nový model nebo import modelu, který můžete exportovat ze Sharepointu.|  
|[Navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md)|Vysvětluje, jak navrhovat prvků modelu s použitím sady Visual Studio návrhové nástroje.|  
|[Kdy použít Návrháře služby SharePoint vs. Visual Studio při vývoji řešení s využitím BCS](http://go.microsoft.com/fwlink/?LinkID=183448)|Vám pomůže rozhodnout, jestli se má použít Visual Studio nebo použijte návrháře služby SharePoint k vytvoření modelu BDC.|  
