---
title: 'Postupy: zákaz aktivace adresy URL aplikací ClickOnce pomocí návrháře | Microsoft Docs'
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
- disallowURLActivation
- URL activation, ClickOnce applications
- ClickOnce deployment, URL activation
ms.assetid: a337a582-e67c-409a-b52e-607cd1a8fc57
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 0300b81a73deef2dabb89631f778d56ff89e820e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-disable-url-activation-of-clickonce-applications-by-using-the-designer"></a>Postupy: Zákaz aktivace adresy URL aplikací ClickOnce pomocí Návrháře
Obvykle [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace se automaticky spustí hned po instalaci z webového serveru. Z bezpečnostních důvodů se můžete rozhodnout pro toto chování zakázat a sdělit uživatelům, a spusťte aplikaci z **spustit** nabídky místo. Následující postup popisuje zákaz aktivace adresy URL.  
  
 Tento postup lze použít pouze pro [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace nainstalované v počítači uživatele z webového serveru. Nelze zadat pro pouze online aplikace, které lze spustit pouze pomocí jejich adresy URL. Další informace o rozdílu mezi pouze online a nainstalovanými aplikacemi najdete v tématu [Výběr strategie nasazení ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md).  
  
 Tento postup používá [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Tento úkol můžete také provést pomocí [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]. Další informace najdete v tématu [postupy: zakázání aktivace adresy URL z aplikace ClickOnce](../deployment/how-to-disable-url-activation-of-clickonce-applications.md).  
  
## <a name="procedure"></a>Postup  
  
#### <a name="to-disable-url-activation-for-your-application"></a>Chcete-li zákaz aktivace adresy URL pro aplikaci  
  
1.  Klikněte pravým tlačítkem na název projektu v **Průzkumníku řešení**a klikněte na tlačítko **vlastnosti**.  
  
2.  Na **vlastnosti** klikněte na tlačítko **publikovat** kartě.  
  
3.  Klikněte na tlačítko **možnosti**.  
  
4.  Klikněte na tlačítko **manifesty**.  
  
5.  Zaškrtněte políčko s názvem bez přípony **blokovat aktivace prostřednictvím adresy URL aplikace**.  
  
6.  Nasazení aplikace.  
  
## <a name="see-also"></a>Viz také  
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)