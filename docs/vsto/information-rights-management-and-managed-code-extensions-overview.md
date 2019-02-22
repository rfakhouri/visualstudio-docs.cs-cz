---
title: Přehled rozšíření spravovaného kódu a správy přístupových práv
ms.date: 02/02/2017
ms.topic: conceptual
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
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 109f6b85653a842f7c6fc9ce2d2c09b74113bbc7
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56641244"
---
# <a name="information-rights-management-and-managed-code-extensions-overview"></a>Přehled rozšíření spravovaného kódu a správy přístupových práv
  Aplikace Microsoft Office Word a Microsoft Office Excel poskytují Správa informačních práv (IRM), funkce, která vám mohou pomoci zabránit neoprávněným osobám v zobrazení nebo změna citlivé informace. Podrobnosti o tom, jak funguje Information Rights Management najdete v nápovědě v konkrétní aplikaci Office.

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

## <a name="run-code-behind-documents-with-restricted-permissions"></a>Spuštění kódu na pozadí dokumentů s omezenými oprávněními
 Pokud vaše řešení obsahuje dokument nebo sešit, který používá technologii IRM, ve výchozím nastavení, Word a Excel není povoleno spuštění kódu. Pokud autor dokumentu nebo mají úplný přístup, můžete změnit výchozí, takže vaše řešení funguje. Další informace najdete v tématu [jak: Povolit kód ke spuštění pozadí dokumentů s omezenými oprávněními](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md).

 IRM brání použití <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ServerDocument> načíst nebo manipulaci s daty, která se uloží do mezipaměti v dokumentu.

## <a name="end-users-to-restrict-permissions-to-documents-that-use-managed-code-extensions"></a>Koncovým uživatelům možnost omezit oprávnění pro dokumenty, které používají rozšíření spravovaného kódu
 Každý, kdo má úplný přístup k dokumentu nebo sešitu ve vašem řešení můžete omezit oprávnění IRM. Pokud koncový uživatel z účetního oddělení používá řešení, které se automaticky vyplní sešit s daty z databáze, tento uživatel může třeba umožňuje změnit přístup pouze uživatelům ve své oddělení a ostatním uživatelům přístup pro čtení. Když uživatel přidá omezená oprávnění, ve výchozím nastavení, nelze spustit kód za listu a listu nesmí být naplněná daty.

 Chcete-li vyřešit tento problém, někdo s úplné řízení přístupu k dokumentu nebo sešitu musí změnit výchozí nastavení oprávnění povolit programový přístup k objektovému modelu. Další informace najdete v tématu [jak: Povolit kód ke spuštění pozadí dokumentů s omezenými oprávněními](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md).

## <a name="see-also"></a>Viz také:
- [Ochrana dokumentů v řešeních na úrovni dokumentu](../vsto/document-protection-in-document-level-solutions.md)
- [Ochrana dokumentů Office heslem](../vsto/password-protection-on-office-documents.md)
- [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)
- [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)
- [Návrh a vytvoření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)
