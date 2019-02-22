---
title: 'Postupy: Nasazení, publikování a upgradování řešení služby SharePoint na vzdáleném serveru | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- remote deployment [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, remote deployment
- deploying [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, deploying
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: ed75a5a6d888f3fc82acf8e7d41ac2ec82007636
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56639775"
---
# <a name="how-to-deploy-publish-and-upgrade-sharepoint-solutions-on-a-remote-server"></a>Postupy: Nasazení, publikování a upgradování řešení služby SharePoint na vzdáleném serveru
  Kromě nasazení řešení služby SharePoint do místního systému, můžete publikovat v izolovaném prostoru řešení SharePoint vzdálenými lokalitami nebo místní weby služby SharePoint. Tyto vzdálené kopie procesu publikování *.wsp* souboru na SharePoint serveru nainstaluje řešení a pak umožňuje aktivovat řešení. Rovněž lze upgradovat vzdálenou instalaci řešení služby SharePoint po provedení změn na ni.

## <a name="to-publish-a-sandboxed-sharepoint-solution-to-a-remote-sharepoint-server"></a>Chcete-li publikovat v izolovaném prostoru řešení SharePoint na vzdálený server služby SharePoint

1.  V **Průzkumníka řešení**, otevřete místní nabídku v izolovaném prostoru projektu služby SharePoint, kterou chcete publikovat a pak zvolte **publikovat**.

2.  V **publikovat** dialogového okna zvolte **publikovat na webu služby SharePoint** přepínač a potom zadejte adresu URL webu online publikování třeba: `https://mytestsite.sharepoint.microsoftonline.com`.

3.  Zvolte **otevřít v prohlížeči stránku Galerie řešení po publikování** přepínač a zobrazit seznam řešení **Galerie řešení** stránku po publikování.

4.  Zvolte **publikovat** tlačítko.

5.  Pokud se vyžaduje ověření uživatele, přihlaste se ke vzdálenému serveru.

     V sadě Visual Studio se zobrazí průběh publikování **výstup** okna. Po dokončení procesu, řešení (*.wsp*) soubor je nainstalovaný na vzdáleném serveru SharePoint. Nicméně je nutné stále ho aktivovat předtím, než je možné v Sharepointu.

6.  Na **Galerie řešení** stránky, vyberte aplikaci služby SharePoint a potom na pásu karet, zvolte **aktivovat** tlačítko.

7.  V **aktivovat řešení** dialogovém okně na pásu karet, zvolte **aktivovat** tlačítko znovu.

     **Stav** sloupec **Galerie řešení** stránka indikuje, že je aplikace aktivní.

## <a name="to-upgrade-a-sandboxed-sharepoint-solution-on-a-remote-sharepoint-server"></a>Upgradovat řešení v izolovaném prostoru služby SharePoint na vzdáleném serveru SharePoint
 Pokud v izolovaném prostoru řešení SharePoint je již publikována na vzdáleném serveru, následující postup umožňuje upgradovat po provedení změn na aplikaci v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].

1.  Přejmenovat balíček Sharepointu v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Chcete-li to provést, v **Průzkumníka řešení** otevření balíku. Zobrazí se v **Průzkumníku balíčků**.

2.  V **Průzkumníku balíčků**v **název** pole, změňte název balíčku na jedinečný název.

3.  Uložte projekt.

4.  V **Průzkumníka řešení**, otevřete místní nabídku pro projekt a klikněte na tlačítko **publikovat**.

5.  V **publikovat** dialogového okna zvolte **publikovat na webu služby SharePoint** přepínač a pokud chybí adresa URL pro vzdálený server, ve kterém je uložený řešení, zadejte ji.

6.  Zvolte **otevřít v prohlížeči stránku Galerie řešení po publikování** přepínač a zobrazit seznam řešení **Galerie řešení** stránku po publikování.

7.  Zvolte **publikovat** tlačítko.

8.  Pokud se vyžaduje ověření uživatele, přihlaste se ke vzdálenému serveru.

     Pokud jste přihlášení ke vzdálenému serveru nedávno, nemusí být vyžaduje ověřování.

     Starší verze aplikace, která má stejný název stále existuje na serveru SharePoint, zobrazí se chyba, že balíček se stejným názvem už na serveru SharePoint. Balíček je třeba přejmenovat na jedinečný název před publikováním.

9. Zvolte Nová aplikace ve službě SharePoint a potom na pásu karet, zvolte **upgradovat** tlačítko.

10. V **Upgrade řešení** dialogovém okně na pásu karet, zvolte **upgradovat** tlačítko znovu. **Stav** sloupec **Galerie řešení** stránka by teď ukazují, že je aplikace aktivní.

     Stará verze řešení je deaktivováno, upgradovaná novou verzi řešení data udržovaná z původní řešení a nové řešení se aktivuje v Sharepointu.

## <a name="see-also"></a>Viz také:
- [Postupy: Nasazení a publikování řešení služby SharePoint na lokální stránce SharePoint](../sharepoint/how-to-deploy-and-publish-a-sharepoint-solution-to-a-local-sharepoint-site.md)
- [Vytváření balíčků řešení služby SharePoint](../sharepoint/creating-sharepoint-solution-packages.md)
- [Postupy: Přizpůsobení balíčku řešení služby SharePoint](../sharepoint/how-to-customize-a-sharepoint-solution-package.md)
- [Postupy: Přidání nebo odebrání funkcí a položek z balíku pomocí návrháře balíčků](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer.md)
