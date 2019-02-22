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
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56598021"
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
