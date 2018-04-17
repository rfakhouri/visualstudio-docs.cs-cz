---
title: 'Postupy: verze publikování ClickOnce sadu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, setting publish version
- publishing, ClickOnce
- Publish Version property
ms.assetid: 06f15504-6385-40a6-b01d-cd90ca36dc73
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: a0f96a3837a2c3a05a8fac20a9b6e5d4448f9c7e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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
 [Postupy: Publikování aplikace ClickOnce pomocí průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)