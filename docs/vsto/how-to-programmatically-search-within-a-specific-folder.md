---
title: 'Postupy: Hledání v rámci konkrétní složky prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Outlook folders [Office development in Visual Studio], searching
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 1427f0ab69cab2c23a0eeb7638bbc6e21778c55a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53915491"
---
# <a name="how-to-programmatically-search-within-a-specific-folder"></a>Postupy: Hledání v rámci konkrétní složky prostřednictvím kódu programu
  Tento příklad kódu používá `Find` a `FindNext` metody k vyhledání textu v poli Předmět e-mailové zprávy, které jsou v **doručené pošty**. Tato metoda používá řetězec filtru k vyhledání písmeno T jako počáteční písmeno `Subject` text.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>Příklad  
 [!code-csharp[Trin_OL_SearchFolder#1](../vsto/codesnippet/CSharp/Trin_OL_SearchFolder/thisaddin.cs#1)]  
  
## <a name="see-also"></a>Viz také:  
 [Práce se složkami](../vsto/working-with-folders.md)   
 [Přehled modelu objektů aplikace Outlook](../vsto/outlook-object-model-overview.md)   
 [Postupy: Programově načítání složek podle názvu](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)  
