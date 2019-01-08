---
title: 'Postupy: Programově přidružte webovou stránku složky aplikace Outlook'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- folders [Office development in Visual Studio], Web pages and
- Outlook [Office development in Visual Studio], Web pages attached to folders
- Web pages [Office development in Visual Studio], Outlook folders
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: b6dc6bec7ecbf872d10045cb24e007edec893585
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54089632"
---
# <a name="how-to-programmatically-associate-a-web-page-with-an-outlook-folder"></a>Postupy: Programově přidružte webovou stránku složky aplikace Outlook
  Tento příklad vyhledá složku s názvem `HtmlView` v aplikaci Microsoft Office Outlook. Pokud složka neexistuje, kód vytvoří složku a přiřadí ji na webové stránce. Pokud složka existuje, kód zobrazí obsah složky.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>Příklad  
 [!code-csharp[Trin_OL_HTMLFolder#1](../vsto/codesnippet/CSharp/Trin_OL_HTMLFolder/thisaddin.cs#1)]  
  
## <a name="see-also"></a>Viz také:  
 [Práce se složkami](../vsto/working-with-folders.md)   
 [Postupy: Programově načítání složek podle názvu](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)   
 [Postupy: Vytváření vlastních položek složek prostřednictvím kódu programu](../vsto/how-to-programmatically-create-custom-folder-items.md)  
