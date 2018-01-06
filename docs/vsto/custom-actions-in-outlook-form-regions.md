---
title: "Vlastní akce v aplikaci Outlook formuláři oblasti | Microsoft Docs"
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
- form regions [Office development in Visual Studio], custom actions
- custom actions [Office development in Visual Studio]
ms.assetid: 583fd5f0-aafa-4858-9c54-38a9fdf3bede
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 89b49139db9d91ba742caeb80308f9175195a843
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="custom-actions-in-outlook-form-regions"></a>Vlastní akce v oblastech formulářů aplikace Outlook
  Akce zobrazení tlačítek, které umožní uživatelům reagovat na položku Microsoft Office Outlook. Například reagovat na položku e-mailu, uživatelé kliknout **odpověď**, **Odpovědět všem**, nebo **dál** tlačítka akce. Všechny tyto akce vytvoří novou položku e-mailu a naplní položky pole pomocí informací z původní položky.  
  
 Můžete vytvořit vlastní akce, které se otevře jakýkoli druh položky aplikace Outlook. Například můžete přidat vlastní akce, které se otevře novou položku události nebo úkolu. Nastavit vlastnosti vlastní akce nebo použít vlastní kód k vyplnění pole nové položky. Vlastní akce se zobrazí v **vlastní akce** rozevíracího seznamu položku, která je otevřený v okně kontroly aplikace Outlook.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="adding-custom-actions-to-a-form-region"></a>Přidání vlastních akcí, které oblasti formuláře  
 Chcete-li přidat vlastní akce do oblasti formuláře, použijte **vlastní akce** dialogové okno. Můžete otevřít **vlastní akce** dialogovém okně **Průzkumníku řešení** rozšířením **Manifest** uzlu, vyberete **CustomActions**vlastnost a potom kliknutím na tlačítko se třemi tečkami (![ASP.NET – Návrhář mobilních řešení elipsy](../sharepoint/media/mwellipsis.gif "ASP.NET – Návrhář mobilních řešení elipsy")).  
  
 Můžete použít **vlastní akce** dialogové okno k zadání *cíle formuláře*. Formulář Cíl je formulář, který se zobrazí, když uživatel provede vlastní akci.  
  
 Můžete také **vlastní akce** chcete určit, jakým způsobem chcete informace z původní položky se objeví v cílovém formuláři.  
  
 Následující tabulka popisuje vlastnosti, které jsou k dispozici v **vlastní akce** dialogové okno.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|**AddressLike**|Určuje, jak bude řešit cílového formuláře.|  
|**Text**|Určuje, jak je text původní položce připojí k cílového formuláře.|  
|**Povoleno**|Určuje, zda je povoleno vlastní akci. Pokud je tato vlastnost nastavena na **false**, vlastní akce je zakázána.|  
|**– Metoda**|Určuje typ odpovědi, které jsou k dispozici při provedení vlastní akce. Vlastní akce můžete odeslat formulář, otevřete formulář nebo výzvy, zda budou chtít poslat nebo otevřít formulář.|  
|**Jméno**|Určuje vnitřní název, který můžete použít, chcete-li tato vlastní akce v kódu.|  
|**ShowOnRibbon**|Určuje, jestli se má zobrazit na pásu karet původní položky vlastní akci.|  
|**SubjectPrefix**|Určuje text, který je vložen na začátku řádku předmětu cílového formuláře.|  
|**TargetForm**|Určuje název třídy zpráva cílového formuláře. Můžete například zadat **IPM. Úloha** otevřete formulář úloh.|  
|**Název**|Určuje popisek tlačítka vlastní akce.|  
  
## <a name="customizing-a-custom-action-at-run-time"></a>Přizpůsobení vlastní akce v době běhu  
 Chování můžete také přidat vlastní akci pomocí kódu. Například můžete přidat kód, který přebírá jména příjemců e-mailu a přidá tyto názvy jako účastníky v nové položky schůzku. K tomuto účelu zpracování [CustomAction](http://msdn.microsoft.com/library/office/ff862186.aspx) události [MailItem objekt](http://msdn.microsoft.com/library/office/ff861332.aspx).  
  
## <a name="see-also"></a>Viz také  
 [Vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md)   
 [Postupy: Návrh oblasti formuláře aplikace Outlook](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Přidružení oblasti formuláře k třídě zpráv aplikace Outlook](../vsto/associating-a-form-region-with-an-outlook-message-class.md)  
  
  