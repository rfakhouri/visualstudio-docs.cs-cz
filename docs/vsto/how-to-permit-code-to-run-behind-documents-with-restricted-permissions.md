---
title: 'Postupy: povolení kód pro spuštění pozadí dokumentů s omezenými oprávněními'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
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
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 3b02afb7008233c720feae179b4726f9958a44af
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35255283"
---
# <a name="how-to-permit-code-to-run-behind-documents-with-restricted-permissions"></a>Postupy: povolení kód pro spuštění pozadí dokumentů s omezenými oprávněními
  Omezit oprávnění k dokumentu nebo sešitu, můžete použít funkci Správa informačních práv (IRM) systému Microsoft Office. Ve výchozím nastavení není povoleno spustit kód s omezeným přístupem dokument aplikace Microsoft Office Word nebo sešitu aplikace Microsoft Office Excel. Výchozí nastavení můžete změnit tak, aby vaše rozšíření spravovaného kódu můžete přístup k modelu objektu a řešení bude fungovat.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Musí být Autor dokumentu nebo sešitu nebo mají úplný přístup, abyste mohli změnit nastavení oprávnění.  
  
## <a name="to-permit-code-to-run-behind-documents-with-restricted-permissions"></a>K povolení kód pro spuštění pozadí dokumentů s omezenými oprávněními  
  
1.  Otevřete dokument nebo sešit v aplikaci Word nebo Excel.  
  
2.  Klikněte na tlačítko **soubor** kartě, přejděte na **Příprava**, přejděte na příkaz **omezit oprávnění**a potom klikněte na **omezený přístup**.  
  
    > [!NOTE]  
    >  Při prvním použití zobrazí se výzva k instalaci klienta Windows Rights Management. Po instalaci klienta, možná budete muset zopakujte kroky.  
  
3.  V **oprávnění** dialogové okno, vyberte **omezit oprávnění k tomuto dokumentu**a potom klikněte na **další možnosti**.  
  
4.  V části **další oprávnění pro uživatele**, vyberte **přístup k obsahu prostřednictvím kódu programu**.  
  
 Word či Excel bude povolit programový přístup k objektu modelu.  
  
## <a name="see-also"></a>Viz také:  
 [Přehled rozšíření spravovaného kódu a Správa přístupových práv](../vsto/information-rights-management-and-managed-code-extensions-overview.md)   
 [Ochrana dokumentů v řešeních na úrovni dokumentu](../vsto/document-protection-in-document-level-solutions.md)   
 [Ochrana heslem v dokumentech Office](../vsto/password-protection-on-office-documents.md)   
 [Návrh a vytvoření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)   
 [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)   
 [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)  
  
  