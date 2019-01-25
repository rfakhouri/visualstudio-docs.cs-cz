---
title: 'Postupy: Hledání konkrétního kontaktu prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- contacts [Office development in Visual Studio], searching
- searching contacts
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 84621a8e31750b61ad2fdb06a6923454f6dc1ef7
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54873467"
---
# <a name="how-to-programmatically-search-for-a-specific-contact"></a>Postupy: Hledání konkrétního kontaktu prostřednictvím kódu programu
  Tento příklad vyhledá kontaktů aplikace Outlook pro konkrétní kontakt podle křestní jméno a příjmení. Příklad předpokládá, že kontakt s názvem **Jan Evans** existuje ve složce kontaktů.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>Příklad  
 [!code-csharp[Trin_Outlook_RL_SearchForContact#1](../vsto/codesnippet/CSharp/trin_outlook_rl_searchforcontact/thisaddin.cs#1)]
 [!code-vb[Trin_Outlook_RL_SearchForContact#1](../vsto/codesnippet/VisualBasic/trin_outlook_rl_searchforcontact/thisaddin.vb#1)]  
  
## <a name="see-also"></a>Viz také:  
 [Práce s položkami kontaktů](../vsto/working-with-contact-items.md)   
 [Začínáme s programováním doplňků VSTO](../vsto/getting-started-programming-vsto-add-ins.md)  
