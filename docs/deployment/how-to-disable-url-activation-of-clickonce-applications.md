---
title: "Postupy: zákaz aktivace adresy URL aplikací ClickOnce | Microsoft Docs"
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
- disallowUrlActivation
- URL activation, ClickOnce applications
- ClickOnce deployment, URL activation
ms.assetid: db31a16b-960f-4264-91d7-c7c40f876068
caps.latest.revision: "9"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 3f94029c682029ad8fa3167314a2d95b51b00648
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-disable-url-activation-of-clickonce-applications"></a>Postupy: Zákaz aktivace adresy URL aplikací ClickOnce
Obvykle [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace se automaticky spustí hned po instalaci z webového serveru. Z bezpečnostních důvodů se můžete rozhodnout pro toto chování zakázat a sdělit uživatelům, aby spuštění aplikace z **spustit** nabídky místo. Následující postup popisuje zákaz aktivace adresy URL.  
  
 Tento postup lze použít pouze pro [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace nainstalované v počítači uživatele z webového serveru. Nelze zadat pro pouze online aplikace, které může být spuštěn pouze pomocí jejich adresy URL. Další informace o rozdílu mezi pouze online a nainstalovanými aplikacemi, najdete v části [Výběr strategie nasazení ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md).  
  
 Tento postup používá [! ZAHRNOUT[winsdklong](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client). Můžete také provést tento postup pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## <a name="procedure"></a>Postup  
  
#### <a name="to-disable-url-activation-for-your-application"></a>Chcete-li zákaz aktivace adresy URL pro aplikaci  
  
1.  Otevřete manifest nasazení v MageUI.exe. Pokud jste zatím žádný nevytvořili, postupujte podle kroků v [návod: Ruční nasazení aplikace ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md).  
  
2.  Vyberte **možnosti nasazení** kartě.  
  
3.  Vymazat **aplikaci po instalaci automaticky spustit** zaškrtávací políčko.  
  
4.  Uložte a podepsání manifestu.  
  
## <a name="see-also"></a>Viz také  
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)