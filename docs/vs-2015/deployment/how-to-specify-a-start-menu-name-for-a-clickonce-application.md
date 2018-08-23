---
title: 'Postupy: určení názvu úvodní nabídky pro aplikaci ClickOnce | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Start menu resource name
- Start menu name
- ClickOnce deployment, Start menu name
ms.assetid: 4b5183b2-2fd4-4433-9310-4a73bb12c4e3
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 303d2cb53ce65fdc4a53a039c78664316579fece
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632404"
---
# <a name="how-to-specify-a-start-menu-name-for-a-clickonce-application"></a>Postupy: Určení názvu úvodní nabídky pro aplikaci ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: určení názvu nabídky Start pro aplikaci ClickOnce](https://docs.microsoft.com/visualstudio/deployment/how-to-specify-a-start-menu-name-for-a-clickonce-application).  
  
Když [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikace se nainstaluje pro použití online i offline, záznam se přidá do **spustit** nabídky a **přidat nebo odebrat programy** seznamu. Ve výchozím nastavení, zobrazovaný název je stejný jako název sestavení aplikace, ale zobrazované jméno můžete změnit nastavením **název produktu** v **možnosti publikování** dialogové okno.  
  
 **Název produktu** se zobrazí na stránce publish.htm; pro aplikace nainstalované v režimu offline, bude název položky v **Start** nabídky a také budou název, který se zobrazí v **přidat nebo odebrat Programy**.  
  
 **Název vydavatele** se zobrazí na stránce publish.htm výše **název produktu**, a pro aplikace nainstalované v režimu offline, bude také název složky, který obsahuje ikonu aplikace **Start**  nabídky.  
  
 Můžete nastavit **název produktu** a **název vydavatele** vlastnosti v **možnosti publikování** dialogovém okně k dispozici na **publikovat** stránky nástroje **Návrhář projektu**.  
  
### <a name="to-specify-a-start-menu-name"></a>K určení názvu úvodní nabídky  
  
1.  S projekt vybraný v **Průzkumníka řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte na tlačítko **publikovat** kartu.  
  
3.  Klikněte na tlačítko **možnosti** tlačítko Otevřít **možnosti publikování** dialogové okno.  
  
4.  Klikněte na tlačítko **popis**.  
  
5.  V **možnosti publikování** dialogového okna zadejte název, který má být zobrazen v **název produktu**.  
  
6.  Volitelně můžete zadat název vydavatele v **název vydavatele**.  
  
## <a name="see-also"></a>Viz také  
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Postupy: Publikování aplikace ClickOnce pomocí průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)



