---
title: "Postupy: povolení kódu spuštění na pozadí dokumentů s omezenými oprávněními | Microsoft Docs"
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
- permissions [Office development in Visual Studio]
- IRM [Office development in Visual Studio]
- code [Office development in Visual Studio], running behind restricted documents
- documents [Office development in Visual Studio], restricted permissions
- Office documents [Office development in Visual Studio, restricted permissions
ms.assetid: d037eae5-cf83-4be0-85ba-05e9f7d570e1
caps.latest.revision: "27"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 2f3ff7f7bb76962e22705fc5c0d42fdf7568ff97
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-permit-code-to-run-behind-documents-with-restricted-permissions"></a>Postupy: Povolení spuštění kódu na pozadí dokumentů s omezenými oprávněními
  Omezit oprávnění k dokumentu nebo sešitu, můžete použít funkci Správa informačních práv (IRM) systému Microsoft Office. Ve výchozím nastavení není povoleno spustit kód s omezeným přístupem dokument aplikace Microsoft Office Word nebo sešitu aplikace Microsoft Office Excel. Výchozí nastavení můžete změnit tak, aby vaše rozšíření spravovaného kódu můžete přístup k modelu objektu a řešení bude fungovat.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Musí být Autor dokumentu nebo sešitu nebo mají úplný přístup, abyste mohli změnit nastavení oprávnění.  
  
### <a name="to-permit-code-to-run-behind-documents-with-restricted-permissions"></a>K povolení kód pro spuštění pozadí dokumentů s omezenými oprávněními  
  
1.  Otevřete dokument nebo sešit v aplikaci Word nebo Excel.  
  
2.  Klikněte na tlačítko **soubor** kartě, přejděte na **Příprava**, přejděte na příkaz **omezit oprávnění**a potom klikněte na **omezený přístup**.  
  
    > [!NOTE]  
    >  Při prvním použití zobrazí se výzva k instalaci klienta Windows Rights Management. Po instalaci klienta, možná budete muset zopakujte kroky.  
  
3.  V **oprávnění** dialogové okno, vyberte **omezit oprávnění k tomuto dokumentu**a potom klikněte na **další možnosti**.  
  
4.  V části **další oprávnění pro uživatele**, vyberte **přístup k obsahu prostřednictvím kódu programu**.  
  
 Word či Excel bude povolit programový přístup k objektu modelu.  
  
## <a name="see-also"></a>Viz také  
 [Přehled rozšíření spravovaného kódu a Information Rights Management](../vsto/information-rights-management-and-managed-code-extensions-overview.md)   
 [Ochrana dokumentů v řešeních na úrovni dokumentu](../vsto/document-protection-in-document-level-solutions.md)   
 [Ochrana heslem v dokumentech Office](../vsto/password-protection-on-office-documents.md)   
 [Návrh a vytváření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)   
 [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)   
 [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)  
  
  