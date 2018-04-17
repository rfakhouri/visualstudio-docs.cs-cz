---
title: 'Postupy: určení alternativního umístění pro nasazení aktualizace | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, updates
- deployment update, alternative locations
ms.assetid: 7faacd35-2638-492d-80f6-6b57e5f820de
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 107fb4680b2ee5600c2cee847ebb3d2b5efd7da4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-specify-an-alternate-location-for-deployment-updates"></a>Postupy: Určení alternativního umístění pro aktualizace nasazení
Můžete nainstalovat vaší [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace původně z disku CD-ROM nebo sdílené složky, ale aplikace musí kontrolovat pravidelné aktualizace na webu. V manifestu nasazení můžete zadat alternativní umístění pro aktualizace, tak, aby vaše aplikace můžete aktualizovat přímo z webu po její počáteční instalaci.  
  
> [!NOTE]
>  Vaše aplikace musí být nakonfigurována pro instalaci místně pro tuto funkci používat. Další informace najdete v tématu [návod: Ruční nasazení aplikace ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md). Kromě toho, pokud nainstalujete [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace ze sítě, nastavení alternativního umístění příčiny [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] použije toto umístění pro počáteční instalaci a všechny následné aktualizace. Pokud nainstalujete aplikaci místně (například z disku CD), počáteční instalace se provádí pomocí původního média a všechny následné aktualizace bude používat alternativního umístění.  
  
### <a name="specifying-an-alternate-location-for-updates-by-using-mageuiexe-windows-forms-based-utility"></a>Zadat alternativní umístění pro aktualizace pomocí MageUI.exe (nástroj založený na Windows Forms)  
  
1.  Otevřete příkazový řádek rozhraní .NET Framework a zadejte:  
  
     **MageUI.exe**  
  
2.  Na **soubor** nabídce zvolte **otevřete** otevřete – manifest nasazení vaší aplikace.  
  
3.  Vyberte **možnosti nasazení** kartě.  
  
4.  Do textového pole s názvem **umístění spuštění**, zadejte adresu URL do adresáře, který bude obsahovat manifest nasazení aktualizací aplikací.  
  
5.  Uložte manifest nasazení.  
  
### <a name="specifying-an-alternate-location-for-updates-by-using-mageexe"></a>Zadat alternativní umístění pro aktualizace pomocí Mage.exe  
  
1.  Otevřete příkazový řádek rozhraní .NET Framework.  
  
2.  Nastavte umístění aktualizace pomocí následujícího příkazu. V tomto příkladu **HelloWorld.exe.application** je cesta k vaší [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifestu aplikace, který má vždy příponu .application a **http://adatum.com/Update/Path** je adresa URL, že [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bude kontrola aktualizací aplikace.  
  
     **Mage-aktualizovat HelloWorld.exe.application - ProviderUrl http://adatum.com/Update/Path**  
  
3.  Uložte soubor.  
  
    > [!NOTE]
    >  Nyní je třeba znovu podepsat soubor s Mage.exe. Další informace najdete v tématu [návod: Ruční nasazení aplikace ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md).  
  
## <a name="net-framework-security"></a>Zabezpečení rozhraní .NET Framework  
 Je-li nainstalovat aplikaci z offline média, například CD, a počítač je online, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nejprve zkontroluje adresu URL zadanou v `<deploymentProvider>` značky v manifestu nasazení k určení, zda umístění aktualizace obsahuje nejnovější verzi aplikace. Pokud ano, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nainstaluje aplikaci přímo z ní, místo z adresáře počáteční instalaci a common language runtime (CLR) určuje důvěryhodnosti aplikace na úrovni pomocí `<deploymentProvider>`. Pokud je počítač v režimu offline, nebo `<deploymentProvider>` nedostupný, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] instalace z disku CD a CLR uděluje důvěryhodnosti na základě instalace bodu; pro instalaci z disku CD, to znamená, vaše aplikace přijímá úplný vztah důvěryhodnosti. Všechny následné aktualizace zdědí tuto úroveň důvěryhodnosti.  
  
 Všechny [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace, které používají `<deploymentProvider>` by explicitně deklarovat oprávnění potřebují v jejich manifestu aplikace tak, aby aplikace neobdrží různé úrovně důvěryhodnosti na různých počítačích.  
  
## <a name="see-also"></a>Viz také  
 [Návod: Ruční nasazení aplikace ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)   
 [ClickOnce – Manifest nasazení](../deployment/clickonce-deployment-manifest.md)   
 [Zabezpečování aplikací ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Výběr strategie aktualizace ClickOnce](../deployment/choosing-a-clickonce-update-strategy.md)