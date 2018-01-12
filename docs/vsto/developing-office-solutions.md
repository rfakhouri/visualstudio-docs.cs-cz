---
title: "Vývoj řešení pro systém Office | Microsoft Docs"
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
- Office development in Visual Studio, about developing solutions
- solutions [Office development in Visual Studio], developing
- Office solutions [Office development in Visual Studio], developing
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: bb3727d95fab03d2485c26f5858e0dbea7fe7543
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="developing-office-solutions"></a>Vývoj řešení pro systém Office
  Po návrhu projektu pomocí doplňku Office developer tools v sadě Visual Studio a nastavit soubory projektu, můžete začít soustředit na implementaci kódu a vlastní uživatelské rozhraní (UI).  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
> [!NOTE]  
>  Máte zájem o vývoji řešení, které rozšiřují Office prostředí napříč [více platforem](https://dev.office.com/add-in-availability)? Podívejte se na [Office Add in modelu](https://dev.office.com/docs/add-ins/overview/office-add-ins). Doplňky Office mají malé nároky ve srovnání s doplňků VSTO a řešení a můžete je vytvořit pomocí téměř jakoukoli webové programování technologie, jako je například HTML5, JavaScript, CSS3 a XML.  
  
## <a name="office-solutions-programming-model"></a>Programovací Model řešení pro systém Office  
 Objektový model Office zveřejňuje řadu objekty, které můžete naprogramovat oproti. Vždy, když budete programu řešení pro systém Office pomocí spravovaného kódu, můžete napsat kód, který používá typy v primární spolupracující sestavení sady Office. V řešení, které vytvoříte pomocí šablony projektů Office v sadě Visual Studio taky napsat kód přímo na generované třídy ve vašem projektu. Další informace najdete v tématu [psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md).  
  
## <a name="programming-different-types-of-office-solutions"></a>Programování různé typy řešení pro systém Office  
 Typ řešení, které vytváříte určuje funkce, které můžete použít ve vašem projektu. Například můžete přidat ovládací prvky Windows Forms a rozšířené ovládací prvky Office (s názvem *hostování ovládacích prvků*) na úpravy na úrovni dokumentů tak, že přetáhnete položky z **sada nástrojů** v sadě Visual Studio v době návrhu . Ale pokud vyvíjíte doplňku VSTO, pouze přidáte tyto řazení ovládacích prvků do dokumentů za běhu pomocí kódu jazyka.  
  
 Další informace o funkcích, které jsou specifické pro různé typy řešení najdete v následujících tématech:  
  
-   [Programování doplňků VSTO](../vsto/programming-vsto-add-ins.md).  
  
-   [Programování přizpůsobení na úrovni dokumentu](../vsto/programming-document-level-customizations.md).  
  
-   [Přizpůsobení uživatelského rozhraní Office](../vsto/office-ui-customization.md).  
  
 Obecné informace, které vám pomohou při plánování řešení pro systém Office a postupy, které vám pomohou vytvořit projekty, najdete v části [návrh a vytváření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md).  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md)|Popisuje různé aspekty psaní kódu v řešeních pro systém Office.|  
|[Programování doplňků VSTO](../vsto/programming-vsto-add-ins.md)|Přehled modelu programování doplňků VSTO a souvisejících úloh programování.|  
|[Programování přizpůsobení na úrovni dokumentu](../vsto/programming-document-level-customizations.md)|Přehled modelu programování přizpůsobení na úrovni dokumentu a souvisejících úloh programování.|  
|[Přizpůsobení uživatelského rozhraní systému Office](../vsto/office-ui-customization.md)|Popisuje různé způsoby, můžete přizpůsobit aplikace uživatelského rozhraní systému Office s použitím doplňků VSTO a úpravy na úrovni dokumentů.|  
|[Data v řešeních pro systém Office](../vsto/data-in-office-solutions.md)|Popisuje různé způsoby, které můžete pracovat s daty v řešeních pro systém Office, jako je například svázání dat s ovládacími prvky a ukládání do mezipaměti data v přizpůsobeních na úrovni dokumentu.|  
|[Jak ovlivňuje automatické ukládání řešení pro Office](./how-autosave-impacts-office-solutions.md)|Popisuje úpravy, které možná budete muset udělat řešení pro systém Office, pokud je povoleno automatické ukládání.|
|[Řešení potíží s řešeními pro systém Office](../vsto/troubleshooting-office-solutions.md)|Poskytuje tipy pro řešení běžných problémů, které se mohou vyskytnout při vytváření řešení pro systém Office.|  
|[Podpora práce s vlákny v systému Office](../vsto/threading-support-in-office.md)|Poskytuje přehled o práci s více vlákny v řešeních pro systém Office.|  
|[Usnadnění v projektech pro systém Office](../vsto/accessibility-in-office-projects.md)|Popisuje funkce usnadnění, které jsou k dispozici v řešeních pro systém Office.|  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytváření a změny přizpůsobených vlastností dokumentu](../vsto/how-to-create-and-modify-custom-document-properties.md)   
 [Postupy: čtení z a zapisovat do vlastností dokumentu](../vsto/how-to-read-from-and-write-to-document-properties.md)   
 [Postupy: cíle vícejazyčné uživatelské rozhraní Office](../vsto/how-to-target-the-office-multilingual-user-interface.md)   
 [Návod: Vytvoření vašeho prvního doplňku VSTO pro Excel](../vsto/walkthrough-creating-your-first-vsto-add-in-for-excel.md)   
 [Návod: Vytvoření prvního přizpůsobení na úrovni dokumentu pro Excel](../vsto/walkthrough-creating-your-first-document-level-customization-for-excel.md)   
 [Návod: Vytvoření vašeho prvního doplňku VSTO pro Outlook](../vsto/walkthrough-creating-your-first-vsto-add-in-for-outlook.md)   
 [Návod: Vytvoření vašeho prvního doplňku VSTO pro PowerPoint](../vsto/walkthrough-creating-your-first-vsto-add-in-for-powerpoint.md)   
 [Návod: Vytvoření vašeho prvního doplňku VSTO pro projekt](../vsto/walkthrough-creating-your-first-vsto-add-in-for-project.md)   
 [Návod: Vytvoření vašeho prvního doplňku VSTO pro Word](../vsto/walkthrough-creating-your-first-vsto-add-in-for-word.md)   
 [Návod: Vytvoření prvního přizpůsobení na úrovni dokumentu pro Word](../vsto/walkthrough-creating-your-first-document-level-customization-for-word.md)  
  
  