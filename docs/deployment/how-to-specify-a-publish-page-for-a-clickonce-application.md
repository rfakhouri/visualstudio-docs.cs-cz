---
title: 'Postupy: určení stránky publikování pro aplikaci ClickOnce | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications [ClickOnce], specifying publish page
- Publish Page property
- publishing, ClickOnce
- ClickOnce deployment, specifying publish page
ms.assetid: 9d70eebb-bdee-4b42-8e7e-7a07e199bdf7
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 20f7f09688fbeeb3ccd9d79b35dd334bdba888f5
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/19/2018
ms.locfileid: "36235008"
---
# <a name="how-to-specify-a-publish-page-for-a-clickonce-application"></a>Postupy: Určení stránky publikování pro aplikaci ClickOnce
Při publikování [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace, je generována a publikována spolu s aplikací výchozí webové stránky (publish.htm). Tato stránka obsahuje název aplikace, odkaz na instalaci aplikace a všechny požadované součásti a odkaz na téma nápovědy popisující [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]. **Publikovat stránku** vlastnost pro svůj projekt můžete zadat název webové stránky pro vaše [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace.  
  
 Jakmile byl zadán stránky publikování, při příštím publikování se ho bude zkopírován do umístění pro publikování; nebude přepsány, pokud znovu publikovat. Pokud chcete přizpůsobit vzhled stránky, můžete tak učinit bez obav o ztrátu změn. Další informace najdete v tématu [postupy: Úprava výchozí webové stránky ClickOnce](../deployment/how-to-customize-the-default-web-page-for-a-clickonce-application.md).  
  
 **Publikovat stránku** vlastnost lze nastavit **možnosti publikování** dialogové okno, přístupný z **publikovat** podokně **Návrhář projektu**.  
  
### <a name="to-specify-a-custom-web-page-for-a-clickonce-application"></a>Chcete-li určit vlastní webovou stránku pro aplikaci ClickOnce  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídce klikněte na tlačítko **vlastnosti**.  
  
2.  Vyberte **publikovat** podokně.  
  
3.  Klikněte na tlačítko **možnosti** tlačítko Otevřít **možnosti publikování** dialogové okno.  
  
4.  Klikněte na tlačítko **nasazení**.  
  
5.  V **možnosti publikování** dialogové okno pole, ujistěte se, že **webovou stránku otevřít nasazení po publikování** políčko (měl by být vybrán ve výchozím nastavení).  
  
6.  V **nasazení webové stránky** pole, zadejte název pro svou webovou stránku a pak klikněte na tlačítko **OK**.  
  
### <a name="to-prevent-the-publish-page-from-launching-each-time-you-publish"></a>Chcete zabránit spouštění pokaždé, když publikujete stránky publikování  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídce klikněte na tlačítko **vlastnosti**.  
  
2.  Vyberte **publikovat** podokně.  
  
3.  Klikněte na tlačítko **možnosti** tlačítko Otevřít **možnosti publikování** dialogové okno.  
  
4.  Klikněte na tlačítko **nasazení**.  
  
5.  V **možnosti publikování** dialogové okno, zrušte **webovou stránku otevřít nasazení po publikování** zaškrtávací políčko.  
  
## <a name="see-also"></a>Viz také  
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Postupy: publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)   
 [Postupy: přizpůsobení ClickOnce výchozí webové stránky](../deployment/how-to-customize-the-default-web-page-for-a-clickonce-application.md)