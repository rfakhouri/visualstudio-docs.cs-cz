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
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 1950a75eeee6f99a03346dde53317b30824a35f4
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53990656"
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
