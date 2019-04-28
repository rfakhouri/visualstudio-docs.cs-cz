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
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: e83f8b7f6bcdb790b5e545aa76426bc05f0735f5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62817306"
---
# <a name="how-to-programmatically-associate-a-web-page-with-an-outlook-folder"></a>Postupy: Programově přidružte webovou stránku složky aplikace Outlook
  Tento příklad vyhledá složku s názvem `HtmlView` v aplikaci Microsoft Office Outlook. Pokud složka neexistuje, kód vytvoří složku a přiřadí ji na webové stránce. Pokud složka existuje, kód zobrazí obsah složky.

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

## <a name="example"></a>Příklad
 [!code-csharp[Trin_OL_HTMLFolder#1](../vsto/codesnippet/CSharp/Trin_OL_HTMLFolder/thisaddin.cs#1)]

## <a name="see-also"></a>Viz také:
- [Práce se složkami](../vsto/working-with-folders.md)
- [Postupy: Programově načítání složek podle názvu](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)
- [Postupy: Vytváření vlastních položek složek prostřednictvím kódu programu](../vsto/how-to-programmatically-create-custom-folder-items.md)
