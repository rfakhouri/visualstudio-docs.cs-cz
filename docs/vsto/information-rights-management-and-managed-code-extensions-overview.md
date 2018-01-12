---
title: "Přehled rozšíření spravovaného kódu a Information Rights Management | Microsoft Docs"
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
- Information Rights Management [Office development in Visual Studio]
- workbooks [Office development in Visual Studio], restricted permissions
- IRM [Office development in Visual Studio]
- documents [Office development in Visual Studio], restricted permissions
- rights management [Office development in Visual Studio]
- Office documents [Office development in Visual Studio, restricted permissions
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 561f17acd17cb34892d3f2d4f0eefa05dfced0e4
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="information-rights-management-and-managed-code-extensions-overview"></a>Přehled správy přístupových práv k informacím a rozšíření spravovaného kódu
  Aplikace Microsoft Office Word a Microsoft Office Excel poskytují Správa informačních práv (IRM), funkce, která vám mohou pomoci zabránit neoprávněným osobám v zobrazení nebo změna citlivé informace. Podrobnosti o tom, jak funguje Information Rights Management najdete v tématu nápovědy v konkrétní aplikaci Office.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
## <a name="running-code-behind-documents-with-restricted-permissions"></a>Spuštění kódu na pozadí dokumentů s omezenými oprávněními  
 Pokud vaše řešení obsahuje dokument nebo sešit, který používá technologii IRM, ve výchozím nastavení, Word a Excel nepovoluje spuštění kódu. Pokud jsou Autor dokumentu nebo mají úplný přístup, můžete změnit výchozí nastavení tak, aby vaše řešení funguje. Další informace najdete v tématu [postupy: povolení kód pro spuštění za dokumentů s omezenými oprávněními](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md).  
  
 IRM brání použití <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ServerDocument> načíst nebo pracovat s daty, která se uloží do mezipaměti v dokumentu.  
  
## <a name="end-users-restricting-permissions-to-documents-that-use-managed-code-extensions"></a>Koncoví uživatelé omezení oprávnění k dokumentům, které používají rozšíření spravovaného kódu  
 Každý, kdo má plný přístup k dokumentu nebo sešitu ve vašem řešení použít IRM a omezit oprávnění. Pokud koncový uživatel v účetním oddělení používá řešení, které automaticky naplní na listu s daty z databáze, tento uživatel může například umožňuje změnit přístup jenom na osoby ve své oddělení a přístup pro čtení k ostatním. Pokud uživatel přidá omezená oprávnění, ve výchozím nastavení, nelze spustit kódu listu a listu se nenaplní s daty.  
  
 Chcete-li problém vyřešit, někdo s plný přístup k dokumentu nebo sešitu musíte změnit výchozí nastavení oprávnění povolit programový přístup k modelu objektu. Další informace najdete v tématu [postupy: povolení kód pro spuštění za dokumentů s omezenými oprávněními](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md).  
  
## <a name="see-also"></a>Viz také  
 [Ochrana dokumentů v řešeních na úrovni dokumentu](../vsto/document-protection-in-document-level-solutions.md)   
 [Ochrana heslem v dokumentech Office](../vsto/password-protection-on-office-documents.md)   
 [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)   
 [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)   
 [Navrhování a tvorba řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)  
  
  