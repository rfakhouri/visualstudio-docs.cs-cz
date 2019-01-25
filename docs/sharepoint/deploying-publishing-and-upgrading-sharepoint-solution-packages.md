---
title: Nasazení, publikování a upgradování balíčků řešení služby SharePoint | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.Project.SharePointProjectPropertyTab
- VS.SharePointTools.Project.Publishing
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
ms.openlocfilehash: ebe207bffe16ef7b8dc7af5a79c01b3ee74abe3f
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54863276"
---
# <a name="deploy-publish-and-upgrade-sharepoint-solution-packages"></a>Nasazení, publikování a upgrade balíčků řešení služby SharePoint
  Poté, co při vývoji řešení služby SharePoint v sadě Visual Studio, můžete nasadit jeho souboru balíčku (.wsp) na místním serveru SharePoint nebo ji publikovat na Sharepointový server vzdálený, nebo místní. Pokud nasazujete soubory, můžete přizpůsobit, jak nasadit soubory balíčku (.wsp).  
  
> [!NOTE]  
>  V současné době pouze řešení v izolovaném prostoru, můžete ho publikovat do vzdálených serverů služby SharePoint. Další informace najdete v tématu [aspekty řešení v izolovaném prostoru](../sharepoint/sandboxed-solution-considerations.md).  
  
## <a name="deploy-publish-and-upgrade"></a>Nasazení, publikování a upgrade
 *Nasazení* odkazuje na kopírování souboru řešení služby SharePoint vytvořená z projektu služby SharePoint v sadě Visual Studio na místního hostitele. V nasazeném řešení můžete nakonfigurovat jednotlivé kroky nasazení, jako je například recyklace fondu Internetové informační služby (IIS), aktivuje se po nasazení řešení a tak dále. Pokud chcete nasadit, použijte **nasazení** příkaz **sestavení** nabídky. Další informace najdete v tématu [jak: Úprava konfigurace nasazení služby SharePoint](../sharepoint/how-to-edit-a-sharepoint-deployment-configuration.md) a [jak: Nasazení a publikování řešení služby SharePoint na místní Sharepointový web](../sharepoint/how-to-deploy-and-publish-a-sharepoint-solution-to-a-local-sharepoint-site.md).  
  
 *Publikování* odkazuje na nahrání souboru v izolovaném prostoru řešení SharePoint do vzdáleného serveru SharePoint Web; to znamená, umístěné v jiném systému lokality. Můžete také publikovat soubor řešení v izolovaném prostoru služby SharePoint na lokální stránce SharePoint, ale bez ohledu na to, zda je stránka publikují do místního nebo vzdáleného, není možné konfigurovat jeho kroky nasazení.  
  
 *Upgrade* odkazuje na aktualizaci existující vzdáleně nebo místně publikované řešení služby SharePoint. Po provedení změny do řešení služby SharePoint v sadě Visual Studio, můžete změnit název souboru balíčku řešení, znovu publikovat řešení a pak upgradovat řešení po se úspěšně znovu publikuje uzamkl. Pokud publikujete místně publikované řešení, můžete přepsat existující soubor řešení.  
  
## <a name="deploy-packages"></a>Nasadit balíčky
 Soubory balíčku můžete nasadit na server SharePoint na vašem vývojovém počítači pro účely testování a ladění. Můžete také vytvořit soubor balíčku, který můžete nainstalovat na jiný počítač kliknutím **publikování do souborového systému** přepínač v **publikovat** dialogové okno. Balíček je vytvořili a zkopírovali do Zadaná místní cesta k souboru. K nasazení řešení služby SharePoint na místní server, použijte **nasadit** příkaz **sestavení** nabídky. Další informace najdete v tématu [jak: Nasazení a publikování řešení služby SharePoint na lokální stránce SharePoint](../sharepoint/how-to-deploy-and-publish-a-sharepoint-solution-to-a-local-sharepoint-site.md).  
  
 Informace o nasazení definice seznamu, přidat přijímače událostí a používání funkce návrháře a návrháři balíčku najdete v tématu [názorný postup: Nasazení definice seznamu úloh projektu](../sharepoint/walkthrough-deploying-a-project-task-list-definition.md).  
  
## <a name="customize-the-deployment-process"></a>Přizpůsobení procesu nasazení
 V následující tabulce jsou uvedeny oběma konfiguracemi nasazení, které můžete využít při ladění a nasazení řešení služby SharePoint.  
  
|Konfigurace nasazení|Popis|  
|------------------------------|-----------------|  
|Výchozí|Výchozí konfigurace nasazení. Jsou prováděny následující kroky nasazení:<br /><br /> 1.  Spusťte příkaz před nasazením.<br />2.  Recyklujte fond aplikací služby IIS.<br />3.  Odvolat řešení.<br />4.  Přidáte řešení.<br />5.  Aktivace funkce.<br />6.  Spusťte příkaz po nasazení.<br /><br /> Po odinstalaci balíčku se provést následující kroky odvolání.<br /><br /> 1.  Recyklujte fond aplikací služby IIS.<br />2.  Odvolat řešení.|  
|Nevyžaduje se žádná aktivace|Tato konfigurace nasazení spouští stejný postup jako výchozí konfiguraci, ale přeskočí krok aktivace.|  
  
 Můžete vytvořit vlastní konfigurace nasazení na dokončení jednoho kroku nebo změnit pořadí kroků v procesu nasazení. Další informace najdete v tématu [jak: Úprava konfigurace nasazení služby SharePoint](../sharepoint/how-to-edit-a-sharepoint-deployment-configuration.md).  

 Můžete také přidat příkazy se spustí před a po nasazení. Další informace najdete v tématu [jak: Nastavení příkazů nasazení služby SharePoint](../sharepoint/how-to-set-sharepoint-deployment-commands.md).  
  
## <a name="publish-packages-to-a-remote-or-local-server"></a>Publikovat balíčky do vzdáleného nebo místního serveru
 Chcete-li publikovat v izolovaném prostoru řešení služby SharePoint na vzdáleném serveru, na panelu nabídek zvolte **sestavení**, **publikovat**a pak na **publikovat** dialogové okno Vyberte **Publikovat na webu služby SharePoint** přepínač poskytuje adresu URL vzdáleného serveru, jako například **https://someremoteserver.sharepoint.microsoftonline.com**.  
  
 Publikování řešení služby SharePoint na místním serveru, v **publikovat** dialogového okna zvolte **publikování do souborového systému** přepínač poskytuje místní systémové cesty.  
  
 Po řešení se úspěšně publikuje do služby SharePoint, řešení se zobrazí v **Galerie řešení** kde ji můžete aktivovat. Další informace najdete v tématu [jak: Nasazení, publikování a upgradování řešení služby SharePoint na vzdáleném serveru](../sharepoint/how-to-deploy-publish-and-upgrade-sharepoint-solutions-on-a-remote-server.md).  
  
### <a name="upgrade-published-packages"></a>Publikované balíčky s upgradem
 Pokud provedete změny projektu služby SharePoint v sadě Visual Studio po publikování, musí být zveřejněný balíček upgradovat na tyto změny zahrnout. Upgrade úspěšně, balíček musí mít jedinečný název. Pokud balíček se stejným názvem se nachází na webu služby SharePoint, - kterému může dojít, pokud aktualizujete existující aplikaci – chybové oznámení můžete k názvu souboru jsou v konfliktu a slouží k přejmenování balíček. Nový balíček po znovu publikovat, se zobrazí na webu služby SharePoint a je možné upgradovat. Aktualizovaného balíčku aktualizací řešení s použitím dat z balíčku starší a potom aktivuje řešení služby SharePoint. Další informace najdete v tématu [jak: Nasazení, publikování a upgradování řešení služby SharePoint na vzdáleném serveru](../sharepoint/how-to-deploy-publish-and-upgrade-sharepoint-solutions-on-a-remote-server.md).  
  
## <a name="see-also"></a>Viz také:
 [Zabalení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
