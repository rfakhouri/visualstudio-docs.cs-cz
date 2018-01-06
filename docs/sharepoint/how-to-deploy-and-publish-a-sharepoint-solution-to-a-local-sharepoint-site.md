---
title: "Postupy: nasazení a publikování řešení služby SharePoint na místní web služby SharePoint | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- deploying [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, deploying
ms.assetid: 73f8d6a9-4c64-4bba-ae0e-9474baf8df26
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 9e643eb31062bcd81302fba6e7d35cc8dfa674b6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-deploy-and-publish-a-sharepoint-solution-to-a-local-sharepoint-site"></a>Postupy: Nasazení a publikování řešení služby SharePoint na lokální stránce SharePoint
  Můžete nasadit nebo publikování řešení služby SharePoint na místním serveru SharePoint na vývojovém počítači. Proces nasazení zkopíruje soubor WSP server služby SharePoint, nainstaluje řešení a potom aktivuje funkce. Proces publikování pouze zkopíruje soubor WSP server služby SharePoint a ho nainstaluje. Je nutné ručně aktivovat jej a povolte ve službě SharePoint.  
  
## <a name="to-deploy-a-sharepoint-solution-to-the-local-sharepoint-server"></a>K nasazení řešení služby SharePoint na místním serveru SharePoint  
  
1.  V **Průzkumníku**, zvolte projekt, který chcete nasadit.  
  
2.  Na řádku nabídek zvolte **sestavení**, **nasadit řešení**.  
  
     Soubor WSP a nainstalované na místním serveru SharePoint. Kromě toho jsou aktivované funkce.  
  
## <a name="to-publish-a-sharepoint-solution-to-a-local-sharepoint-server"></a>K publikování řešení služby SharePoint na místním serveru SharePoint  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídky projektu služby SharePoint, kterou chcete publikovat a potom zvolte **publikovat**.  
  
2.  V **publikovat** dialogovém okně vyberte **publikovat do systému souborů** tlačítko.  
  
3.  V **cílové umístění** textového pole zadejte místní cestu a potom zvolte **publikovat** tlačítko.  
  
     V sadě Visual Studio se zobrazí průběh publikování **výstup** okno. Po dokončení tohoto procesu je soubor řešení (WSP) je nainstalována na místním serveru SharePoint. Nicméně je nutné stále ho aktivovat pro použití ve službě SharePoint. Pokud již existuje soubor řešení, chybě dojde a zobrazí dotaz, zda chcete přepsat existující soubor. Informace o upgrade balíčku, najdete v části týkající se upgradu vzdálené balíčky v [postupy: nasazení, publikování a upgradovat řešení služby SharePoint na vzdáleném serveru](../sharepoint/how-to-deploy-publish-and-upgrade-sharepoint-solutions-on-a-remote-server.md).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: nasazení, publikování a upgradování řešení služby SharePoint na vzdáleném serveru](../sharepoint/how-to-deploy-publish-and-upgrade-sharepoint-solutions-on-a-remote-server.md)   
 [Vytváření balíčků řešení služby SharePoint](../sharepoint/creating-sharepoint-solution-packages.md)   
 [Postupy: přizpůsobení balíčku řešení služby SharePoint](../sharepoint/how-to-customize-a-sharepoint-solution-package.md)   
 [Postupy: Přidání nebo odebrání funkcí a položek z balíčku pomocí návrháře balíčků](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer.md)  
  
  