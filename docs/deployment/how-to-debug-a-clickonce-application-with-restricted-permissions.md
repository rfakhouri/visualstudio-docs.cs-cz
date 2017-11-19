---
title: "Postupy: ladění aplikace ClickOnce s omezenými oprávněními | Microsoft Docs"
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
- debugging [Visual Studio], ClickOnce applications
- ClickOnce deployment, debugging
- ClickOnce applications, debugging
ms.assetid: 6991ea91-5253-451b-923d-22273a3d38b1
caps.latest.revision: "10"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: aa51d29a1d5703f4fd02ee023eb1180da8031ac4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-debug-a-clickonce-application-with-restricted-permissions"></a>Postupy: Ladění aplikace ClickOnce s omezenými oprávněními
Jako vývojář pravděpodobně používáte vývojovém počítači s oprávnění úplné důvěryhodnosti, neuvidíte stejné výjimky zabezpečení při ladění aplikace ClickOnce, který koncoví uživatelé mohou se zobrazit při spuštění s omezenými oprávněními.  
  
 Aby bylo možné zachytit tyto výjimky, budete muset ladění aplikace se stejnými oprávněními jako koncový uživatel. Ladění s omezenými oprávněními, může být povoleno na **zabezpečení** stránky **Návrhář projektu**.  
  
 Kromě toho při vývoji aplikací, které volají webové služby, tyto webové služby často nacházejí ve svém vývojovém počítači. Po nasazení koncový uživatel přístup k těmto webovým službám z jinou adresu URL. Chcete-li emulovat činnost koncového uživatele během ladění, můžete zadat že adresu URL a ladicí program bude považovat webové služby, jako kdyby byly volány z této adresy URL.  
  
### <a name="to-enable-debugging-with-restricted-permissions"></a>Pokud chcete povolit ladění s omezenými oprávněními  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  V **Návrhář projektu**, klikněte **zabezpečení** kartě.  
  
3.  Vyberte **povolit nastavení zabezpečení ClickOnce** zaškrtněte políčko a klikněte **Toto je aplikace s částečnou důvěryhodností** tlačítko.  
  
4.  Klikněte **Upřesnit** tlačítko.  
  
5.  Vyberte **ladění tuto aplikaci s vybraným nastavením oprávnění** zaškrtněte políčko a potom klikněte na **OK**.  
  
     Při ladění aplikace, všechny pokusy o přístup k oprávněním, který není součástí sady oprávnění, bude vyvolána výjimka zabezpečení.  
  
### <a name="to-specify-a-url-for-debugging"></a>Zadejte adresu URL pro ladění  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  V **Návrhář projektu**, klikněte **zabezpečení** kartě.  
  
3.  Vyberte **povolit nastavení zabezpečení ClickOnce** zaškrtněte políčko a klikněte **Toto je aplikace s částečnou důvěryhodností** tlačítko.  
  
4.  Klikněte **Upřesnit** tlačítko.  
  
5.  Vyberte **ladění tuto aplikaci s vybraným nastavením oprávnění** zaškrtněte políčko a potom klikněte na **OK**.  
  
6.  V **ladění této aplikace, jako kdyby byly staženy z následující adresy URL** textového pole zadejte adresu URL nebo síťovou cestu.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: nastavení vlastních oprávnění pro aplikaci ClickOnce](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [Zabezpečování aplikací ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Zabezpečení přístupu kódu pro aplikace ClickOnce](../deployment/code-access-security-for-clickonce-applications.md)   
 [Zabezpečování aplikací ClickOnce](../deployment/securing-clickonce-applications.md)