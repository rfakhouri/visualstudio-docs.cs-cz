---
title: "Postupy: podepisování řešení pro systém Office | Microsoft Docs"
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
helpviewer_keywords:
- certificates [Office development in Visual Studio], Office solutions
- security [Office development in Visual Studio], signing Office solutions
- signing manifests [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 2883f75c6ca75e1875621f9c6779db09722d6945
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-sign-office-solutions"></a>Postupy: Podepisování řešení pro systém Office
  Pokud podepíšete řešení, můžete udělit vztah důvěryhodnosti k řešení pomocí certifikátu jako důkaz. Můžete použít stejný certifikát pro více řešení a všechna řešení budou důvěryhodné s žádné další bezpečnostní aktualizace zásad.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Pokud je ručně upravit, aplikace a manifesty nasazení pomocí generování manifestu a nástroj pro úpravy (mage.exe a mageui.exe), musíte znovu podepsat manifesty, abyste mohli používat. Další informace najdete v tématu [postupy: opakované podepsání aplikace a manifesty nasazení](/visualstudio/deployment/how-to-re-sign-application-and-deployment-manifests).  
  
## <a name="signing-by-using-a-certificate"></a>Podepisování pomocí certifikátu  
 Certifikát je soubor, který obsahuje jedinečný klíč a identity vydavatele. Můžete nákup certifikátů od certifikační autority, nebo vytvořit svůj vlastní certifikát a mít certifikační autority podepsat ji.  
  
 Visual Studio podepisuje řešení Office s certifikátem dočasné chcete povolit ladění. Dočasné certifikát v nasazeném řešení byste neměli používat jako důkaz.  
  
#### <a name="to-sign-an-office-solution-by-using-a-certificate"></a>K podepisování řešení Office s použitím certifikátu  
  
1.  Na **projektu** nabídky, klikněte na tlačítko *název řešení SolutionName***vlastnosti**.  
  
2.  Klikněte **podpisování** kartě.  
  
3.  Vyberte **podepsání manifestů ClickOnce**.  
  
4.  Vyhledejte certifikát klepnutím na **zvolit z úložiště** nebo **vybrat ze souboru** a přejdete na certifikátu.  
  
5.  Chcete-li ověřit, jestli se používá správný certifikát, klikněte na tlačítko **další podrobnosti** k zobrazení informací o certifikátu.  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)   
 [Udělení důvěry pro řešení pro systém Office](../vsto/granting-trust-to-office-solutions.md)   
 [Stránka Podepisování, Návrhář projektu](/visualstudio/ide/reference/signing-page-project-designer)  
  
  