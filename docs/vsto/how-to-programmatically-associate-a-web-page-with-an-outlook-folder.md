---
title: "Postupy: programové přidružení webové stránky ke složce aplikace Outlook | Microsoft Docs"
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
- folders [Office development in Visual Studio], Web pages and
- Outlook [Office development in Visual Studio], Web pages attached to folders
- Web pages [Office development in Visual Studio], Outlook folders
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 0fa0ccb3035bc4be8e316c96bd5da8c166dcb4b8
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-associate-a-web-page-with-an-outlook-folder"></a>Postup: Přidružení webové stránky ke složce aplikace Outlook prostřednictvím kódu programu
  Tento příklad zkontroluje složku s názvem `HtmlView` v aplikaci Microsoft Office Outlook. Pokud složka neexistuje, kód vytvoří složku a přiřadí na webové stránce. Pokud složka existuje, kód zobrazí obsah složky.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>Příklad  
 [!code-csharp[Trin_OL_HTMLFolder#1](../vsto/codesnippet/CSharp/Trin_OL_HTMLFolder/thisaddin.cs#1)]  
  
## <a name="see-also"></a>Viz také  
 [Práce se složkami](../vsto/working-with-folders.md)   
 [Postupy: načítání složek podle názvu prostřednictvím kódu programu](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)   
 [Postupy: Vytváření vlastních položek složek prostřednictvím kódu programu](../vsto/how-to-programmatically-create-custom-folder-items.md)  
  
  