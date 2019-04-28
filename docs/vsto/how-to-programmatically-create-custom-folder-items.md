---
title: 'Postupy: Vytváření vlastních položek složek prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Outlook folders [Office development in Visual Studio], creating
- Outlook folders [Office development in Visual Studio], custom
author: John-Hart
ms.author: johnhart
ms.workload:
- office
ms.openlocfilehash: f10bb578d2d83c6e3a07477078245f281e4e3820
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62575062"
---
# <a name="how-to-programmatically-create-custom-folder-items"></a>Postupy: Vytváření vlastních položek složek prostřednictvím kódu programu
  Tento příklad vytvoří novou složku v aplikaci Microsoft Office Outlook. Jméno uživatele, který je přihlášen se používá pro název složky.

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

## <a name="example"></a>Příklad
 [!code-csharp[Trin_OL_CustFolderItem#1](../vsto/codesnippet/CSharp/Trin_OL_CustFolderItem/thisaddin.cs#1)]

## <a name="see-also"></a>Viz také:
- [Práce se složkami](../vsto/working-with-folders.md)
- [Postupy: Přidávání položky ke kontaktům aplikace Outlook prostřednictvím kódu programu](../vsto/how-to-programmatically-add-an-entry-to-outlook-contacts.md)
- [Postupy: Vytváření událostí prostřednictvím kódu programu](../vsto/how-to-programmatically-create-appointments.md)
