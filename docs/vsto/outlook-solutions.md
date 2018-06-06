---
title: řešení pro aplikaci Outlook
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- solutions [Office development in Visual Studio], Outlook
- Office projects [Office development in Visual Studio], Outlook
- Office solutions [Office development in Visual Studio], Outlook
- templates [Office development in Visual Studio], Outlook
- projects [Office development in Visual Studio], Outlook
- Outlook [Office development in Visual Studio]
- e-mail [Office development in Visual Studio], Outlook solutions
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 07a7917e1c33da2151abaeba7dc4f684ca0d067b
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34572943"
---
# <a name="outlook-solutions"></a>řešení pro aplikaci Outlook
  Visual Studio poskytuje šablony projektů, které můžete použít k vytvoření doplňků VSTO pro aplikaci Microsoft Office Outlook. Doplňků VSTO slouží k automatizaci operací aplikace Outlook, rozšířit funkce aplikace Outlook nebo přizpůsobení uživatelského rozhraní (UI) aplikace Outlook. Další informace o doplňků VSTO najdete v tématu [architektura VSTO doplňky](../vsto/architecture-of-vsto-add-ins.md).  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
> [!NOTE]  
>  Máte zájem o vývoji řešení, které rozšiřují Office prostředí napříč [více platforem](https://dev.office.com/add-in-availability)? Podívejte se na [Office Add in modelu](https://dev.office.com/docs/add-ins/overview/office-add-ins). Doplňky Office mají malé nároky ve srovnání s doplňků VSTO a řešení a můžete je vytvořit pomocí téměř jakoukoli webové programování technologie, jako je například HTML5, JavaScript, CSS3 a XML.  
  
## <a name="create-an-outlook-vsto-add-in-project"></a>Vytvoření projektu doplňku aplikace Outlook VSTO  
 Vytváření projektů Outlook pomocí **doplněk aplikace Outlook** šablona projektu v **nový projekt** dialogové okno. Tato šablona obsahuje požadované odkazy na sestavení a soubory projektu.  
  
 Další informace o tom, jak vytvořit projekt VSTO Add-in najdete v tématu [postupy: vytvoření Office projekty v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md). Další informace o šablonách projektů najdete v tématu [Přehled šablon projektů Microsoft Office](../vsto/office-project-templates-overview.md).  
  
## <a name="outlook-vsto-add-in-programming-model"></a>Outlook doplňku VSTO programovací model  
 Při vytvoření projektu doplňku VSTO pro Outlook, Visual Studio vytvoří třídu s názvem `ThisAddIn`, což je základ pro vaše řešení. Tato třída poskytuje výchozí bod pro zápis kódu a taky zpřístupňuje objektový model aplikace Outlook k vaší doplňku VSTO.  
  
 Další informace o `ThisAddIn` třídy a další funkce, které můžete použít VSTO Add-in, najdete v části [doplňků Program VSTO](../vsto/programming-vsto-add-ins.md).  
  
## <a name="automate-outlook-by-using-the-outlook-object-model"></a>Automatizace aplikace Outlook pomocí objektového modelu aplikace Outlook  
 Model objektu aplikace zpřístupní mnoho typů, které můžete použít k automatizaci aplikace Outlook. Tyto typy umožňují napsat kód k provádění běžných úloh:  
  
-   Prostřednictvím kódu programu vytvoření a odeslání e-mailových zpráv.  
  
-   Odeslání nových žádostí o schůzku.  
  
-   Hledání položek v složky aplikace Outlook.  
  
 Další informace najdete v tématu [přehled modelu objektů aplikace Outlook](../vsto/outlook-object-model-overview.md).  
  
## <a name="customize-the-user-interface-of-an-outlook-application"></a>Přizpůsobení uživatelského rozhraní aplikace Outlook  
  
|Úloha|Další informace|  
|----------|--------------------------|  
|Přidáte vlastní karty na pásu karet Kontrola aplikace Outlook.|[Přehled pásu karet](../vsto/ribbon-overview.md)|  
|Přidáte vlastní skupiny do předdefinované karty v Kontrola aplikace Outlook.|[Postupy: Přizpůsobení předdefinované karty](../vsto/how-to-customize-a-built-in-tab.md)|  
|Přidání vlastního podokna úloh zobrazené v Kontrola aplikace Outlook|[Vlastní podokna úloh](../vsto/custom-task-panes.md).|  
|Přidání oblasti formuláře, který rozšiřuje nebo nahradí existující formulářů aplikace Outlook.|[Vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md)|  
  
 Další informace o přizpůsobení uživatelského rozhraní aplikace Outlook a další aplikace Microsoft Office, najdete v části [přizpůsobení uživatelského rozhraní Office](../vsto/office-ui-customization.md).  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Přehled modelu objektů aplikace Outlook](../vsto/outlook-object-model-overview.md)|Obsahuje přehled objektů, které jsou dostupné ve model objektu aplikace.|  
|[Vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md)|Popisuje nástroje poskytované subsystémem pro Visual Studio, které usnadňují návrh, vyvíjet a ladit oblasti formuláře.|  
|[Návod: Vytvoření vaší první VSTO Add-In pro aplikaci Outlook](../vsto/walkthrough-creating-your-first-vsto-add-in-for-outlook.md)|Ukazuje, jak vytvořit doplňku VSTO pro aplikaci Microsoft Office Outlook.|  
|[Outlook 2010 v vývoj pro Office](http://go.microsoft.com/fwlink/?LinkId=199013)|Oblasti v knihovně MSDN, kde můžete najít články a referenční dokumentace o vývoji řešení pro aplikaci Outlook (nejsou specifické pro vývoj pro Office pomocí sady Visual Studio).|  
  
  