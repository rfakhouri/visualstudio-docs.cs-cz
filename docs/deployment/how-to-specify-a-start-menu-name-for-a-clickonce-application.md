---
title: "Postupy: určení názvu úvodní nabídky pro aplikaci ClickOnce | Microsoft Docs"
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
- Start menu resource name
- Start menu name
- ClickOnce deployment, Start menu name
ms.assetid: 4b5183b2-2fd4-4433-9310-4a73bb12c4e3
caps.latest.revision: "17"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: f01bb5750f31101a6d8ec0cb5f33669e5fbf2b4b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-a-start-menu-name-for-a-clickonce-application"></a>Postupy: Určení názvu úvodní nabídky pro aplikaci ClickOnce
Když [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace se nainstaluje pro použití online i offline, bude položka přidána do **spustit** nabídky a **přidat nebo odebrat programy** seznamu. Ve výchozím nastavení, zobrazovaný název není stejný jako název sestavení aplikace, ale můžete změnit zobrazovaný název nastavením **název produktu** v **možnosti publikování** dialogové okno.  
  
 **Název produktu** se zobrazí na stránce publish.htm; pro aplikaci nainstalovanou v režimu offline, bude název položky v **spustit** nabídce a také se název, který se zobrazí v **přidat nebo odebrat Programy**.  
  
 **Název vydavatele** se zobrazí na stránce publish.htm výše **název produktu**, a pro aplikace nainstalované offline, bude také název složky, která obsahuje ikonu aplikace v **Start**  nabídky.  
  
 Můžete nastavit **název produktu** a **název vydavatele** vlastnosti v **možnosti publikování** dialogové okno, k dispozici na **publikovat** stránky z **Návrhář projektu**.  
  
### <a name="to-specify-a-start-menu-name"></a>K určení názvu úvodní nabídky  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte **publikovat** kartě.  
  
3.  Klikněte na tlačítko **možnosti** tlačítko Otevřít **možnosti publikování** dialogové okno.  
  
4.  Klikněte na tlačítko **popis**.  
  
5.  V **možnosti publikování** dialogovém okně zadejte název, který má zobrazit v **název produktu**.  
  
6.  Volitelně můžete zadat název vydavatele v **název vydavatele**.  
  
## <a name="see-also"></a>Viz také  
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Postupy: Publikování aplikace ClickOnce pomocí průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)