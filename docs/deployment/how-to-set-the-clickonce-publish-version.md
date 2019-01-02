---
title: 'Postupy: Nastavení publikování ClickOnce verze | Dokumentace Microsoftu'
ms.date: 11/04/2016
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bd0f38fda93d1a91e72c547bdfe230354988da9d
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53869109"
---
# <a name="how-to-set-the-clickonce-publish-version"></a>Postupy: Nastavení publikování ClickOnce verze
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] `Publish Version` Vlastnost určuje, zda aplikace, které publikujete bude považována za aktualizace. Každá verze se zvýší, aplikace bude publikována jako aktualizace.  
  
 `Publish Version` Vlastnost lze nastavit na **publikovat** stránku **Návrháře projektu**.  
  
> [!NOTE]
>  Projekt možnost, bude automaticky zvýší `Publish Version` vlastnost pokaždé, když je aplikace publikována, tato možnost je standardně povolená. Další informace najdete v tématu [jak: Automaticky ClickOnce Inkrementace verze publikování](../deployment/how-to-automatically-increment-the-clickonce-publish-version.md).  
  
### <a name="to-change-the-publish-version"></a>Chcete-li změnit verzi publikování  
  
1.  S projekt vybraný v **Průzkumníka řešení**na **projektu** klikněte na nabídku **vlastnosti**.  
  
2.  Klikněte na tlačítko **publikovat** kartu.  
  
3.  V **publikovat verzi** pole, zvýší **hlavní**, **menší**, **sestavení**, nebo **revize** verze čísla.  
  
    > [!NOTE]
    >  Nikdy by měla snížit na číslo verze. To uděláte tak může způsobit nepředvídatelné chování aktualizace.  
  
## <a name="see-also"></a>Viz také:  
 [Volba strategie aktualizace ClickOnce](../deployment/choosing-a-clickonce-update-strategy.md)   
 [Postupy: Automaticky ClickOnce Inkrementace verze publikování](../deployment/how-to-automatically-increment-the-clickonce-publish-version.md)   
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Postupy: Publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)