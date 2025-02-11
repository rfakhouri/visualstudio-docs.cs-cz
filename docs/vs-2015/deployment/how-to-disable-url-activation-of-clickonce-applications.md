---
title: 'Postupy: Zákaz aktivace adresy URL aplikací ClickOnce | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- disallowUrlActivation
- URL activation, ClickOnce applications
- ClickOnce deployment, URL activation
ms.assetid: db31a16b-960f-4264-91d7-c7c40f876068
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 75a98706858323693ec01ec3c3420a6d2d25ffef
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65697216"
---
# <a name="how-to-disable-url-activation-of-clickonce-applications"></a>Postupy: Zakázání aktivace adresy URL aplikací ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Obvykle [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikace se automaticky spustí ihned po jeho instalaci z webového serveru. Z bezpečnostních důvodů se můžete rozhodnout pro toto chování zakázat a že se uživatelé ke spuštění aplikace z **Start** nabídky místo. Následující postup popisuje, jak zákaz aktivace adresy URL.  
  
 Tento postup lze použít pouze pro [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikace nainstalované v počítači uživatele z webového serveru. Nelze použít pro online jen pro aplikace, které lze spustit pouze pomocí jejich adresy URL. Další informace o rozdílu mezi pouze v režimu online a nainstalované aplikace najdete v tématu [Výběr strategie nasazení ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md).  
  
 Tento postup používá [!INCLUDE[winsdklong](../includes/winsdklong-md.md)] nástroj MageUI.exe. Další informace o tomto nástroji najdete v tématu [MageUI.exe (Manifest Generation and Editing Tool, grafický klient)](https://msdn.microsoft.com/library/f9e130a6-8117-49c4-839c-c988f641dc14). Můžete také provést tento postup pomocí [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
## <a name="procedure"></a>Postup  
  
#### <a name="to-disable-url-activation-for-your-application"></a>Chcete-li zákaz aktivace adresy URL pro vaši aplikaci  
  
1. Otevření manifestu nasazení v MageUI.exe. Pokud jste ještě nevytvořili, jednu, postupujte podle kroků v [názorný postup: Ruční nasazení aplikace ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md).  
  
2. Vyberte **možnosti nasazení** kartu.  
  
3. Zrušte **automaticky spustit po instalaci aplikace** zaškrtávací políčko.  
  
4. Uložit a podepsání manifestu.  
  
## <a name="see-also"></a>Viz také  
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)
