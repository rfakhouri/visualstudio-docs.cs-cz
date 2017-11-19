---
title: "Postupy: verze publikování ClickOnce sadu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, setting publish version
- publishing, ClickOnce
- Publish Version property
ms.assetid: 06f15504-6385-40a6-b01d-cd90ca36dc73
caps.latest.revision: "9"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: be66edb3880e8ef91f8fd95d7f11fe465322451f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-set-the-clickonce-publish-version"></a>Postupy: Nastavení verze publikování ClickOnce
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] `Publish Version` Vlastnost určuje, zda publikovaná aplikace bude považována za aktualizace. Jednotlivé verze čas se zvýší, aplikace bude publikována jako aktualizace.  
  
 `Publish Version` Vlastnost lze nastavit u **publikovat** stránky **Návrhář projektu**.  
  
> [!NOTE]
>  Není možnost projektu, se automaticky zvýší `Publish Version` vlastnost pokaždé, když je aplikace publikována; tato možnost je povolená ve výchozím nastavení. Další informace najdete v tématu [postup: automaticky zvýší verze publikování ClickOnce](../deployment/how-to-automatically-increment-the-clickonce-publish-version.md).  
  
### <a name="to-change-the-publish-version"></a>Chcete-li změnit verze publikování  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídce klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte **publikovat** kartě.  
  
3.  V **verze publikování** pole, zvýší **hlavní**, **menší**, **sestavení**, nebo **revize** verze čísla.  
  
    > [!NOTE]
    >  Neměly nikdy snížit číslo verze; tak můžete způsobit nepředvídatelné chování aktualizace.  
  
## <a name="see-also"></a>Viz také  
 [Výběr strategie aktualizace ClickOnce](../deployment/choosing-a-clickonce-update-strategy.md)   
 [Postupy: automaticky verze publikování ClickOnce přírůstku](../deployment/how-to-automatically-increment-the-clickonce-publish-version.md)   
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Postupy: publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)