---
title: 'Postupy: podepisování řešení pro systém Office | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- certificates [Office development in Visual Studio], Office solutions
- security [Office development in Visual Studio], signing Office solutions
- signing manifests [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 31b5e1fc3c78aecf518af0941a4a2dd0ab7e57c5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-sign-office-solutions"></a>Postupy: Podepisování řešení pro systém Office
  Pokud podepíšete řešení, můžete udělit vztah důvěryhodnosti k řešení pomocí certifikátu jako důkaz. Můžete použít stejný certifikát pro více řešení a všechna řešení budou důvěryhodné s žádné další bezpečnostní aktualizace zásad.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Pokud je ručně upravit, aplikace a manifesty nasazení pomocí generování manifestu a nástroj pro úpravy (mage.exe a mageui.exe), musíte znovu podepsat manifesty, abyste mohli používat. Další informace najdete v tématu [postupy: opakované podepsání aplikace a manifesty nasazení](/visualstudio/deployment/how-to-re-sign-application-and-deployment-manifests).  
  
## <a name="signing-by-using-a-certificate"></a>Podepisování pomocí certifikátu  
 Certifikát je soubor, který obsahuje jedinečný klíč a identity vydavatele. Můžete nákup certifikátů od certifikační autority, nebo vytvořit svůj vlastní certifikát a mít certifikační autority podepsat ji.  
  
 Visual Studio podepisuje řešení Office s certifikátem dočasné chcete povolit ladění. Dočasné certifikát v nasazeném řešení byste neměli používat jako důkaz.  
  
#### <a name="to-sign-an-office-solution-by-using-a-certificate"></a>K podepisování řešení Office s použitím certifikátu  
  
1.  Na **projektu** nabídky, klikněte na tlačítko * název řešení SolutionName ***vlastnosti**.  
  
2.  Klikněte **podpisování** kartě.  
  
3.  Vyberte **podepsání manifestů ClickOnce**.  
  
4.  Vyhledejte certifikát klepnutím na **zvolit z úložiště** nebo **vybrat ze souboru** a přejdete na certifikátu.  
  
5.  Chcete-li ověřit, jestli se používá správný certifikát, klikněte na tlačítko **další podrobnosti** k zobrazení informací o certifikátu.  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)   
 [Udělení důvěry pro řešení pro systém Office](../vsto/granting-trust-to-office-solutions.md)   
 [Stránka Podepisování, Návrhář projektu](/visualstudio/ide/reference/signing-page-project-designer)  
  
  