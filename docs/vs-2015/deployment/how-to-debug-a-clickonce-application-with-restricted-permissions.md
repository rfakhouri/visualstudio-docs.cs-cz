---
title: 'Postupy: Ladění aplikace ClickOnce s omezenými oprávněními | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], ClickOnce applications
- ClickOnce deployment, debugging
- ClickOnce applications, debugging
ms.assetid: 6991ea91-5253-451b-923d-22273a3d38b1
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: d60f88c4d1532a03922f12f21bb9b455ef5d84d8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68153803"
---
# <a name="how-to-debug-a-clickonce-application-with-restricted-permissions"></a>Postupy: Ladění aplikace ClickOnce s omezenými oprávněními
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Jako vývojář pravděpodobně používáte vývojového počítače oprávnění plné důvěryhodnosti, takže neuvidíte stejné výjimky zabezpečení při ladění aplikace ClickOnce, která koncový uživatel může zobrazit při spuštění s omezenými oprávněními.  
  
 Pokud chcete zachytit tyto výjimky, je potřeba ladění aplikace se stejnými oprávněními jako koncový uživatel. Ladění s omezenými oprávněními může být povoleno na **zabezpečení** stránku **Návrháře projektu**.  
  
 Kromě toho při vývoji aplikací, které volají webové služby, tyto webové služby často jsou umístěny ve svém vývojovém počítači. Po nasazení, koncovému uživateli přístup k těmto webovým službám z jinou adresu URL. Pokud chcete emulovat činnost koncového uživatele při ladění, můžete zadat že adresu URL a ladicí program bude považovat webové služby, jako kdyby byly volány z této adresy URL.  
  
### <a name="to-enable-debugging-with-restricted-permissions"></a>Pokud chcete povolit ladění s omezenými oprávněními  
  
1. S projekt vybraný v **Průzkumníka řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2. V **Návrháře projektu**, klikněte na tlačítko **zabezpečení** kartu.  
  
3. Vyberte **povolit nastavení zabezpečení ClickOnce** zaškrtněte políčko a potom klikněte **Toto je aplikace s částečnou důvěryhodností** přepínač.  
  
4. Klikněte na tlačítko **Upřesnit** tlačítko.  
  
5. Vyberte **Ladit tuto aplikaci s vybranou sadou oprávnění** zaškrtněte políčko a potom klikněte na tlačítko **OK**.  
  
     Při ladění aplikace, všechny pokusy o přístup k oprávněním, který není součástí sady oprávnění vyvolá výjimka zabezpečení.  
  
### <a name="to-specify-a-url-for-debugging"></a>Zadejte adresu URL pro ladění  
  
1. S projekt vybraný v **Průzkumníka řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2. V **Návrháře projektu**, klikněte na tlačítko **zabezpečení** kartu.  
  
3. Vyberte **povolit nastavení zabezpečení ClickOnce** zaškrtněte políčko a potom klikněte **Toto je aplikace s částečnou důvěryhodností** přepínač.  
  
4. Klikněte na tlačítko **Upřesnit** tlačítko.  
  
5. Vyberte **Ladit tuto aplikaci s vybranou sadou oprávnění** zaškrtněte políčko a potom klikněte na tlačítko **OK**.  
  
6. V **Ladit tuto aplikaci, jako kdyby byla stažena z následující adresy URL** textového pole zadejte adresu URL nebo síťovou cestu.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Nastavení vlastních oprávnění pro aplikaci ClickOnce](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [Zabezpečování aplikací ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Zabezpečení přístupu ke kódu pro aplikace ClickOnce](../deployment/code-access-security-for-clickonce-applications.md)   
 [Zabezpečování aplikací ClickOnce](../deployment/securing-clickonce-applications.md)
