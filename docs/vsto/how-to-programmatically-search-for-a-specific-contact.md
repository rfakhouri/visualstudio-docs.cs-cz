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
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 93f3444745f3c7e6fdaf039cda5a8c95bb717eed
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53902747"
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
