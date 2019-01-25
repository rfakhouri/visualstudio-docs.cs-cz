---
title: 'Postupy: Nasazení a publikování řešení služby SharePoint na lokální stránce SharePoint | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- deploying [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, deploying
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 2efdc339500786de87c35b4caeb3c85cef5191b7
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54864095"
---
# <a name="how-to-deploy-and-publish-a-sharepoint-solution-to-a-local-sharepoint-site"></a>Postupy: Nasazení a publikování řešení služby SharePoint na lokální stránce SharePoint
  Můžete nasadit nebo publikování řešení služby SharePoint na místní server SharePoint ve svém vývojovém počítači. Tyto kopie procesu nasazení *.wsp* souboru na SharePoint serveru nainstaluje řešení a potom aktivuje funkce. Publikování zpracovat pouze kopie *.wsp* soubor na server SharePoint a nainstaluje ho. Musíte ručně aktivovat ji a povolte v Sharepointu.  
  
## <a name="to-deploy-a-sharepoint-solution-to-the-local-sharepoint-server"></a>K nasazení řešení služby SharePoint k místnímu serveru SharePoint  
  
1.  V **Průzkumníka řešení**, vyberte projekt, který chcete nasadit.  
  
2.  V panelu nabídky zvolte **sestavení**, **nasadit řešení**.  
  
     *.Wsp* soubor je vytvořen a nainstalován na místním serveru SharePoint. Kromě toho jsou aktivované funkce.  
  
## <a name="to-publish-a-sharepoint-solution-to-a-local-sharepoint-server"></a>Publikování řešení služby SharePoint na místní server služby SharePoint  
  
1.  V **Průzkumníka řešení**, otevřete místní nabídku pro projekt služby SharePoint, kterou chcete publikovat a pak zvolte **publikovat**.  
  
2.  V **publikovat** dialogového okna zvolte **publikování do souborového systému** přepínač.  
  
3.  V **cílové umístění** textové pole, zadejte místní cestu a klikněte na tlačítko **publikovat** tlačítko.  
  
     V sadě Visual Studio se zobrazí průběh publikování **výstup** okna. Po dokončení procesu, řešení (*.wsp*) je soubor nainstalovat na místním serveru SharePoint. Nicméně je nutné stále ho aktivovat pro použití v Sharepointu. Pokud soubor řešení již existuje, dojde k chybě a zeptá, jestli chcete přepsat existující soubor. Informace o upgradu balíčku najdete v části o upgradu vzdálené balíčky v [jak: Nasazení, publikování a upgradování řešení služby SharePoint na vzdáleném serveru](../sharepoint/how-to-deploy-publish-and-upgrade-sharepoint-solutions-on-a-remote-server.md).  
  
## <a name="see-also"></a>Viz také:
 [Postupy: Nasazení, publikování a upgradování řešení služby SharePoint na vzdáleném serveru](../sharepoint/how-to-deploy-publish-and-upgrade-sharepoint-solutions-on-a-remote-server.md)   
 [Vytváření balíčků řešení služby SharePoint](../sharepoint/creating-sharepoint-solution-packages.md)   
 [Postupy: Přizpůsobení balíčku řešení služby SharePoint](../sharepoint/how-to-customize-a-sharepoint-solution-package.md)   
 [Postupy: Přidání nebo odebrání funkcí a položek z balíku pomocí návrháře balíčků](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer.md)  
