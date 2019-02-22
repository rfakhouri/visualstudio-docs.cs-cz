---
title: 'Postupy: Určení názvu úvodní nabídky pro aplikaci ClickOnce | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Start menu resource name
- Start menu name
- ClickOnce deployment, Start menu name
ms.assetid: 4b5183b2-2fd4-4433-9310-4a73bb12c4e3
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3ab55674cd1de54881eb46b47997a943678cbacd
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56635615"
---
# <a name="how-to-specify-a-start-menu-name-for-a-clickonce-application"></a>Postupy: Určení názvu úvodní nabídky pro aplikaci ClickOnce
Když [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace se nainstaluje pro použití online i offline, záznam se přidá do **spustit** nabídky a **přidat nebo odebrat programy** seznamu. Ve výchozím nastavení, zobrazovaný název je stejný jako název sestavení aplikace, ale zobrazované jméno můžete změnit nastavením **název produktu** v **možnosti publikování** dialogové okno.

 **Název produktu** bude zobrazen na *publish.htm* stránky; pro aplikace nainstalované v režimu offline, bude název položky v **Start** nabídky a také budou název, který se zobrazuje v **Přidat nebo odebrat programy**.

 **Název vydavatele** se zobrazí na *publish.htm* stránky výše **název produktu**, a pro aplikace nainstalované v režimu offline, bude také název složky, která obsahuje aplikace ikona **Start** nabídky.

 Vytvoří se odkaz aplikace nebo místní nabídky Start ve *%appdata%\Microsoft\Windows\Start Start\Programy\\< název vydavatele\>*. Odkaz na místní nebo aplikace má stejný název jako název produktu.

 Můžete nastavit **název produktu** a **název vydavatele** vlastnosti v **možnosti publikování** dialogovém okně k dispozici na **publikovat** stránky nástroje **Návrhář projektu**.

### <a name="to-specify-a-start-menu-name"></a>K určení názvu úvodní nabídky

1.  S projekt vybraný v **Průzkumníka řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.

2.  Klikněte na tlačítko **publikovat** kartu.

3.  Klikněte na tlačítko **možnosti** tlačítko Otevřít **možnosti publikování** dialogové okno.

4.  Klikněte na tlačítko **popis**.

5.  V **možnosti publikování** dialogového okna zadejte název, který má být zobrazen v **název produktu**.

6.  Volitelně můžete zadat název vydavatele v **název vydavatele**.

## <a name="see-also"></a>Viz také:
- [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)
- [Postupy: Publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)