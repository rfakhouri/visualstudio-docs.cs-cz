---
title: "Postupy: hledání v rámci konkrétní složky prostřednictvím kódu programu | Microsoft Docs"
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
helpviewer_keywords: Outlook folders [Office development in Visual Studio], searching
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 71b9da77857bb82a27f6bd6ae057a1df1fca8a1d
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
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
  
  