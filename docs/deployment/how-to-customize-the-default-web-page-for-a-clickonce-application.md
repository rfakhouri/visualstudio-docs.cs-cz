---
title: 'Postupy: Úprava výchozí webové stránky pro aplikaci ClickOnce | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Publish.htm Web page
- ClickOnce deployment default Web page
- deploying applications [ClickOnce], publishing
- publishing, ClickOnce
ms.assetid: 418de18c-bee9-4f24-9cd9-0252d175070d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 743d7f259da4129eda578808d1ce04619104a3f1
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31557668"
---
# <a name="how-to-customize-the-default-web-page-for-a-clickonce-application"></a>Postupy: Úprava výchozí webové stránky pro aplikaci ClickOnce
Při publikování aplikací ClickOnce k webu, je automaticky generována a publikována spolu s aplikací na webové stránce. Výchozí stránka obsahuje název aplikace a odkazy na instalaci aplikace, instalace požadovaných součástí nebo získat přístup k nápovědě na webu MSDN.  
  
> [!NOTE]
>  Skutečné odkazy, které se zobrazí na stránce závisí na počítači, kde prohlížení stránky a co chcete zahrnout požadované součásti.  
  
 Název výchozí webové stránky je Publish.htm; můžete změnit název v **Návrhář projektu**. Další informace najdete v tématu [postupy: určení stránky publikování pro aplikaci ClickOnce](../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md).  
  
 Publish.htm – webová stránka je publikován pouze v případě, že je zjištěna novější verze.  
  
> [!NOTE]
>  Změny, které provedete vaše **publikovat** nastavení nebude mít vliv na stránce Publish.htm s jednou výjimkou: Pokud přidáte nebo odeberete požadavky po počátečním publikování, seznam požadovaných součástí už nebude přesná. Je potřeba upravit text pro odkaz požadovaných tak, aby odrážely změny.  
  
### <a name="to-customize-the-publish-web-page"></a>Chcete-li přizpůsobit publikování webové stránky  
  
1.  Publikování aplikace ClickOnce webových umístění. Další informace najdete v tématu [postupy: publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
2.  Na webovém serveru otevřete soubor Publish.htm v vizuálního návrháře webové nebo jiný editor HTML.  
  
3.  Přizpůsobení stránce podle potřeby a uložte ho.  
  
4.  Volitelné. Abyste zabránili přepsání přizpůsobené publikování webové stránky Visual Studio, zrušte zaškrtnutí políčka **automaticky generovat webovou stránku nasazení po každé publikování** v dialogovém okně Možnosti publikování.  
  
## <a name="see-also"></a>Viz také  
 [ClickOnce – zabezpečení a nasazení](../deployment/clickonce-security-and-deployment.md)   
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Postupy: instalace předpokladů s aplikací ClickOnce](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)   
 [Postupy: Určení stránky publikování pro aplikaci ClickOnce](../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md)