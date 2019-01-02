---
title: 'Postupy: Povolit kód ke spuštění pozadí dokumentů s omezenými oprávněními'
ms.date: 02/02/2017
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
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: df2f16a434cd4e2907e3e5d9a6054967b8a6abf9
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53949333"
---
# <a name="how-to-permit-code-to-run-behind-documents-with-restricted-permissions"></a>Postupy: Povolit kód ke spuštění pozadí dokumentů s omezenými oprávněními
  Funkci Správa informačních práv (IRM) systému Microsoft Office můžete použít k omezení oprávnění k dokumentu nebo sešitu. Ve výchozím nastavení nemá oprávnění spustit kódu s omezeným přístupem dokument aplikace Microsoft Office Word nebo sešit aplikace Microsoft Office Excel. Výchozí nastavení můžete změnit tak, aby vaše rozšíření spravovaného kódu můžete přístup k objektu modelu, a vaše řešení bude fungovat.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Musí být autorem dokumentu nebo sešitu nebo mají úplný přístup, abyste mohli změnit nastavení oprávnění.  
  
## <a name="to-permit-code-to-run-behind-documents-with-restricted-permissions"></a>Tak, aby povolovala kód ke spuštění pozadí dokumentů s omezenými oprávněními  
  
1. Otevření dokumentu nebo sešitu v aplikaci Word nebo Excel.  
  
2. Klikněte na tlačítko **souboru** kartu, přejděte na **připravit**, přejděte na **omezit oprávnění**a potom klikněte na tlačítko **omezený přístup**.  
  
   > [!NOTE]  
   >  Při prvním použití zobrazí výzva k instalaci klienta Windows Rights Management. Po instalaci klienta, můžete potřebovat zopakujte kroky.  
  
3. V **oprávnění** dialogu **omezit oprávnění k tomuto dokumentu**a potom klikněte na tlačítko **další možnosti**.  
  
4. V části **další oprávnění pro uživatele**vyberte **programový přístup k obsahu**.  
  
   Programový přístup k objektovému modelu umožní aplikaci Word nebo Excel.  
  
## <a name="see-also"></a>Viz také:  
 [Přehled rozšíření spravovaného kódu a správy přístupových práv](../vsto/information-rights-management-and-managed-code-extensions-overview.md)   
 [Ochrana dokumentů v řešeních na úrovni dokumentu](../vsto/document-protection-in-document-level-solutions.md)   
 [Ochrana dokumentů Office heslem](../vsto/password-protection-on-office-documents.md)   
 [Návrh a vytvoření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)   
 [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)   
 [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)  
