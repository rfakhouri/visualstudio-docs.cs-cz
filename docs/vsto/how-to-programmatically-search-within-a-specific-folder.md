---
title: 'Postupy: hledání v rámci konkrétní složky prostřednictvím kódu programu | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
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
ms.openlocfilehash: aedddb0eab79e66d9d5a41d70a4907a2f22951ab
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-search-within-a-specific-folder"></a>Postupy: Hledání v rámci konkrétní složky prostřednictvím kódu programu
  Tento příklad kódu používá `Find` a `FindNext` metody chcete hledat text v poli subjekt e-mailových zpráv, které jsou v **doručené pošty**. Tato metoda používá řetězec filtru pro vyhledání písmeno T jako počáteční písmeno `Subject` text.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>Příklad  
 [!code-csharp[Trin_OL_SearchFolder#1](../vsto/codesnippet/CSharp/Trin_OL_SearchFolder/thisaddin.cs#1)]  
  
## <a name="see-also"></a>Viz také  
 [Práce se složkami](../vsto/working-with-folders.md)   
 [Přehled modelu objektů aplikace Outlook](../vsto/outlook-object-model-overview.md)   
 [Postup: Načítání složek podle názvu prostřednictvím kódu programu](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)  
  
  