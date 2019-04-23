---
title: 'Postupy: Zákaz aktivace adresy URL aplikací ClickOnce pomocí návrháře | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
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
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 27690ab275d0c7ef2a090fa8ef2e42887ae9daeb
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60043846"
---
# <a name="how-to-disable-url-activation-of-clickonce-applications-by-using-the-designer"></a>Postupy: Zakázání aktivace adresy URL aplikací ClickOnce pomocí Návrháře
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Obvykle [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikace se automaticky spustí ihned po jeho instalaci z webového serveru. Z bezpečnostních důvodů se můžete rozhodnout pro toto chování zakázat a že se uživatelé můžou spouštět aplikace z **Start** nabídky místo. Následující postup popisuje, jak zákaz aktivace adresy URL.  
  
 Tento postup lze použít pouze pro [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikace nainstalované v počítači uživatele z webového serveru. Nelze použít pro online jen pro aplikace, které lze spustit pouze pomocí jejich adresy URL. Další informace o rozdílech mezi pouze v režimu online a nainstalovaných aplikací, najdete v části [Výběr strategie nasazení ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md).  
  
 Tento postup používá [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Tuto úlohu lze provést také pomocí [!INCLUDE[winsdklong](../includes/winsdklong-md.md)]. Další informace najdete v tématu [jak: Zákaz aktivace adresy URL aplikací ClickOnce](../deployment/how-to-disable-url-activation-of-clickonce-applications.md).  
  
## <a name="procedure"></a>Postup  
  
#### <a name="to-disable-url-activation-for-your-application"></a>Chcete-li zákaz aktivace adresy URL pro vaši aplikaci  
  
1. Klikněte pravým tlačítkem na název vašeho projektu v **Průzkumníka řešení**a klikněte na tlačítko **vlastnosti**.  
  
2. Na **vlastnosti** stránky, klikněte na tlačítko **publikovat** kartu.  
  
3. Klikněte na tlačítko **možnosti**.  
  
4. Klikněte na tlačítko **manifesty**.  
  
5. Zaškrtněte políčko s popiskem **blokovat aplikaci při aktivaci prostřednictvím adresy URL**.  
  
6. Při nasazování aplikace.  
  
## <a name="see-also"></a>Viz také  
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)
